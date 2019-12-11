# YYYYMM\_OPT算法<a name="ddm_10_0009"></a>

## 适用场景<a name="section15760711132611"></a>

适用于需要按年份与月份进行分库的场景。

## 使用说明<a name="section1877171510217"></a>

-   拆分键的数据类型必须是DATE / DATETIME / TIMESTAMP其中之一。
-   具有相应的操作权限才可以使用，您可以联系客服人员申请。

>![](public_sys-resources/icon-note.gif) **说明：**   
>该算法的路由方式在分库拆分算法上与YYYYMM相同，在分表拆分算法上则不同。具体请参见后续推出的分表拆分算法。  

## 路由方式<a name="section149331275411"></a>

根据拆分键的时间值的年份与月份计算哈希值，然后再按分库数取余。例如，YYYYMM\_OPT\(‘2018-12-31 12:12:12’\) 等价于 \(2018 \* 12 + 12\) % D（D是分库数目）。

## 建表语法<a name="section83236412181"></a>

```
create table yyyymm_opt_tb( 
    id int, 
    name varchar(30) DEFAULT NULL, 
    create_time datetime DEFAULT NULL, 
update_time datetime DEFAULT NULL,
    primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by YYYYMM_OPT(create_time)
tbpartition by YYYYMM_OPT(update_time) tbpartitions 12;
```

## 注意事项<a name="section121681236151812"></a>

-   拆分键和键值皆不能修改。
-   YYYYMM\_OPT算法不支持对于每一个年月都独立对应一张分库。
-   当月份经历一个轮回（如 2013-03 是 2012-03 的一个轮回）后，同一个月份有可能被路由到同一个分库，请以实际的分库数目而定。

