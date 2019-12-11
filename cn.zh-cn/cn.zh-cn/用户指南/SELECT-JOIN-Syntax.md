# SELECT JOIN Syntax<a name="ddm-08-0010"></a>

## 前提条件<a name="section538373852615"></a>

跨分片的JOIN语句，须开通参数support\_complex\_sql，即将其状态设置为“ON”。

>![](public_sys-resources/icon-note.gif) **说明：**   
>support\_complex\_sql为隐藏参数，如需开通请联系技术人员。  

## 常用语法<a name="section1470113220458"></a>

table\_references:

```
table_reference [, table_reference] ...
```

table\_reference:

```
table_factor | join_table
```

table\_factor:

```
tbl_name [[AS] alias]
| table_subquery [AS] alias
| ( table_references )
```

join\_table:

```
table_reference [INNER | CROSS] JOIN table_factor [join_condition]
| table_reference {LEFT|RIGHT} [OUTER] JOIN table_reference join_condition
| table_reference [{LEFT|RIGHT} [OUTER]] JOIN table_factor
```

join\_condition:

```
ON conditional_expr
| USING (column_list)
```

## 语法限制<a name="section18123141258"></a>

不支持SELECT STRAIGHT\_JOIN 和 NATURAL JOIN。

## 示例<a name="section1236614481944"></a>

```
select id,name from test1 where id=1;
select distinct id,name from test1 where id>=1;
select id,name from test1 order by id limit 2 offset 2;
select id,name from test1 order by id limit 2,2;
select  1+1,'test',id,id*1.1,now() from test1 limit 3;
select  current_date,current_timestamp;
select abs(sum(id)) from test1;
```

