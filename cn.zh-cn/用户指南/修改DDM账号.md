# 修改DDM账号<a name="zh-cn_topic_0051815065"></a>

## 操作场景<a name="section35183690"></a>

本章节为您介绍如何修改现有DDM账号的权限或者与逻辑库的管理关系。

## 前提条件<a name="section48217758"></a>

存在DDM账号。

## 操作步骤<a name="section31306641"></a>

1.  登录管理控制台。
2.  在导航上选择“数据库 \> 分布式数据库中间件”，进入总览页面。
3.  单击左侧菜单栏的“DDM实例管理”，进入“DDM实例管理”页面。
4.  单击DDM实例名称，进入实例基本信息页面。
5.  在实例基本信息页面，选择“账号管理”选项卡，查看账号管理页面。
6.  选择需要修改的账号，单击右边操作栏的“修改”，进入修改页面。

    **表 1**  DDM账号修改说明

    <a name="table51979763617"></a>
    <table><thead align="left"><tr id="row14197107193613"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.3.1.1"><p id="p16197157203611"><a name="p16197157203611"></a><a name="p16197157203611"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="78.2%" id="mcps1.2.3.1.2"><p id="p1419715723613"><a name="p1419715723613"></a><a name="p1419715723613"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row131971472361"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p141976715365"><a name="p141976715365"></a><a name="p141976715365"></a>账号名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p2019767113613"><a name="p2019767113613"></a><a name="p2019767113613"></a>DDM账号的名称。不可修改。</p>
    </td>
    </tr>
    <tr id="row2047310932113"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p1230214107213"><a name="p1230214107213"></a><a name="p1230214107213"></a>账号权限（老实例可见）</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p153025103212"><a name="p153025103212"></a><a name="p153025103212"></a>DDM账号的权限，分为“只读”和“读写”。</p>
    <div class="note" id="note54721358591"><a name="note54721358591"></a><a name="note54721358591"></a><span class="notetitle"> 说明： </span><div class="notebody"><div class="p" id="p18932173513595"><a name="p18932173513595"></a><a name="p18932173513595"></a>老实例：即2018-10-12 21:00之前创建的实例，仅支持通过选择读写和只读权限进行修改，基础/扩展权限不可修改。<a name="ul21941158205013"></a><a name="ul21941158205013"></a><ul id="ul21941158205013"><li>选中“读写”表示拥有基础/扩展权限中所有权限。</li><li>选择“只读”表示拥有的基础权限为SELECT，扩展权限为全表查询。</li></ul>
    </div>
    <p id="p1595993805514"><a name="p1595993805514"></a><a name="p1595993805514"></a>如果老实例想升级支持修改基础权限和扩展权限，请提交工单申请。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row18653192575712"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p6653725115719"><a name="p6653725115719"></a><a name="p6653725115719"></a>基础权限</p>
    </td>
    <td class="cellrowborder" rowspan="2" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p449013825815"><a name="p449013825815"></a><a name="p449013825815"></a>DDM账号的基础权限和扩展权限。</p>
    <p id="p481944154818"><a name="p481944154818"></a><a name="p481944154818"></a>基础权限：CREATE、DROP、ALTER、INDEX、INSERT、DELETE、UPDATE、SELECT</p>
    <p id="p9144443499"><a name="p9144443499"></a><a name="p9144443499"></a>扩展权限：全表查询、全表删除、全表更新。</p>
    <div class="note" id="note1395054815212"><a name="note1395054815212"></a><a name="note1395054815212"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul98144410528"></a><a name="ul98144410528"></a><ul id="ul98144410528"><li>新实例：即2018-10-12 21:00之后创建的实例，仅支持根据需要自定义选择基础权限和扩展权限，默认基础权限为SELECT，扩展权限为全表查询。</li><li>权限配置应该遵循如下原则：<div class="p" id="p16624218150"><a name="p16624218150"></a><a name="p16624218150"></a>请至少选择一个基础权限，且扩展权限对应的基础权限必须选择，对应关系如下：<a name="ul135508474016"></a><a name="ul135508474016"></a><ul id="ul135508474016"><li>“全表查询”对应“SELECT”</li><li>“全表删除”对应“DELETE”</li><li>“全表更新”对应“UPDATE”</li></ul>
    </div>
    </li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row105081017175718"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1550811705712"><a name="p1550811705712"></a><a name="p1550811705712"></a>扩展权限</p>
    </td>
    </tr>
    <tr id="row1771951811132"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p10785201918135"><a name="p10785201918135"></a><a name="p10785201918135"></a>读策略类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p147851719141314"><a name="p147851719141314"></a><a name="p147851719141314"></a>DDM账号的读策略，默认为空，取值范围如下：</p>
    <a name="ul4785219121314"></a><a name="ul4785219121314"></a><ul id="ul4785219121314"><li>全读主</li><li>均衡读</li><li>只读实例均衡</li></ul>
    </td>
    </tr>
    <tr id="row1719715720366"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p6197876361"><a name="p6197876361"></a><a name="p6197876361"></a>关联逻辑库</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p11231164114479"><a name="p11231164114479"></a><a name="p11231164114479"></a>DDM账号与逻辑库关联绑定，下拉列表中显示可关联的逻辑库。</p>
    <p id="p31971172368"><a name="p31971172368"></a><a name="p31971172368"></a>DDM账号只对已关联的逻辑库有访问权限。</p>
    <div class="note" id="note1559411320133"><a name="note1559411320133"></a><a name="note1559411320133"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p16594103210139"><a name="p16594103210139"></a><a name="p16594103210139"></a>关联的逻辑库所关联的RDS实例配置的读策略与DDM账号读策略不一样时，DDM账号配置的“读策略类型”优先级较高。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row181988719369"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p519820763616"><a name="p519820763616"></a><a name="p519820763616"></a>描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p1746114583174"><a name="p1746114583174"></a><a name="p1746114583174"></a>对账号的详细描述。</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  填写完相关信息后单击“确定”，完成修改。

