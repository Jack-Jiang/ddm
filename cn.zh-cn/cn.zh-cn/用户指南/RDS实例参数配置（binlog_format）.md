# RDS实例参数配置（binlog\_format）<a name="ddm_04_0021"></a>

DDM在导入RDS时会将**binlog\_format**设置为**row**，表示将binlog记录成每一行数据被修改的形式，包括修改前和修改后的数据。

建议不要对该参数进行修改，否则可能影响您的正常使用。

