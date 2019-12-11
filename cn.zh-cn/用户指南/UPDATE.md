# UPDATE<a name="ddm-08-0009"></a>

## 常用语法<a name="section0886140223"></a>

```
UPDATE table_reference
SET col_name1={expr1} [, col_name2={expr2}] ...
[WHERE where_condition]
```

## 语法限制<a name="section13101911638"></a>

-   UPDATE语句中的where\_condition不支持计算表达式及其子查询；
-   不支持limit；
-   不支持同时UPDATE多张表；
-   不支持多表JOIN的UPDATE。

