# YYYYWEEK算法<a name="ddm_10_0008"></a>

## 适用场景<a name="section15760711132611"></a>

适用于需要按年份与一年的周数进行分库的场景。

## 使用说明<a name="section1877171510217"></a>

-   拆分键的数据类型必须是DATE / DATETIME / TIMESTAMP其中之一。
-   具有相应的操作权限才可以使用，您可以联系客服人员申请。

## 路由方式<a name="section149331275411"></a>

根据拆分键的时间值的年份与一年的周数计算哈希值，然后再按分库/表数取余。例如，YYYYWEEK\(‘2018-12-31 12:12:12’\) 等价于 \(2019 \* 54 + 1\) % D（D是分库数目）。

>![](public_sys-resources/icon-note.gif) **说明：**   
>此处“2018-12-31”是2019年第一周。计算公式中“2019\*54”的“54”为固定取值。  

## 建表语法<a name="section83236412181"></a>

```
create table yyyyweek_tb( 
    id int, 
    name varchar(30) DEFAULT NULL, 
    create_time datetime DEFAULT NULL,
update_time datetime DEFAULT NULL, 
    primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by YYYYWEEK(create_time)
tbpartition by YYYYWEEK(update_time) tbpartitions 54;
```

## 注意事项<a name="section121681236151812"></a>

-   拆分键和键值皆不能修改。
-   YYYYWEEK算法不支持对于每一个年周都独立对应一张分库。
-   当周数经历一个轮回（如2013年第一周是2012年第一周的一个轮回）后，相同周数有可能被路由到同一个分库，请以实际的分库数目而定。

