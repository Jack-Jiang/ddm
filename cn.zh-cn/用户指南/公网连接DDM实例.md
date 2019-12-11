# 公网连接DDM实例<a name="ddm_02_0006"></a>

公网连接DDM实例，方便开发人员在本地搭建开发或测试环境，提高开发效率。正式环境请通过VPC内连接方式访问DDM实例，保障访问效率。

公网连接DDM实例的安全性是基于Stunnel客户端加密连接，将访问请求转发到DDM实例。

>![](public_sys-resources/icon-note.gif) **说明：**   
>Stunnel推荐版本为4.56，服务端Stunnel安装和证书生成由服务端在绑定公网IP时自动完成，本章介绍Windows和Linux版Stunnel客户端安装。  

## 前提条件<a name="section1502270695932"></a>

-   已有DDM实例，且实例状态为“运行中”。
-   DDM实例已开启公网访问功能，如果访问DDM实例需要使用证书，可以在实例开启公网访问功能后下载证书。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >实例规格变更时会自动关闭公网访问功能，需要您再次打开公网访问开关才能继续使用。  

-   DDM实例安全组需要配置了正确的规则（允许36379端口被外部地址访问），才能正常连接DDM实例。

## Stunnel客户端安装配置（Windows版）<a name="section1280845895932"></a>

1.  <a name="li74761644131012"></a>查看并获取待连接DDM实例的弹性IP地址。

    可在DDM管理控制台“DDM实例管理”页面单击DDM实例名称，进入实例基本信息页面。

2.  下载Stunnel安装包。

    从[http://www.stunnel.org/downloads.html](http://www.stunnel.org/downloads.html)下载Windows版Stunnel安装包（以exe结尾的安装包，例如，stunnel-4.56-win32-installer.exe）到本地Windows设备。

3.  运行Stunnel安装程序，安装Stunnel客户端。
4.  <a name="li11161015556"></a>配置Stunnel客户端。打开Stunnel后，在“Configuration“下单击“Edit Configuration”，新增如下配置内容，然后保存退出。

    ```
    [ddm-client]
    client = yes
    CAfile = D:\tmp\ddm\ddm-ca.crt
    accept = 127.0.0.1:8000
    connect = {弹性IP地址}:{端口}
    ```

    以下参数需要根据说明修改，其他参数不用修改：

    -   ****client****值固定填yes，表示为Stunnel客户端。
    -   **CAfile**为CA证书路径，可选。如果需要，可以进入到DDM实例详情页面下载该证书；如果不需要，可不配置，删除此参数。
    -   **accept**为Stunnel监听地址端口，自定义。
    -   **connect**为Stunnel转发地址与端口，此处填弹性IP地址，即[1](#li74761644131012)中获取的弹性IP地址，端口固定为36379。

5.  打开Stunnel后，在“Configuration“下单击“Reload Configuration“。
6.  打开命令提示符工具**cmd.exe**，执行以下命令，查看127.0.0.1:8000是否已经被监听。

    其中，127.0.0.1:8000为[4](#li11161015556)中accept字段配置的Stunnel监听地址端口。

    **netstat -an |find "8000"**

    返回列表行中显示有“127.0.0.1:8000”，状态为“LISTENING”，表示stunnel客户端正常运行。

7.  连接DDM。

    例如：

    MySQL客户端直连DDM弹性IP端口：

    ```
    mysql -hxxx.xxx.xxx.xxx -P5066 -uinfopq -Ddb_pq -p
    ```

    其中IP和端口为DDM控制台实例详情页面显示的弹性IP和端口。

    使用Stunnel客户端转发：

    ```
    mysql -h127.0.0.1 -P8000 -uinfopq -Ddb_pq -p
    ```

    其中IP和端口为[4](#li11161015556)配置的**accept**的值（当关闭SSL安全访问时，不支持该方式连接DDM）**。**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >使用JDBC驱动、sidecar模式和PHP驱动负载均衡模式连接时，只配置单地址即可，即“127.0.0.1:8000”。  


## Stunnel客户端安装配置（Linux版）<a name="section66391559191819"></a>

1.  <a name="li115231654173717"></a>查看并获取待连接DDM实例的弹性IP地址。

    可在DDM管理控制台“DDM实例管理”页面单击DDM实例名称，进入实例基本信息页面。

2.  登录本地Linux设备。
3.  安装stunnel客户端。

    这里主要介绍Stunnel客户端的几种常见安装方法。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >推荐使用apt和yum两种安装方式，常见Linux系统，一般至少支持其中一种。  

    1.  apt-get方式安装。apt-get管理deb格式的软件包，适用于Debian类操作系统，如Ubuntu。命令如下：

        **apt install stunnel**  或**apt-get install stunnel**

        如果命令执行后提示找不到Stunnel，可以尝试执行**apt update**，更新配置后再安装Stunnel。

    2.  yum方式安装。管理rpm格式的软件包，适用于Fedora、CentOS、Red Hat等操作系统。

        **yum install stunnel**

    3.  其他通用方式安装。Unix系统还可以直接[下载Stunnel安装包](https://www.stunnel.org/downloads.html)，编译后安装。前提是需要安装gcc编译环境，以及[openssl-devel](https://pkgs.org/download/openssl-devel)工具。

        下载并解压Stunnel后，进入解压目录，执行以下命令编译和安装：

        **./configure;**

        **make && make install;**

4.  安装成功后，编辑/etc/default/stunnel4，将参数ENABLED设置为1。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >不同的Linux系统版本，配置文件名称可能有差异，可在/etc/default/路径下查找该文件。  

    ```
    ... 
    ENABLED=1
    ...
    ```

5.  打开配置文件。

    stunnel配置文件名为：stunnel.conf。配置文件可以存储在任何路径，在Stunnel启动的时候指定改配置文件即可。

    也可以按照Stunnel默认的方式新增配置文件：

    1.  apt-get方式

        路径为/etc/stunnel/stunnel.conf，如果路径不存在或者路径下无配置文件，可新增。

    2.  yum方式

        默认路径为/usr/local/stunnel/stunnel.conf，如果路径不存在或者路径下无配置文件，可新增。

    3.  其他通用方式

        路径为/usr/local/stunnel/stunnel.conf，如果路径不存在或者路径下无配置文件，可新增。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果不确定配置文件应该存储在哪，可以在安装后直接输入stunnel命令，获取文件路径提示。  

6.  <a name="li650512191335"></a>在配置文件中新增如下内容，然后保存退出。

    ```
    debug = 4
    output = /var/log/stunnel.log
    sslVersion = all
    [ddm-client]
    client = yes
    accept = 127.0.0.1:8000
    connect = {弹性IP地址}:{端口}
    CAfile = /etc/stunnel/ddm-ca.crt
    ```

    以下参数需要根据说明修改，其他参数不用修改：

    -   **client**值固定填**yes**，表示为Stunnel客户端。
    -   **CAfile**为CA证书路径，可选。如果需要，可以进入到DDM实例详情页面下载该证书；如果不需要，可不配置，删除此参数。
    -   **accept**为Stunnel监听地址端口。
    -   **connect**为Stunnel转发地址与端口，此处填弹性IP地址，即[1](#li115231654173717)中获取的弹性IP地址，端口固定为36379。

7.  启动stunnel服务。

    1.  使用了stunnel默认配置文件，则直接执行命令：

        **stunnel**

    2.  自定义配置文件的路径，则执行命令：

        **stunnel /\{customdir\}/stunnel.conf**

        其中/\{customdir\}/stunnel.conf为自定义存储路径。

    3.  Ubuntu还可以使用** service stunnel4 start **或者**systemctl start stunnel4**。Stunnel4.x的版本，服务/进程名为stunnel4。

    启动后可执行**ps -ef|grep stunnel**确认进程是否正常运行。

8.  执行以下命令，查看127.0.0.1:8000是否已经被监听。

    其中，127.0.0.1:8000为[6](#li650512191335)中accept字段配置的Stunnel监听地址端口。

    **netstat -plunt |grep 8000|grep "LISTEN"**

    返回列表行中显示有“127.0.0.1:8000”，表示stunnel客户端正常运行。

9.  连接DDM。

    例如：

    MySQL客户端直连DDM弹性IP端口：

    ```
    mysql -hxxx.xxx.xxx.xxx -P5066 -uinfopq -Ddb_pq -p
    ```

    其中IP和端口为DDM控制台实例详情页面显示的弹性IP和端口。

    使用Stunnel客户端转发：

    ```
    mysql -h127.0.0.1 -P8000 -uinfopq -Ddb_pq -p
    ```

    其中IP和端口为[6](#li650512191335)配置的**accept**的值（当关闭SSL安全访问时，不支持该方式连接DDM）**。**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >使用JDBC驱动、sidecar模式和PHP驱动负载均衡模式连接时，只配置单地址即可，即“127.0.0.1:8000”。  


