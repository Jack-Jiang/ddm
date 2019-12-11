# 修改RDS读策略<a name="ddm_03_0019"></a>

## 操作场景<a name="section13678125554210"></a>

DDM支持配置RDS读策略。

您可以根据数据读取压力负载情况，合理配置RDS读策略，提高查询性能。

## 前提条件<a name="section169604486320"></a>

已导入RDS实例，且实例状态为“运行中”或“未关联”。

## 操作步骤<a name="section36781455144210"></a>

1.  登录管理控制台。
2.  在导航上选择“数据库 \> 分布式数据库中间件”，进入总览页面。
3.  单击左侧菜单栏的“RDS导入管理”，进入“RDS实例管理”页面。
4.  选择需要修改的RDS实例，单击右边操作栏下的“更多 \> 设置RDS读策略”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   只有实例状态为“运行中”或“未关联”状态才能设置RDS读策略。  
    >-   导入的RDS没有只读实例时，默认策略为“全读主”；有只读实例时，默认策略为“只读实例均衡”。  
    >-   RDS实例导入时没有只读实例（默认为“全读主”），同步RDS信息后增加了只读实例，则策略变为“只读实例均衡”。  
    >-   RDS实例导入时有只读实例（默认为“只读实例均衡”），在RDS控制台删除该RDS所有只读实例后，DDM同步RDS信息后没有只读实例（只读实例全部被移除），则RDS读策略变更为“全读主”。  
    >-   RDS实例导入时有只读实例，同步RDS信息后再次增加只读实例。  
    >    -   同步RDS信息前，如果RDS读策略为“全读主”或“自定义读”，则同步后增加的RDS只读实例相对权重为0。  
    >    -   同步RDS信息前，如果RDS读策略为“均衡读”或“只读实例均衡读”，则同步后增加的RDS只读实例会根据读策略分配相对权重。  

5.  配置参数。
    1.  选择读策略，详细信息如[表1](#table118571152124217)所示。

        **表 1**  读策略详细信息

        <a name="table118571152124217"></a>
        <table><thead align="left"><tr id="row19857205220429"><th class="cellrowborder" valign="top" width="16.48%" id="mcps1.2.6.1.1"><p id="p15857152104210"><a name="p15857152104210"></a><a name="p15857152104210"></a>RDS读策略</p>
        </th>
        <th class="cellrowborder" valign="top" width="20.46%" id="mcps1.2.6.1.2"><p id="p88578520423"><a name="p88578520423"></a><a name="p88578520423"></a>全读主</p>
        </th>
        <th class="cellrowborder" valign="top" width="20.810000000000002%" id="mcps1.2.6.1.3"><p id="p178575522424"><a name="p178575522424"></a><a name="p178575522424"></a>均衡读</p>
        </th>
        <th class="cellrowborder" valign="top" width="20.64%" id="mcps1.2.6.1.4"><p id="p1985713528425"><a name="p1985713528425"></a><a name="p1985713528425"></a>只读实例均衡</p>
        </th>
        <th class="cellrowborder" valign="top" width="21.61%" id="mcps1.2.6.1.5"><p id="p9349342174711"><a name="p9349342174711"></a><a name="p9349342174711"></a>自定义读</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1595014453306"><td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.6.1.1 "><p id="p2950114593013"><a name="p2950114593013"></a><a name="p2950114593013"></a>策略说明</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.46%" headers="mcps1.2.6.1.2 "><p id="p1495044593015"><a name="p1495044593015"></a><a name="p1495044593015"></a>读请求只会分发到主实例上，即关闭读写分离。</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.810000000000002%" headers="mcps1.2.6.1.3 "><p id="p159504452308"><a name="p159504452308"></a><a name="p159504452308"></a>读请求在主实例和只读实例上平均分发。</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.64%" headers="mcps1.2.6.1.4 "><p id="p119501545173014"><a name="p119501545173014"></a><a name="p119501545173014"></a>读请求在只读实例上平均分发，不会分发到主实例上。</p>
        </td>
        <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.6.1.5 "><p id="p1795015450304"><a name="p1795015450304"></a><a name="p1795015450304"></a>读请求根据自定义的相对权重分发到各个实例上。</p>
        </td>
        </tr>
        <tr id="row1685745224211"><td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.6.1.1 "><p id="p6857155254213"><a name="p6857155254213"></a><a name="p6857155254213"></a>适用场景</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.46%" headers="mcps1.2.6.1.2 "><p id="p1285715525427"><a name="p1285715525427"></a><a name="p1285715525427"></a>强一致性读。</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.810000000000002%" headers="mcps1.2.6.1.3 "><p id="p14857252114211"><a name="p14857252114211"></a><a name="p14857252114211"></a>读压力较大时配置读负载均衡，接受数据短时间不一致。</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.64%" headers="mcps1.2.6.1.4 "><p id="p1285714524429"><a name="p1285714524429"></a><a name="p1285714524429"></a>希望读不影响主实例，接受数据短时间不一致。</p>
        </td>
        <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.6.1.5 "><p id="p134913427479"><a name="p134913427479"></a><a name="p134913427479"></a>读压力较大时控制读主的比例，接受数据短时间不一致。</p>
        </td>
        </tr>
        <tr id="row158579520429"><td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.6.1.1 "><p id="p18576529429"><a name="p18576529429"></a><a name="p18576529429"></a>约束限制</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.46%" headers="mcps1.2.6.1.2 "><p id="p178577529428"><a name="p178577529428"></a><a name="p178577529428"></a>无。</p>
        </td>
        <td class="cellrowborder" valign="top" width="20.810000000000002%" headers="mcps1.2.6.1.3 "><a name="ol167103610515"></a><a name="ol167103610515"></a><ol id="ol167103610515"><li>存在只读实例。</li><li>主实例和只读实例允许短时间不一致。</li></ol>
        </td>
        <td class="cellrowborder" valign="top" width="20.64%" headers="mcps1.2.6.1.4 "><a name="ol20930543105110"></a><a name="ol20930543105110"></a><ol id="ol20930543105110"><li>存在只读实例。</li><li>主实例和只读实例允许数据短时间不一致。</li><li>如果只读实例全部故障则临时全读主。</li></ol>
        </td>
        <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.6.1.5 "><a name="ol11258827175216"></a><a name="ol11258827175216"></a><ol id="ol11258827175216"><li>存在只读实例。</li><li>主实例和只读实例允许数据短时间不一致。</li><li>如果只读实例全部故障则临时全读主。</li></ol>
        </td>
        </tr>
        <tr id="row13140105117352"><td class="cellrowborder" colspan="5" valign="top" headers="mcps1.2.6.1.1 mcps1.2.6.1.2 mcps1.2.6.1.3 mcps1.2.6.1.4 mcps1.2.6.1.5 "><div class="note" id="note1982056193520"><a name="note1982056193520"></a><a name="note1982056193520"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ol134881256143517"></a><a name="ol134881256143517"></a><ol id="ol134881256143517"><li>2018-07-05 24:00之前创建的DDM实例，如果RDS有只读实例，仅支持只读实例均衡。</li><li>由于RDS只读实例和主实例之间的数据同步可能存在延迟，从只读实例上读取的可能不是最新的数据，可通过加事务或者hint强制分发到主实例上。</li></ol>
        </div></div>
        </td>
        </tr>
        </tbody>
        </table>

    2.  配置实例相对权重值。

        相对权重：

        -   全读主：读请求分发到该实例的相对权重。
        -   均衡度：读请求分发到该实例的相对权重，均衡读策略相对权重固定为50，读请求在所有实例间平均分发。
        -   只读实例均衡：读请求分发到该实例的相对权重，只读实例均衡，主实例相对权重固定为0，只读实例相对权重固定位50，请求在所有只读实例间平均分发。
        -   自定义读：读请求分发到该实例的相对权重，比如一个主实例和两个只读实例，相对权重分别设置为20、80、100，则读请求分发到主实例的概率为20/\(20+80+100\)%=10%，分发到两个只读实例的概率分别为40%、50%。

        例如：RDS实例A有2个只读实例B和C，读权重如[表2](#table182667371215)所示。

        **表 2**  实例相对权重示例

        <a name="table182667371215"></a>
        <table><thead align="left"><tr id="row9265137925"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p426516371622"><a name="p426516371622"></a><a name="p426516371622"></a>读策略</p>
        </th>
        <th class="cellrowborder" valign="top" width="28.000000000000004%" id="mcps1.2.5.1.2"><p id="p826510371025"><a name="p826510371025"></a><a name="p826510371025"></a>主实例A读相对权重</p>
        </th>
        <th class="cellrowborder" valign="top" width="28.000000000000004%" id="mcps1.2.5.1.3"><p id="p12265437722"><a name="p12265437722"></a><a name="p12265437722"></a>只读实例B相对权重</p>
        </th>
        <th class="cellrowborder" valign="top" width="28.000000000000004%" id="mcps1.2.5.1.4"><p id="p426518371325"><a name="p426518371325"></a><a name="p426518371325"></a>只读实例C相对权重</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row22657378211"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p826518371927"><a name="p826518371927"></a><a name="p826518371927"></a>全读主</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.2 "><p id="p2265163714220"><a name="p2265163714220"></a><a name="p2265163714220"></a>100</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.3 "><p id="p1526519371426"><a name="p1526519371426"></a><a name="p1526519371426"></a>0</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.4 "><p id="p18265937122"><a name="p18265937122"></a><a name="p18265937122"></a>0</p>
        </td>
        </tr>
        <tr id="row1726611371822"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p2026615371129"><a name="p2026615371129"></a><a name="p2026615371129"></a>均衡读</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.2 "><p id="p142661137222"><a name="p142661137222"></a><a name="p142661137222"></a>50</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.3 "><p id="p1526619371727"><a name="p1526619371727"></a><a name="p1526619371727"></a>50</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.4 "><p id="p626610371326"><a name="p626610371326"></a><a name="p626610371326"></a>50</p>
        </td>
        </tr>
        <tr id="row32663372211"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p32661137126"><a name="p32661137126"></a><a name="p32661137126"></a>只读实例均衡</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.2 "><p id="p142661637320"><a name="p142661637320"></a><a name="p142661637320"></a>0</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.3 "><p id="p13266637026"><a name="p13266637026"></a><a name="p13266637026"></a>50</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.4 "><p id="p11266123713212"><a name="p11266123713212"></a><a name="p11266123713212"></a>50</p>
        </td>
        </tr>
        <tr id="row2266037623"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p1266163714215"><a name="p1266163714215"></a><a name="p1266163714215"></a>自定义读</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.2 "><p id="p1726617379217"><a name="p1726617379217"></a><a name="p1726617379217"></a>20</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.3 "><p id="p226618371323"><a name="p226618371323"></a><a name="p226618371323"></a>80</p>
        </td>
        <td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.5.1.4 "><p id="p1826618371724"><a name="p1826618371724"></a><a name="p1826618371724"></a>100</p>
        </td>
        </tr>
        </tbody>
        </table>

6.  确认无误后，单击“确定”，完成RDS读策略设置。

