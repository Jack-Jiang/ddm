# 场景六：数据从DDM实例导出<a name="ddm_03_0029"></a>

## 场景介绍<a name="section44058561269"></a>

因为业务使用需要，将DDM实例的数据导出成SQL文本文件。

## 导出表结构<a name="section211192517263"></a>

执行以下命令导出表结构。

```
mysqldump -h {DDM_ADDRESS} -P {DDM_PORT} -u {DDM_USER} -p --single-transaction --hex-blob --set-gtid-purged=OFF --no-data --order-by-primary {DB_NAME} {TABLE_NAME} > {mysql_table_schema_ddm.sql}
```

## 导出表数据<a name="section18814132892615"></a>

执行以下命令导出表数据。

```
mysqldump -h {DDM_ADDRESS} -P {DDM_PORT} -u {DDM_USER} -p --single-transaction --hex-blob --complete-insert --set-gtid-purged=OFF --quick --no-create-info --skip-comments [--where=""] {DB_NAME} {TABLE_NAME} > {mysql_table_data_ddm.sql}

```

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   本阶段会在一定程度上影响DDM实例以及RDS实例性能，请选择在业务空闲时间导出。  
>-   为了提高导出数据的效率，对于非拆分库的表可以直连RDS进行导出。  

