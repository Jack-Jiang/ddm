# RIGHT\_SHIFT算法<a name="ddm_10_0004"></a>

## 适用场景<a name="section15760711132611"></a>

当拆分键大部分键值的低位部位区分度比较低而高位部分区分度比较高时，则适用于通过此拆分算法提高散列结果的均匀度。

## 使用说明<a name="section1877171510217"></a>

-   拆分键的数据类型必须是整数类型（INT, INTEGER, BIGINT, MEDIUMINT, SMALLINT, TINYINT, DECIMAL, NUMERIC）。
-   具有相应的操作权限才可以使用，您可以联系客服人员申请。

## 路由方式<a name="section149331275411"></a>

根据分库键的键值向右移二进制位（位数由用户通过DDL指定），然后将得到的整数值按分库/表数取余。

## 建表语法<a name="section83236412181"></a>

```
create table right_shift_tb( 
    id int, 
uuid int,
    name varchar(30) DEFAULT NULL, 
    create_time datetime DEFAULT NULL, 
    primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by RIGHT_SHIFT(id,4)
tbpartition by RIGHT_SHIFT(uuid,4) tbpartitions 3;
```

## 注意事项<a name="section121681236151812"></a>

-   拆分键和键值皆不能修改。

