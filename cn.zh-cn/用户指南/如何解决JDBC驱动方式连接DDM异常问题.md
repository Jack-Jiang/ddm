# 如何解决JDBC驱动方式连接DDM异常问题<a name="ddm_04_0008"></a>

MySQL驱动（ JDBC）通过Loadbalance方式连接DDM，在某些场景下连接切换时会陷入死循环，最终导致栈溢出。

## 问题定位<a name="section32751322962"></a>

1.  查看APP日志，定位异常原因。

    例如，从以下日志中分析出异常最终原因为栈溢出。

    ```
    Caused by: java.lang.StackOverflowError
         at java.nio.HeapByteBuffer.<init>(HeapByteBuffer.java:57)
         at java.nio.ByteBuffer.allocate(ByteBuffer.java:335)
         at java.nio.charset.CharsetEncoder.encode(CharsetEncoder.java:795)
         at java.nio.charset.Charset.encode(Charset.java:843)
         at com.mysql.jdbc.StringUtils.getBytes(StringUtils.java:2362)
         at com.mysql.jdbc.StringUtils.getBytes(StringUtils.java:2344)
         at com.mysql.jdbc.StringUtils.getBytes(StringUtils.java:568)
         at com.mysql.jdbc.StringUtils.getBytes(StringUtils.java:626)
         at com.mysql.jdbc.Buffer.writeStringNoNull(Buffer.java:670)
         at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2636)
    ```

2.  分析溢出源。

    例如，从以下日志可以分析出，溢出原因为驱动内部陷入死循环。

    ```
    at com.mysql.jdbc.LoadBalancedConnectionProxy.pickNewConnection(LoadBalancedConnectionProxy.java:344)
    at com.mysql.jdbc.LoadBalancedAutoCommitInterceptor.postProcess(LoadBalancedAutoCommitInterceptor.java:104)
    at com.mysql.jdbc.MysqlIO.invokeStatementInterceptorsPost(MysqlIO.java:2885)
    at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2808)
    at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2483)
    at com.mysql.jdbc.ConnectionImpl.setReadOnlyInternal(ConnectionImpl.java:4961)
    at com.mysql.jdbc.ConnectionImpl.setReadOnly(ConnectionImpl.java:4954)
    at com.mysql.jdbc.MultiHostConnectionProxy.syncSessionState(MultiHostConnectionProxy.java:381)
    at com.mysql.jdbc.MultiHostConnectionProxy.syncSessionState(MultiHostConnectionProxy.java:366)
    at com.mysql.jdbc.LoadBalancedConnectionProxy.pickNewConnection(LoadBalancedConnectionProxy.java:344)
    ```

3.  查看使用的MySQL版本，为5.1.44。

    查看该版本源代码，发现获取连接时，**LoadBalance**会根据负载均衡策略更新连接，并将老连接的配置复制给新连接，在新连接**AutoCommit**为**true**，新连接部分参数和老连接不一致，**loadBalanceAutoCommitStatementThreshold**参数没有配置的场景下，会陷入死循环，更新连接函数调用同步参数函数，同步参数又调用更新连接，最终导致栈溢出。


## 解决方法<a name="section132331111272"></a>

在连接DDM的URL添加**loadBalanceAutoCommitStatementThreshold=5&retriesAllDown=10**参数。

```
//使用负载均衡的连接示例
//jdbc:mysql:loadbalance://ip1:port1,ip2:port2..ipN:portN/{db_name}
String url = "jdbc:mysql:loadbalance://192.168.0.200:5066,192.168.0.201:5066/db_5133?loadBalanceAutoCommitStatementThreshold=5&retriesAllDown=10";
```

-   loadBalanceAutoCommitStatementThreshold：表示连接上执行多少个语句后会重新选择连接。

    假设loadBalanceAutoCommitStatementThreshold设为5，则当执行5个sql后（Queries或者updates等），将会重新选择连接。若为0表示“粘性连接，不重新选择连接”。关闭自动提交时（autocommit=false）会等待事务完成再考虑是否重新选择连接。


