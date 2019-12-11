# SELECT Subquery Syntax<a name="ddm-08-0012"></a>

## 前提条件<a name="section449518258111"></a>

须开通参数support\_complex\_sql，即将其状态设置为“ON”。

>![](public_sys-resources/icon-note.gif) **说明：**   
>support\_complex\_sql为隐藏参数，如需开通请联系技术人员。  

## The Subquery as Scalar Operand<a name="section15771114685915"></a>

示例

```
SELECT (SELECT id FROM test1 where id=1);         
SELECT (SELECT id FROM test2 where id=1)FROM test1;              
SELECT UPPER((SELECT name FROM test1 limit 1)) FROM test2;
```

## Comparisons Using Subqueries<a name="section14287162151520"></a>

语法

```
non_subquery_operand comparison_operator (subquery)
comparison_operator ：= > < >= <= <> != <=> like
```

示例

```
select name from test1 where id > (select id from test2 where id=1);
select name from test1 where id = (select id from test2 where id=1);
select id from test1 where name like (select name from test2 where id=1);
```

## Subqueries with ANY, IN, NOT IN, SOME,ALL,Exists,NOT Exists<a name="section14597152195810"></a>

语法

```
operand comparison_operator SOME (subquery)
operand comparison_operator ALL (subquery)
operand comparison_operator ANY (subquery) 
operand IN (subquery) 
operand not IN (subquery)
operand exists (subquery)
operand not exists (subquery)
```

示例

```
select id from test1 where id > any (select id from test2);
select id from test1 where id > some (select id from test2);
select id from test1 where id > all (select id from test2);
select id from test1 where id in (select id from test2);
select id from test1 where id not in (select id from test2);
select id from test1 where exists (select id from test2 where id=1);
select id from test1 where not exists (select id from test2 where id=1);
```

## Derived Tables \(Subqueries in the FROM Clause\)<a name="section892675411611"></a>

语法

```
SELECT ... FROM (subquery) [AS] tbl_name ...
```

示例

```
select id from (select id,name from test2 where id>1) a  order by a.id;
```

## 语法限制<a name="section104153553013"></a>

-   Derived Tables 必须拥有一个别名。
-   Derived Tables 不可以成为 Correlated Subqueries，即不能包含子查询外部表的引用。
-   标量子查询在一些场景下当前不能得到正确结果，建议改写为join，同时可提高性能。
-   不支持 HAVING 子句中的子查询，JOIN ON 条件中的子查询。

-   不支持Row Subqueries。
-   不支持关联子查询，可改写为join来支持，同时可提高性能。示例：

```
select id from test1 where name like (select name from test2 where test2.id=test1.id);
改写为
select test1.id from test1,test2 where test1.name like test2.name and test2.id=test1.id;
```

