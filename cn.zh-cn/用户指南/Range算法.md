# Range算法<a name="ddm_10_0013"></a>

## 适用场景<a name="section15760711132611"></a>

适用于范围类操作较多的场景。在SQL查询条件中，使用“\>”、“<”、“BETWEEN ... AND ...”之类运算符相对较多。

## 使用说明<a name="section1877171510217"></a>

拆分键为表字段或表字段+日期函数。若拆分键为表字段+日期函数，其中数据表字段必须是日期类型（DATE / DATETIME / TIMESTAMP），日期函数适用于需要按时间（年、月、日、周及其组合）对数据进行拆分的场景。

## 路由方式<a name="section149331275411"></a>

根据拆分键，按照算法元数据的规则将数据行存储到相应的分片上。

## 建表语法<a name="section83236412181"></a>

```
create table range_tb( 
    id int, 
    name varchar(30) DEFAULT NULL, 
    create_time datetime DEFAULT NULL, 
    primary key(id) 
)ENGINE=InnoDB DEFAULT CHARSET=utf8 
dbpartition by range(month(create_time)) 
{      
    1-2=1,  
    3-4=2,  
    5-6=3,  
    7-8=4,  
    9-10=5,  
    11-12=6,  
    default=7  
};
```

## 注意事项<a name="section121681236151812"></a>

拆分键和键值皆不能修改。

