# 修改DDM实例信息<a name="ddm_03_0002"></a>

## 操作场景<a name="section139065085018"></a>

DDM支持修改实例基本信息。

## 前提条件<a name="section480975545018"></a>

已创建实例，且实例状态处于“运行中”。

## 操作步骤<a name="section146041511508"></a>

1.  登录管理控制台。
2.  在导航上选择“数据库 \> 分布式数据库中间件”，进入总览页面。
3.  单击左侧菜单栏的“DDM实例管理”，进入“DDM实例管理”页面。
4.  单击DDM实例名称，进入实例基本信息页面。
5.  选择需要修改的参数，单击参数后的修改键，详情如[表1](#table18919230125211)所示。

    **表 1**  修改实例信息

    <a name="table18919230125211"></a>
    <table><thead align="left"><tr id="row129191430145211"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.3.1.1"><p id="p59191230135210"><a name="p59191230135210"></a><a name="p59191230135210"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="79%" id="mcps1.2.3.1.2"><p id="p18919113055216"><a name="p18919113055216"></a><a name="p18919113055216"></a>修改说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row291993035211"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p10919030125216"><a name="p10919030125216"></a><a name="p10919030125216"></a>实例名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p146093813198"><a name="p146093813198"></a><a name="p146093813198"></a>DDM实例的名称。</p>
    <a name="ul166099812197"></a><a name="ul166099812197"></a><ul id="ul166099812197"><li>名称不能为空。</li><li>只能以英文字母开头。</li><li>长度为4到64位的字符串。</li><li>仅包含英文字母、数字和中划线（-）。<div class="note" id="note4225748566"><a name="note4225748566"></a><a name="note4225748566"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p0226194145613"><a name="p0226194145613"></a><a name="p0226194145613"></a>实例名称修改后，“费用中心”中涉及实例名称的地方都会同步刷新。</p>
    </div></div>
    </li></ul>
    </td>
    </tr>
    <tr id="row18919630195213"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p159191330105220"><a name="p159191330105220"></a><a name="p159191330105220"></a>维护时间窗口</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p39199300524"><a name="p39199300524"></a><a name="p39199300524"></a>在配置的时间段内，服务运维可以对该实例的节点进行维护操作，维护期间业务可以正常使用，可能会发生闪断，但很快会自动恢复正常，维护操作并非频繁发生（通常几个月一次）。</p>
    </td>
    </tr>
    <tr id="row20919330135212"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p491919302522"><a name="p491919302522"></a><a name="p491919302522"></a>描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p1461014818198"><a name="p1461014818198"></a><a name="p1461014818198"></a>对DDM实例的描述信息。长度不超过256个字符。</p>
    </td>
    </tr>
    </tbody>
    </table>


