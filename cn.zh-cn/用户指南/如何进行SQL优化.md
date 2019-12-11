# 如何进行SQL优化<a name="ddm_04_0016"></a>

-   尽量避免使用LEFT JOIN或RIGHT JOIN，建议使用INNER。
-   在使用LEFT或RIGHT JOIN时，ON会优先执行，WHERE条件在最后执行，所以在使用过程中，条件尽可能在ON语句中判断，减少WHERE的执行。
-   尽量少用子查询，改用JOIN，避免大表全表扫描。

