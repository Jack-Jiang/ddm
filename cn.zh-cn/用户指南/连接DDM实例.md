# 连接DDM实例<a name="ddm_02_0005"></a>

MySQL命令行或者图形化MySQL客户端（如Navicat）连接DDM实例访问实例下的逻辑库。

Java应用程序通过JDBC驱动连接DDM实例，具体步骤请参见[JDBC驱动连接DDM实例](#section1690417388176)。

如果客户端应用程序无法支持负载均衡，可以使用mysql-router搭建负载均衡进行业务测试以评估是否满足应用需求，具体步骤请参见[sidecar模式负载均衡](#section177069583187)。

PHP驱动方式连接请参见[PHP驱动连接](#section1773918484207)。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   连接前需确保已成功配置DDM实例；弹性云服务器上已安装MySQL客户端或程序已配置好MySQL连接驱动，MySQL客户端建议使用5.6或5.7版本，不兼容8.0版本。  
>-   出于安全考虑，连接DDM所使用的弹性云服务器必须与DDM实例处于相同的虚拟私有云（VPC）。  
>-   弹性云服务器和DDM实例的安全组分别有互通的访问规则。  
>-   DDM实例目前不支持绑定弹性公网IP，因此客户端不能从公网直接访问DDM实例。您可以通过搭建网络代理方式，使得客户端从公网访问DDM实例。  

## 获取DDM实例连接地址<a name="section1567342520566"></a>

1.  登录管理控制台。
2.  在导航上选择“数据库 \> 分布式数据库中间件”，进入总览页面。
3.  单击左侧菜单栏的“DDM实例管理”，进入“DDM实例管理”页面，列表中显示DDM实例连接地址。
4.  您还可以直接单击DDM实例名称，进入实例详情页面。在其中的“逻辑库管理”页签中，单击实例名称前的下箭头展开实例详情，获取命令行连接地址或jdbc连接地址，在“账号管理”页签中获取DDM实例的账号信息。
5.  使用以上获取到的DDM实例连接信息，连接DDM实例。

    DDM实例提供多个连接地址，确保连接的可用性，使用应用程序驱动方式连接DDM实例时，建议配置负载均衡。

    配置负载均衡的优先推荐顺序如下：

    1.  [JDBC驱动连接DDM实例](#section1690417388176)
    2.  [sidecar模式负载均衡](#section177069583187)
    3.  [PHP驱动连接](#section1773918484207)

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >连接DDM时，如果多次输入错误密码，系统将会自动锁定20分钟，DDM支持手工解锁。  


## MySQL命令行连接DDM实例<a name="section1621624581510"></a>

登录弹性云服务器，打开命令行工具，输入连接以下命令。

**mysql -h $\{**_DDM\_SERVER\_ADDRESS_**\} -P$\{**_DDM\_SERVER\_PORT_**\} -u$\{**_DDM\_USER_**\} -p \[-D$\{**_DDM\_DBNAME_**\}\] \[--default-character-set=utf8\]**

参数值填写说明如下。

**表 1**  mysql客户端连接参数说明

<a name="table17511477146"></a>
<table><thead align="left"><tr id="row105074701420"><th class="cellrowborder" valign="top" width="39%" id="mcps1.2.3.1.1"><p id="p3501147171410"><a name="p3501147171410"></a><a name="p3501147171410"></a>参数示例</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.3.1.2"><p id="p20501847181410"><a name="p20501847181410"></a><a name="p20501847181410"></a>参数填写说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row2506471142"><td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.3.1.1 "><p id="p195014771414"><a name="p195014771414"></a><a name="p195014771414"></a>DDM_SERVER_ADDRESS</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.3.1.2 "><p id="p1450134711417"><a name="p1450134711417"></a><a name="p1450134711417"></a>DDM实例所在IP地址。</p>
</td>
</tr>
<tr id="row19500478148"><td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.3.1.1 "><p id="p155013475149"><a name="p155013475149"></a><a name="p155013475149"></a>DDM_SERVER_PORT</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.3.1.2 "><p id="p125024713146"><a name="p125024713146"></a><a name="p125024713146"></a>DDM实例连接端口。</p>
</td>
</tr>
<tr id="row5512477140"><td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.3.1.1 "><p id="p450547171415"><a name="p450547171415"></a><a name="p450547171415"></a>DDM_USER</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.3.1.2 "><p id="p6501247141416"><a name="p6501247141416"></a><a name="p6501247141416"></a>DDM实例账号。</p>
</td>
</tr>
<tr id="row1551134751412"><td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.3.1.1 "><p id="p351347191413"><a name="p351347191413"></a><a name="p351347191413"></a>DDM_DBNAME</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.3.1.2 "><p id="p151947171410"><a name="p151947171410"></a><a name="p151947171410"></a>DDM实例逻辑库名，选填。</p>
</td>
</tr>
<tr id="row1851144719143"><td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.3.1.1 "><p id="p45194716149"><a name="p45194716149"></a><a name="p45194716149"></a>default-character-set=utf8</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.3.1.2 "><p id="p16519479144"><a name="p16519479144"></a><a name="p16519479144"></a>指定字符编码为UTF-8，选填。</p>
<p id="p1251147121412"><a name="p1251147121412"></a><a name="p1251147121412"></a>当mysql连接编码和实际编码不一致，导致DDM解析出现乱码时请配置该参数。</p>
</td>
</tr>
</tbody>
</table>

下图为Windows服务器命令行窗口中使用mysql命令连接服务器回显情况。

```
C:\Users\testDDM>mysql -h192.168.0.200 -P5066 -Ddb_5133 -udbuser01 -p
Enter password:
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A
 
Welcome to the MySQL monitor.  Commands end with ;or \g.
Your MySQL connection id is 5
Server version: 5.6.29
 
Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.
 
Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.
 
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
 
mysql>
```

## Navicat客户端连接DDM实例<a name="section1620213565506"></a>

通过Navicat客户端连接DDM实例的操作和通过其他图形化管理MySQL客户端（例如，MySQL Workbench）连接DDM实例的操作基本一致，在此不做详细描述。

在通过Navicat客户端多线程导入数据时，有以下约束条件：

1.  autocommit参数不能等于0或者OFF。
2.  事务模型不能为“最终原子性”。
3.  在满足单语句的限制条件下，导入的数据仅仅支持insert/update/delete/select四种语句，这四种语句，可任意组合。
4.  导入的数据中，支持/\*!mycat: annotation \*/这种形式的注解，但是不支持/\*\#mycat: annotation \*/这种形式的注解。

## JDBC驱动连接DDM实例<a name="section1690417388176"></a>

```
//以下仅抽取一些关键代码示例行
//不使用负载均衡的连接示例
//String url = "jdbc:mysql://192.168.0.200:5066/db_5133"; 
//使用负载均衡的连接示例
//jdbc:mysql:loadbalance://ip1:port1,ip2:port2..ipN:portN/{db_name}
String url = "jdbc:mysql:loadbalance://192.168.0.200:5066,192.168.0.201:5066/db_5133?loadBalanceAutoCommitStatementThreshold=5&loadBalanceHostRemovalGracePeriod=15000&loadBalanceBlacklistTimeout=60000&loadBalancePingTimeout=5000&retriesAllDown=10&connectTimeout=10000&socketTimeout=60000";
String username = "dbuser01" ;
String password = "xxxxxx" ; 

//加载mysql驱动
com.mysql.jdbc.Driver driver = new com.mysql.jdbc.Driver();
Connection con = DriverManager.getConnection(url , username , password ) ;
//开始执行sql            
Statement stmt = con.createStatement() ; 
ResultSet rs = stmt.executeQuery("select now() as Systemtime");
con.close();
```

-   loadBalanceAutoCommitStatementThreshold：表示执行多少个语句后重新选择连接。

    假设loadBalanceAutoCommitStatementThreshold设为5，则当执行5个sql后（Queries或者updates等），将会重新选择连接。若为0表示“粘性连接，不重新选择连接”。关闭自动提交时（autocommit=false）会等待事务完成再考虑是否重新选择连接。

-   retriesAllDown：当所有的连接地址都无法连接时，轮询重试的最大次数。

    重试次数达到阈值仍然无法获取有效连接，将会抛出SQLException。

-   更多关于jdbc负载均衡模式的配置参数，请参考MySQL官网关于[数据库连接的配置参数介绍](https://dev.mysql.com/doc/connector-j/5.1/en/connector-j-reference-configuration-properties.html)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   **loadBalanceAutoCommitStatementThreshold**和**retriesAllDown**参数必须按照以上样例进行配置，否则在连接切换时可能进入死循环，导致栈溢出。  
    >-   DDM当前暂不支持**useSSL=true**和**useLocalSession**2个参数。  
    >-   建议JDBC驱动版本为5.1.35-5.1.45。  
    >-   MySQL提供的官方连接驱动暂时支持jdbc方式负载均衡，用户如使用其他语言，需自行查找帮助资料，实现负载均衡。  


## sidecar模式负载均衡<a name="section177069583187"></a>

该负载均衡配置方式适合除了java语言以外的语言来访问，如python 、php等。

1.  解压安装程序文件，以“mysql-router-8.0.11-linux-glibc2.12-x86-64bit.tar.gz”版本为例。

    **\[root@mysqlrouter mytmp\]\#  tar -xzvf mysql-router-8.0.11-linux-glibc2.12-x86-64bit.tar.gz**

2.  重命名安装文件夹。

    **\[root@mysqlrouter mytmp\]\#  mv mysql-router-8.0.11-linux-glibc2.12-x86-64bit /usr/local/mysqlrouter**

3.  创建日志和配置相关文件存放目录。

    **\[root@mysqlrouter mytmp\]\# cd /usr/local/mysqlrouter**

    **\[root@mysqlrouter mysqlrouter\]\# mkdir logs**

    **\[root@mysqlrouter mysqlrouter\]\# mkdir etc**

4.  用模板文件创建配置文件。

    **\[root@mysqlrouter mysqlrouter\]\#cp share/doc/mysqlrouter/sample\_mysqlrouter.conf ./etc/mysqlrouter.conf**

    以下提供两种方式，建议应用与MyRouter部署在同一节点，使用Unix sockets连接，以增加安全性和提高访问效率。

    -   使用Unix sockets

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >APP与Router部署在同一节点，基于安全和高效性考虑，可将绑定IP改为127.0.0.1（vi etc/mysqlrouter.conf）或注释配置项**bind\_address**，只用socket进行连接。  

        ```
        [DEFAULT]
        logging_folder = /usr/local/mysqlrouter/log/
        plugin_folder = /usr/local/mysqlrouter/lib/mysqlrouter/
        config_folder = /usr/local/mysqlrouter/etc/
        runtime_folder = /usr/local/mysqlrouter/run/
         
        [logger]
        level = INFO
         
        # 负载均衡配置
        [routing:balancing]
        # 绑定的IP端口
        # bind_address = 0.0.0.0:7002
        bind_address = 127.0.0.1:7002
        socket = /tmp/mysqlrouter.sock
        # 连接超时时间（秒）
        connect_timeout = 3
        # 最大连接数
        max_connections = 100
        # 后端服务器地址.默认读进行轮询
        destinations = 192.168.4.235:5066,192.168.4.231:5066
        # 路由策略
        routing_strategy=round-robin
         
        [keepalive]
        interval = 60
        ```

        其中，**destinations**从DDM管理控制台，DDM实例详情中的连接地址获取。

        连接实例如下：

        ```
        [root@xxx ]# ./mysql -uddmtest -p -S /tmp/mysqlrouter.sock
        Enter password:
         
        mysql>
        ```

    -   使用IP和端口

        **vi /usr/local/mysqlrouter/etc/mysqlrouter.conf**

        ```
        [DEFAULT]
        logging_folder = /usr/local/mysqlrouter/log/
        plugin_folder = /usr/local/mysqlrouter/lib/mysqlrouter/
        config_folder = /usr/local/mysqlrouter/etc/
        runtime_folder = /usr/local/mysqlrouter/run/
         
        [logger]
        level = INFO
         
        # 负载均衡配置
        [routing:balancing]
        # 绑定的IP地址
        bind_address=0.0.0.0
        # 监听的端口
        bind_port = 7002
        # 连接超时时间（秒）
        connect_timeout = 3
        # 最大连接数
        max_connections = 100
        # 后端服务器地址.默认读进行轮询
        destinations = 192.168.4.235:5066,192.168.4.231:5066
        # 路由策略
        routing_strategy=round-robin
         
        [keepalive]
        interval = 60
        ```

        连接示例如下：

        ```
        [root@xxx ]# ./mysql -uddmtest -h128.11.2.2 -P7002 -p
        Enter password:
         
        mysql>
        ```

        其中**128.11.2.2**为Mysql Router所在IP。

5.  启动mysql router。

    **\[root@mysqlrouter mysqlrouter\]\# cd bin**

    **\[root@mysqlrouter bin\]\# ./mysqlrouter -c /usr/local/mysqlrouter/etc/mysqlrouter.conf &**

6.  连接验证。

    python连接示例：

    ```
    import mysql.connector
    import time
    import traceback
    # connection = mysql.connector.Connect(host="128.11.2.2", user="ddmtest", passwd="123456", port=7002)
    connection = mysql.connector.Connect(user="ddmtest", passwd="123456", unix_socket="/tmp/mysqlrouter.sock")
    cursor = connection.cursor()
    for num in range(0, 10):
        try:
            cursor.execute("use db_demo")
            cursor.execute("insert into t_demo(col1) values('haha');")
            cursor.execute("select * from t_demo; ")
            rows = cursor.fetchall()
            for row in rows:
                print row[1]
            time.sleep(0.1)
        except Exception, e:
            print traceback.print_exc()
            if not connection.is_connected():
                connection.reconnect(10, 1)
    cursor.close()
    connection.close()
    ```


## PHP驱动连接<a name="section1773918484207"></a>

1.  安装mysqlnd\_ms拓展（仅负载均衡需要安装此拓展）。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >支持php7.0以上版本的mysqlnd\_ms拓展需要在github上下载，下载地址为：[https://github.com/sergiotabanelli/mysqlnd\_ms](https://github.com/sergiotabanelli/mysqlnd_ms)。  

2.  在php.ini文件中添加如下配置。

    ```
    ;启用mysqli拓展
    extension=php_mysqli.dll 
    ;添加mysqlnd_ms拓展以及进行相关配置（以下信息仅负载均衡需要进行配置）
    extension = /your-php-path/php7/lib/php/extensions/no-debug-non-zts-20131226/mysqlnd_ms.so
    ;启用mysqlnd_ms拓展
    mysqlnd_ms.enable=1
    ;关联负载均衡相关配置文件
    mysqlnd_ms.config_file=/your-config-path/lb_only_for_DDM_cluster.ini
    ;启用多写多读DDM集群
    mysqlnd_ms.multi_master=1
    ;关闭mysqlnd_ms拓展的读写分离
    mysqlnd_ms.disable_rw_split=1
    ```

3.  配置lb\_only\_for\_DDM\_cluster.ini文件。

    ```
    {
    	"myapp": {
    		"master": {
    			"master_0": {
    			        "host": "XXX.XXX.XXX.XXX",
    			        "port": "5066"
    			},
    			"master_1": {
    			        "host": "XXX.XXX.XXX.XXX",
    			        "port": "5066"
    			}
    		},
    		"slave": {
    			
    		},
                    "failover": {"strategy": "loop_before_master" },
                    "filters": {            
                        "random": {                
                            "weights": {                    
                                "master_0":2,                    
                                "master_1":1                
                             }            
                         }        
                     }
    	}
    }
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   为了支持多读多写，因此需要将slave设置为空。  
    >-   当前故障处理模式设置为loop\_before\_master，当访问的节点故障时会自动遍历下一个节点。  
    >-   当前负载均衡策略使用的是random weights策略，在filters中设置为random，在weights中设置每一个节点访问的权重，此策略在访问一定的次数后，master\_0与master\_1访问次数的比例为2:1。  
    >-   连接地址信息您可以在实例管理页面实例连接地址栏获取。  

4.  连接示例。

    ```
    <?php
        $loadbalanceconfig = "myapp"
        $servername = "XXX.XXX.XXX.XXX";
        $username = "dbuser01";
        $password = "xxxxxx";
        $dbname = "db_name";
        $port = "5066";
        //非负载均衡创建连接
        //$conn = new mysqli($servername, $username, $password, $dbname, $port);
        //负载均衡创建连接
        $conn = new mysqli($loadbalanceconfig, $username, $password, $dbname);
     
        $sql = "select now() as Systemtime";
        $result = $conn->query($sql);
     
        $conn->close();
    ?>
    ```


