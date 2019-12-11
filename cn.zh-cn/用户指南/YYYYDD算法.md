# YYYYDD算法<a name="ddm_10_0007"></a>

## 适用场景<a name="section15760711132611"></a>

适用于需要按年份与一年的天数进行分库的场景。

## 使用说明<a name="section1877171510217"></a>

-   拆分键的数据类型必须是DATE / DATETIME / TIMESTAMP其中之一。
-   具有相应的操作权限才可以使用，您可以联系客服人员申请。

## 路由方式<a name="section149331275411"></a>

根据拆分键的时间值的年份与一年的天数计算哈希值，然后再按分库/表数取余。例如，YYYYDD\(‘2018-12-31 12:12:12’\) 等价于 \(2018 \* 366 + 365\) % D（D是分库数目）。

>![](public_sys-resources/icon-note.gif) **说明：**   
>计算得出“2018-12-31”是 2018 年第 365 天。计算公式中“2018\*366”的“366”为固定取值。  

## 建表语法<a name="section83236412181"></a>

```
create table yyyydd_tb( 
    id int, 
    name varchar(30) DEFAULT NULL, 
    create_time datetime DEFAULT NULL,
update_time datetime DEFAULT NULL, 
    primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by YYYYDD(create_time)
tbpartition by YYYYDD(update_time) tbpartitions 30;
```

## 注意事项<a name="section121681236151812"></a>

-   拆分键和键值皆不能修改。
-   YYYYDD算法不支持对于每一个年天都独立对应一张分库。
-   当日期经历一个轮回（如 2013-03 是 2012-03 的一个轮回）后，同一个日期有可能被路由到同一个分库，请以实际的分库数目而定。

