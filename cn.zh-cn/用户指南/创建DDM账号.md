# 创建DDM账号<a name="ddm_02_0001"></a>

DDM账号用于连接和管理DDM逻辑库。一个DDM实例最多能创建100个DDM账号，一个DDM账号可以关联多个逻辑库。

-   老实例：即2018-10-12 21:00之前创建的实例，权限分为读写和只读两类。
    -   “读写”表示拥有基础/扩展权限中所有权限。
    -   “只读”表示拥有的基础权限为SELECT，扩展权限为全表查询。

-   新实例：即2018-10-12 21:00之后创建的实例，权限分为基础权限和扩展权限，默认基础权限为SELECT，扩展权限为全表查询。
    -   基础权限：CREATE、DROP、ALTER、INDEX、INSERT、DELETE、UPDATE、SELECT。
    -   扩展权限：全表查询、全表删除、全表更新。


如果老实例想升级支持修改基础权限和扩展权限，请提交工单申请。

1.  在DDM管理控制台“DDM实例管理”下单击DDM实例名称，进入实例基本信息页面。
2.  选择“账号管理”选项卡，进入账号管理页面。
3.  单击“创建DDM账号”，填写[表1](#table184114346315)中的DDM账号信息。

    **表 1**  创建DDM账号配置参数

    <a name="table184114346315"></a>
    <table><thead align="left"><tr id="row98391534173115"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.3.1.1"><p id="p15839193411319"><a name="p15839193411319"></a><a name="p15839193411319"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79%" id="mcps1.2.3.1.2"><p id="p38391734183114"><a name="p38391734183114"></a><a name="p38391734183114"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row188411434143117"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p684153453112"><a name="p684153453112"></a><a name="p684153453112"></a>账号名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p7841113416311"><a name="p7841113416311"></a><a name="p7841113416311"></a>DDM账号的名称，命名规则如下。</p>
    <a name="ul1178410712499"></a><a name="ul1178410712499"></a><ul id="ul1178410712499"><li>必须以字母开头</li><li>长度为6~32个字符</li><li>仅包含字母，数字、下划线</li></ul>
    </td>
    </tr>
    <tr id="row98411634103118"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p484173483118"><a name="p484173483118"></a><a name="p484173483118"></a>账号密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p148412034113119"><a name="p148412034113119"></a><a name="p148412034113119"></a>DDM账号的密码，密码复杂度要求如下。</p>
    <a name="ul449210258508"></a><a name="ul449210258508"></a><ul id="ul449210258508"><li>长度为8~32个字符</li><li>至少包含两种字符组合：大小写字母、数字、特殊字符`~!@#$%^&amp;*()-_=+\\|[{}];:'\",&lt;.&gt;/?和空格</li><li>不能与用户名或倒序的用户名相同</li></ul>
    </td>
    </tr>
    <tr id="row1684143463118"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p15841183453111"><a name="p15841183453111"></a><a name="p15841183453111"></a>确认密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p12841183433118"><a name="p12841183433118"></a><a name="p12841183433118"></a>-</p>
    </td>
    </tr>
    <tr id="row0533163934910"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p15352390493"><a name="p15352390493"></a><a name="p15352390493"></a>账号权限（老实例可见）</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p19535139154920"><a name="p19535139154920"></a><a name="p19535139154920"></a>账号的权限。</p>
    <p id="p19201137165014"><a name="p19201137165014"></a><a name="p19201137165014"></a>读写和只读。</p>
    <div class="note" id="note1025976165113"><a name="note1025976165113"></a><a name="note1025976165113"></a><span class="notetitle"> 说明： </span><div class="notebody"><div class="p" id="p117014865118"><a name="p117014865118"></a><a name="p117014865118"></a>老实例：即2018-10-12 21:00之前创建的实例，仅支持通过选择读写和只读权限进行修改，基础/扩展权限不可修改。<a name="ul21941158205013"></a><a name="ul21941158205013"></a><ul id="ul21941158205013"><li>选中“读写”表示拥有基础/扩展权限中所有权限。</li><li>选择“只读”表示拥有的基础权限为SELECT，扩展权限为全表查询。</li></ul>
    </div>
    <p id="p1595993805514"><a name="p1595993805514"></a><a name="p1595993805514"></a>如果老实例想升级支持修改基础权限和扩展权限，请提交工单申请。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row48191417485"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p9819249482"><a name="p9819249482"></a><a name="p9819249482"></a>基础权限</p>
    </td>
    <td class="cellrowborder" rowspan="2" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p10444164416486"><a name="p10444164416486"></a><a name="p10444164416486"></a>账号的基础和扩展权限。</p>
    <p id="p481944154818"><a name="p481944154818"></a><a name="p481944154818"></a>基础权限：CREATE、DROP、ALTER、INDEX、INSERT、DELETE、UPDATE、SELECT</p>
    <p id="p9144443499"><a name="p9144443499"></a><a name="p9144443499"></a>扩展权限：全表查询、全表删除、全表更新。</p>
    <div class="note" id="note1395054815212"><a name="note1395054815212"></a><a name="note1395054815212"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul98144410528"></a><a name="ul98144410528"></a><ul id="ul98144410528"><li>新实例：即2018-10-12 21:00之后创建的实例，仅支持根据需要自定义选择基础权限和扩展权限，默认基础权限为SELECT，扩展权限为全表查询。</li><li>权限配置应该遵循如下原则：<div class="p" id="p13647149135211"><a name="p13647149135211"></a><a name="p13647149135211"></a>请至少选择一个基础权限，且扩展权限对应的基础权限必须选择，对应关系如下：<a name="ul135508474016"></a><a name="ul135508474016"></a><ul id="ul135508474016"><li>“全表查询”对应“SELECT”</li><li>“全表删除”对应“DELETE”</li><li>“全表更新”对应“UPDATE”</li></ul>
    </div>
    </li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row104641811487"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p11464118204816"><a name="p11464118204816"></a><a name="p11464118204816"></a>扩展权限</p>
    </td>
    </tr>
    <tr id="row91094158111"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p18474151615118"><a name="p18474151615118"></a><a name="p18474151615118"></a>读策略类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p2474131610112"><a name="p2474131610112"></a><a name="p2474131610112"></a>DDM账号的读策略，默认为空，取值范围如下：</p>
    <a name="ul1474816131119"></a><a name="ul1474816131119"></a><ul id="ul1474816131119"><li>全读主</li><li>均衡读</li><li>只读实例均衡</li></ul>
    <div class="note" id="note1437611162114"><a name="note1437611162114"></a><a name="note1437611162114"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p3476181613117"><a name="p3476181613117"></a><a name="p3476181613117"></a>当选择“均衡读”或“只读实例均衡”时，如果RDS没有只读实例或只读实例全部故障，则会选择读主实例。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row784103413111"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p684143418318"><a name="p684143418318"></a><a name="p684143418318"></a>关联逻辑库</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p78418343314"><a name="p78418343314"></a><a name="p78418343314"></a>DDM账号与逻辑库关联绑定，下拉列表中显示可关联的逻辑库。</p>
    <p id="p08411134123118"><a name="p08411134123118"></a><a name="p08411134123118"></a>DDM账号只对已关联的逻辑库有访问权限。</p>
    <div class="note" id="note62291145161113"><a name="note62291145161113"></a><a name="note62291145161113"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p822984591112"><a name="p822984591112"></a><a name="p822984591112"></a>关联的逻辑库所关联的RDS实例配置的读策略与DDM账号读策略不一样时，DDM账号配置的“读策略类型”优先级较高。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row14841143403119"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p1084163493116"><a name="p1084163493116"></a><a name="p1084163493116"></a>描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p1184116343318"><a name="p1184116343318"></a><a name="p1184116343318"></a>对DDM账号的详细描述信息。</p>
    <p id="p78411434193115"><a name="p78411434193115"></a><a name="p78411434193115"></a>长度不能超过256个字符。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“确定”完成创建DDM账号。

