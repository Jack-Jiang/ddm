# DDM控制台显示的RDS实例名称/ID和RDS控制台显示的RDS实例名称/ID为什么不同<a name="ddm_04_0024"></a>

DDM基于RDS的OpenAPI，RDS实例名称/ID为导入RDS时从RDS获取的RDS实例名称/ID，DDM显示的RDS实例名称采用RDS实例名称加后缀方式命名，RDS实例名称/ID可在RDS的“查看监控”中查阅。

例如：

RDS上的实例名称为"rds-infopq"（[图1](#fig374412437449)），对应DDM上显示的RDS实例名称为“rds-infopq\_node0”（[图3](#fig0641132618474)）。

DDM上显示的RDS实例名称/ID（[图3](#fig0641132618474)），与RDS“查看监控”中的节点名称/ID（[图2](#fig16941907468)）相对应。

## RDS实例ID<a name="section11527133223217"></a>

在RDS管理控制台，左侧导航单击“实例管理”，[图1](#fig374412437449)红框所示即为RDS实例ID。

**图 1**  RDS实例名称/ID<a name="fig374412437449"></a>  
![](figures/RDS实例名称-ID.png "RDS实例名称-ID")

## RDS节点名称/ID<a name="section1692053653217"></a>

在RDS管理控制台，在任一实例右操作列选择“更多 \> 查看监控”，并在左侧导航选择“关系型数据库”。

[图2](#fig16941907468)中红框所示即为RDS节点名称/ID。

**图 2**  RDS节点名称/ID<a name="fig16941907468"></a>  
![](figures/RDS节点名称-ID.png "RDS节点名称-ID")

## DDM实例名称/ID<a name="section254554116327"></a>

DDM中的RDS实例名称/ID（[图3](#fig0641132618474)）为实例名称所对应的RDS节点名称/ID（[图2](#fig16941907468)）。

**图 3**  DDM实例名称/ID<a name="fig0641132618474"></a>  
![](figures/DDM实例名称-ID.png "DDM实例名称-ID")

