# RANGE\_HASH算法<a name="ddm_10_0005"></a>

## 适用场景<a name="section15760711132611"></a>

适用于需要有两个拆分键，并且查询时仅有一个拆分键值的场景。

## 使用说明<a name="section1877171510217"></a>

-   拆分键的数据类型必须一致且是字符类型或整数类型（INT, INTEGER, BIGINT, MEDIUMINT, SMALLINT, TINYINT, DECIMAL, NUMERIC）。
-   插入数据时，两个拆分键的后N位请确保一致。
-   字符串必须保证长度不少于N位。
-   具有相应的操作权限才可以使用，您可以联系客服人员申请。

## 路由方式<a name="section149331275411"></a>

当拆分键类型是字符串类型时，根据任一拆分键后 N 位计算哈希值，然后再按分库数\(分表数\)去取余，完成路由计算。当拆分键类型是整型时，根据任一拆分键后 N 位\(不需要计算哈希值\)，然后再按分库数\(分表数\)去取余，完成路由计算。N 为函数第三个参数。

例如：RANGE\_HASH\(COL1, COL2, N\) ，计算时会优先选择 COL1，截取其后 N 位进行计算。 COL1 不存在时找 COL2。

## 建表语法<a name="section83236412181"></a>

```
create table range_hash_tb(
    id int,
    buyer_id varchar(30) DEFAULT NULL,
    order_id varchar(30) DEFAULT NULL,
    create_time datetime DEFAULT NULL,
 primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by RANGE_HASH(buyer_id,order_id,3)
tbpartition by RANGE_HASH(buyer_id,order_id,3) tbpartitions 3;
```

## 注意事项<a name="section121681236151812"></a>

两个拆分键和键值皆不能修改。

