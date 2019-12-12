# SELECT<a name="ddm-08-0006"></a>

SELECT通常用于查询一个或多个表中的数据。

## 常用语法<a name="section8559171941216"></a>

```
SELECT
[ALL | DISTINCT | DISTINCTROW ]
select_expr
[, select_expr ...]
[FROM table_references [WHERE where_condition]
[GROUP BY {col_name | expr | position} [ASC | DESC], ...]
[HAVING where_condition] [ORDER BY {col_name | expr | position} [ASC | DESC], ...]
[LIMIT {[offset,] row_count | row_count OFFSET offset}]
```

**表 1**  说明信息

<a name="table123165064115"></a>
<table><thead align="left"><tr id="row13232195034115"><th class="cellrowborder" valign="top" width="33.87%" id="mcps1.2.3.1.1"><p id="p12232205017410"><a name="p12232205017410"></a><a name="p12232205017410"></a>语法</p>
</th>
<th class="cellrowborder" valign="top" width="66.13%" id="mcps1.2.3.1.2"><p id="p10232950184114"><a name="p10232950184114"></a><a name="p10232950184114"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row32321650114111"><td class="cellrowborder" valign="top" width="33.87%" headers="mcps1.2.3.1.1 "><p id="p123210502410"><a name="p123210502410"></a><a name="p123210502410"></a>select_expr</p>
</td>
<td class="cellrowborder" valign="top" width="66.13%" headers="mcps1.2.3.1.2 "><p id="p162322500417"><a name="p162322500417"></a><a name="p162322500417"></a>每个select_expr<span>都指示一个您想要查询的列</span>。</p>
</td>
</tr>
<tr id="row10232350164113"><td class="cellrowborder" valign="top" width="33.87%" headers="mcps1.2.3.1.1 "><p id="p92321850174115"><a name="p92321850174115"></a><a name="p92321850174115"></a>FROM table_references</p>
</td>
<td class="cellrowborder" valign="top" width="66.13%" headers="mcps1.2.3.1.2 "><p id="p19232125016412"><a name="p19232125016412"></a><a name="p19232125016412"></a>指您将从哪个或哪些表中查询。</p>
</td>
</tr>
<tr id="row42321650204114"><td class="cellrowborder" valign="top" width="33.87%" headers="mcps1.2.3.1.1 "><p id="p8232135034115"><a name="p8232135034115"></a><a name="p8232135034115"></a>WHERE</p>
</td>
<td class="cellrowborder" valign="top" width="66.13%" headers="mcps1.2.3.1.2 "><p id="p1232105015411"><a name="p1232105015411"></a><a name="p1232105015411"></a><span>关键词</span><span>WHERE</span><span>其后跟一个表达式，用于表示被选择的行所须满足的条件。</span></p>
</td>
</tr>
<tr id="row523285019412"><td class="cellrowborder" valign="top" width="33.87%" headers="mcps1.2.3.1.1 "><p id="p202321350174119"><a name="p202321350174119"></a><a name="p202321350174119"></a>GROUP BY</p>
</td>
<td class="cellrowborder" valign="top" width="66.13%" headers="mcps1.2.3.1.2 "><p id="p7232125024116"><a name="p7232125024116"></a><a name="p7232125024116"></a><span>语法中被使用的子句将按一定的顺序排列，</span>GROUP BY表示语句间关系，支持列名。如<span>一个</span><span>HAVING</span><span>子句必须位于</span><span>GROUP BY</span><span>子句之后，并在</span><span>ORDER BY</span><span>子句之前。</span></p>
</td>
</tr>
<tr id="row20232750184118"><td class="cellrowborder" valign="top" width="33.87%" headers="mcps1.2.3.1.1 "><p id="p15232115016414"><a name="p15232115016414"></a><a name="p15232115016414"></a>ORDER BY</p>
</td>
<td class="cellrowborder" valign="top" width="66.13%" headers="mcps1.2.3.1.2 "><p id="p023225074110"><a name="p023225074110"></a><a name="p023225074110"></a>语法顺序排列的一种方式，表示语句间关系，支持列名和指定的排序方式（如ASC、 DESC）。</p>
</td>
</tr>
<tr id="row4232175014110"><td class="cellrowborder" valign="top" width="33.87%" headers="mcps1.2.3.1.1 "><p id="p20232155094118"><a name="p20232155094118"></a><a name="p20232155094118"></a>LIMIT/OFFSET</p>
</td>
<td class="cellrowborder" valign="top" width="66.13%" headers="mcps1.2.3.1.2 "><p id="p114501511204313"><a name="p114501511204313"></a><a name="p114501511204313"></a>对输出结果集的偏移量及大小给予约束，如：LIMIT接受一个或者两个数字参数； LIMIT … OFFSET …。</p>
</td>
</tr>
</tbody>
</table>

## 语法限制<a name="section1019017511569"></a>

-   不支持select ... use/ignore index ...；
-   不支持select ... group by ... with rollup；
-   不支持select ... into outfile ...。

