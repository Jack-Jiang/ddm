# DDM不支持复杂SQL时如何处理<a name="ddm_04_0017"></a>

对读写分离等场景，如果某些复杂SQL不支持，可通过注释方式透传到RDS上。

将/\*\* mycat:sql=select 1 \*\*/放在原SQL最开头处，注意最开头处不能有空格。

>![](public_sys-resources/icon-note.gif) **说明：**   
>如果是mysql命令行连接DDM，需要在命令行加上-c，否则mysql客户端会把注释自动去除。  

