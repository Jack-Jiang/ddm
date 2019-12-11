# UNI\_HASH算法<a name="ddm_10_0003"></a>

## 适用场景<a name="section15760711132611"></a>

适用于需要按用户ID或订单ID进行分库的场景。

## 使用说明<a name="section1877171510217"></a>

-   拆分键的数据类型必须是整数类型（INT, INTEGER, BIGINT, MEDIUMINT, SMALLINT, TINYINT, DECIMAL, NUMERIC）或字符串类型。
-   具有相应的操作权限才可以使用，您可以联系客服人员申请。

## 路由方式<a name="section149331275411"></a>

根据分库键的键值按分库/表数取余。如果键值是字符串，则字符串会被计算成哈希值再对分库/表数取余。例如，UNI\_HASH\('6'\)等价于6 % D（D是分库数目）。

## 建表语法<a name="section83236412181"></a>

```
create table uni_hash_tb( 
    id int, 
    name varchar(30) DEFAULT NULL, 
    create_time datetime DEFAULT NULL, 
    primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by UNI_HASH(ID) 
tbpartition by UNI_HASH(name) tbpartitions 3;
```

## 注意事项<a name="section121681236151812"></a>

-   拆分键和键值皆不能修改。
-   UNI\_HASH算法是简单取模，要求拆分列的值自身分布均衡才能保证哈希均衡。

