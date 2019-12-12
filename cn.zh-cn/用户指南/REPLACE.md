# REPLACE<a name="ddm-08-0007"></a>

REPLACE用于往表中插入行或替换表中的行。

## 常用语法<a name="section1995564111172"></a>

```
replace into table(col1,col2,col3)
values(value1,value2,value3)
```

## 语法限制<a name="section250413125338"></a>

当自增表格ID不存在时，使用REPLACE将会插入一条指定ID的数据，但不会自动生成ID。

