# 变更DDM实例规格<a name="ddm_03_0001"></a>

## 操作场景<a name="section139065085018"></a>

DDM支持对已部署的DDM实例规格进行变更，可对其可用区和规格进行调整。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   请在业务空闲时间段进行规格变更操作，对于“按需付费”类型的实例变更在请求提交后立即执行，对于“包年/包月”类型的实例在付款后立即执行。  
>-   一旦执行后不可撤销变更操作，如果需要修改请在当前变更操作结束后重新提交变更操作。  

## 前提条件<a name="section480975545018"></a>

已创建实例，且实例状态处于“运行中”。

## 操作步骤<a name="section146041511508"></a>

1.  登录管理控制台。
2.  在导航上选择“数据库 \> 分布式数据库中间件”，进入总览页面。
3.  单击左侧菜单栏的“DDM实例管理”，进入“DDM实例管理”页面。
4.  在需要变更的DDM实例右侧操作列，选择“更多 \> 规格变更”。
5.  配置规格变更信息，如[表1](#table9312946102117)所示。

    界面显示当前实例配置，请根据需要配置变更规格。

    **表 1**  规格变更

    <a name="table9312946102117"></a>
    <table><thead align="left"><tr id="row1331218466212"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.3.1.1"><p id="p031219469216"><a name="p031219469216"></a><a name="p031219469216"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="79%" id="mcps1.2.3.1.2"><p id="p931219468213"><a name="p931219468213"></a><a name="p931219468213"></a>修改说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row18312646132115"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p113121462219"><a name="p113121462219"></a><a name="p113121462219"></a>可用区</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p4923409718728"><a name="p4923409718728"></a><a name="p4923409718728"></a>可选择的可用区。</p>
    <p id="p10631718447"><a name="p10631718447"></a><a name="p10631718447"></a>当前部分区域支持跨可用区部署，以增强DDM实例高可用性。</p>
    <p id="p686715919012"><a name="p686715919012"></a><a name="p686715919012"></a>DDM以集群的方式部署您的实例，实例至少包含2个节点。如果您的实例需要跨可用区部署，可以选择复选多个可用区，DDM实例的节点将部署在不同的可用区中。</p>
    <div class="notice" id="note1844948131219"><a name="note1844948131219"></a><a name="note1844948131219"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><p id="p1544916831212"><a name="p1544916831212"></a><a name="p1544916831212"></a>跨可用区部署会产生一定的网络时延，请您综合考虑性能与高可用性，结合实际情况确定是否需要跨可用区部署。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row19312124692111"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p8312646102117"><a name="p8312646102117"></a><a name="p8312646102117"></a>实例规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p8060118"><a name="p8060118"></a><a name="p8060118"></a>DDM实例的规格，核数越多，并行计算能力越强；内存越大，支持更复杂更大批量的数据查询与处理。</p>
    <p id="p12680171010578"><a name="p12680171010578"></a><a name="p12680171010578"></a>您可以根据自己的业务规划选择合适的规格，在满足业务需要的同时降低使用成本。</p>
    </td>
    </tr>
    </tbody>
    </table>

6.  单击“提交”完成规格变更，可在“任务中心”中查看规格变更进度。

