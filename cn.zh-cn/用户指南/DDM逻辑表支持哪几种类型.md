# DDM逻辑表支持哪几种类型<a name="zh-cn_topic_0073885309"></a>

DDM逻辑表支持分片表、全局表、单表和普通表四种类型。

-   分片表

    DDM实例在RDS实例上创建多个物理库，每一个物理库称为分片，在分片上建立的表，叫分片表（不包括单表和全局表）。数据按照分片规则被分配到不同的分片上，分片上的数据支持分布式并行计算。

-   全局表

    将一些数据量小且更新操作不频繁的数据表，如字典表、配置表等，在所有分片上都存储全量数据，提升JOIN效率，这类表叫全局表。

-   单表

    当表数据量不大，且不需要与分片表进行连接查询时，可以只在DDM的默认分片上建表与存储数据，这类表称为单表。

    单表只能通过MySQL客户端或者应用程序连接逻辑库创建。


-   普通表

    DDM将未配置sharding的表，以单表的形式存储在其中一个默认分片上。


**表 1**  各类型逻辑表创建方法

<a name="table0310181114492"></a>
<table><thead align="left"><tr id="row17311811154914"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.1"><p id="p19196248134920"><a name="p19196248134920"></a><a name="p19196248134920"></a>逻辑库类型</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.2"><p id="p17196154874911"><a name="p17196154874911"></a><a name="p17196154874911"></a>逻辑表类型</p>
</th>
<th class="cellrowborder" valign="top" width="59%" id="mcps1.2.4.1.3"><p id="p12429328163411"><a name="p12429328163411"></a><a name="p12429328163411"></a>建表方法</p>
</th>
</tr>
</thead>
<tbody><tr id="row113112011134915"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p171963487494"><a name="p171963487494"></a><a name="p171963487494"></a>拆分</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p101961248204918"><a name="p101961248204918"></a><a name="p101961248204918"></a>分片表</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top" width="59%" headers="mcps1.2.4.1.3 "><p id="p11615125553415"><a name="p11615125553415"></a><a name="p11615125553415"></a>通过管理控制台创建。</p>
</td>
</tr>
<tr id="row3311131174919"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p161961148174914"><a name="p161961148174914"></a><a name="p161961148174914"></a>拆分</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2019613481498"><a name="p2019613481498"></a><a name="p2019613481498"></a>全局表</p>
</td>
</tr>
<tr id="row2311311174915"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p161961148154919"><a name="p161961148154919"></a><a name="p161961148154919"></a>拆分</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p619617489492"><a name="p619617489492"></a><a name="p619617489492"></a>单表</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top" width="59%" headers="mcps1.2.4.1.3 "><p id="p38011159163415"><a name="p38011159163415"></a><a name="p38011159163415"></a>通过sql客户端或者应用程序直接发起创建请求，建表语句兼容MySQL的CREATE TABLE语法。</p>
</td>
</tr>
<tr id="row103111111496"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p11961848164910"><a name="p11961848164910"></a><a name="p11961848164910"></a>非拆分</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1419674813497"><a name="p1419674813497"></a><a name="p1419674813497"></a>普通表</p>
</td>
</tr>
</tbody>
</table>

