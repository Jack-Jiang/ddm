# MOD\_HASH算法<a name="ddm_10_0002"></a>

## 使用说明<a name="section1877171510217"></a>

-   拆分键的数据类型必须是整数类型（INT, INTEGER, BIGINT, MEDIUMINT, SMALLINT, TINYINT, DECIMAL, NUMERIC）或字符串类型。
-   具有相应的操作权限才可以使用，您可以联系客服人员申请。

## 路由方式<a name="section149331275411"></a>

根据分库键的键值按分库数取余，使用HASH分库但不使用同一个拆分键进行HASH分表时，分库键的键值按分库数取余。如果键值是字符串，则字符串会被计算成哈希值再对分库/表数取余。

例如，MOD\_HASH\('6'\)等价于6 % D（D是分库数目）。

分库和分表使用同一个拆分键进行HASH时，拆分键的键值按总的分表数取余。

例如，有 2 个分库，每个分库 4 张分表，那么 0 库上保存分表 0\~3，1 库上保存分表 4\~7。某个键值为 15，15 % \(2 \* 4\) = 7，所以 15 被分到 1 库的表 7 上。

## 建表语法<a name="section83236412181"></a>

```
create table mod_hash_tb( 
    id int, 
    name varchar(30) DEFAULT NULL, 
    create_time datetime DEFAULT NULL, 
    primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by MOD_HASH(id)
tbpartition by MOD_HASH(name) tbpartitions 6;
```

## 注意事项<a name="section121681236151812"></a>

-   拆分键和键值皆不能修改。
-   MOD\_HASH算法是简单取模，要求拆分列的值自身分布均衡才能保证哈希均衡。

