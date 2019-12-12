# SELECT UNION Syntax<a name="ddm-08-0011"></a>

## 前提条件<a name="section559217156110"></a>

须开通参数support\_complex\_sql，即将其状态设置为“ON”。

>![](public_sys-resources/icon-note.gif) **说明：**   
>support\_complex\_sql为隐藏参数，如需开通请联系技术人员。  

## 常用语法<a name="section0452113243813"></a>

```
SELECT ...UNION [ALL | DISTINCT] 
SELECT ...[UNION [ALL | DISTINCT] SELECT ...]
```

## 示例<a name="section9756736185817"></a>

```
select userid from user union select orderid from ordertbl order by userid;
select userid from user union (select orderid from ordertbl group by orderid) order by userid;
```

## 语法限制<a name="section1277220401952"></a>

对于UNION中的每个SELECT，不支持使用多个同名的列，如下：

-   暂不支持\# SELECT 中存在重复的列名；
-   **SELECT** **id**,  **id**,  **name** **FROM_ _**_t1_ **UNION** **SELECT** _pk, pk, _**name FROM**_ t2。_

