# 使用DDM事务模型有哪些注意事项<a name="ddm_04_0010"></a>

1.  事务补偿仅支持对事务中的insert、update和delete语句的补偿。
2.  事务隔离性在最终原子性下，默认极端情况下会有脏读，可以通过对select加**for update**或者**lock in share mode**避免脏读。
3.  对应autocommit=true时，若单条sql（insert、update、delete等）执行跨了多个分片，请在事务里执行。
4.  对DDL如truncate table等，mysql会隐式提交，无法做到事务一致性，建议单独分开。
5.  **insert into ...on duplicate key update**语句仅支持对唯一主键方式，对联合主键或其他唯一索引导致的update行为不支持，无法保证一致性。

