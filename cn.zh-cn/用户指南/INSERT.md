# INSERT<a name="ddm-08-0005"></a>

INSERT是将数据插入到数据库对象中的指令。

## 常用语法<a name="section36113533417"></a>

```
INSERT [INTO] tbl_name
[(col_name,...)]
{VALUES | VALUE} ({expr },...),(...),...
[ ON DUPLICATE KEY UPDATE
col_name=expr
[, col_name=expr] ... ]
OR
INSERT [INTO] tbl_name
SET col_name={expr | DEFAULT}, ...
[ ON DUPLICATE KEY UPDATE
col_name=expr [, col_name=expr] ... ]
```

## 语法限制<a name="section1280014191938"></a>

-   对于INSERT... VALUES\(expr\)，不支持expr中含有子查询；
-   不支持INSERT DELAYED...；
-   不支持INSERT... SELECT...；
-   不支持不包含拆分字段的INSERT。

