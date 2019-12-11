# 重置DDM账号密码<a name="ddm_03_0013"></a>

## 操作场景<a name="section35183690"></a>

本章节为您介绍如何重置现有DDM账号的密码。

>![](public_sys-resources/icon-note.gif) **说明：**   
>DDM账号密码重置时，您的应用服务需要同时修改JDBC配置。  
>出于安全需要，DDM账号密码被重置后，DDM实例会将该逻辑库的原有连接全部断开。  

## 前提条件<a name="section48217758"></a>

存在DDM账号。

## 操作步骤<a name="section9494452181911"></a>

1.  登录管理控制台。
2.  在导航上选择“数据库 \> 分布式数据库中间件”，进入总览页面。
3.  单击左侧菜单栏的“DDM实例管理”，进入“DDM实例管理”页面。
4.  单击DDM实例名称，进入实例基本信息页面。
5.  在实例基本信息页面，选择“账号管理”选项卡，查看账号管理页面。
6.  选择需要修改的账号，单击右边操作栏的“更多”，选择“重置密码”，进入重置密码页面。

    **表 1**  DDM账号密码修改说明

    <a name="table51979763617"></a>
    <table><thead align="left"><tr id="row14197107193613"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.3.1.1"><p id="p16197157203611"><a name="p16197157203611"></a><a name="p16197157203611"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="78.2%" id="mcps1.2.3.1.2"><p id="p1419715723613"><a name="p1419715723613"></a><a name="p1419715723613"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row131971472361"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p141976715365"><a name="p141976715365"></a><a name="p141976715365"></a>账户名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p2019767113613"><a name="p2019767113613"></a><a name="p2019767113613"></a>DDM账号的名称。不可修改。</p>
    </td>
    </tr>
    <tr id="row181988719369"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p519820763616"><a name="p519820763616"></a><a name="p519820763616"></a>新密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p168709598171"><a name="p168709598171"></a><a name="p168709598171"></a>重新设置逻辑库的密码，密码复杂度要求如下。</p>
    <a name="ul449210258508"></a><a name="ul449210258508"></a><ul id="ul449210258508"><li>长度为8-32个字符</li><li>至少包含三种字符组合：大小写字母、数字、特殊字符`~!@#$%^&amp;*()-_=+\\|[{}];:'\",&lt;.&gt;/?和空格</li><li>能与用户名或倒序的用户名相同</li></ul>
    <div class="note" id="note58704594172"><a name="note58704594172"></a><a name="note58704594172"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p687025991715"><a name="p687025991715"></a><a name="p687025991715"></a>管理控制台用户即为DDM的管理员，所以允许直接重置新密码，而不用输入原密码进行校验。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row2019827193612"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.3.1.1 "><p id="p15832175417379"><a name="p15832175417379"></a><a name="p15832175417379"></a>确认密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.2%" headers="mcps1.2.3.1.2 "><p id="p88321954123711"><a name="p88321954123711"></a><a name="p88321954123711"></a>-</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  填写完相关信息后单击“确定”，完成修改。

