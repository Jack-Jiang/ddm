# 购买DDM实例<a name="zh-cn_topic_0062524589"></a>

分布式数据库中间件运行于虚拟私有云，在购买DDM实例前，需保证有可用的虚拟私有云，并且已配置好子网与安全组。创建虚拟私有云、子网以及安全组的方法，请参见《虚拟私有云用户指南》。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   2018年5月12日之后创建的DDM实例才支持DDM、ECS、RDS同VPC跨子网互通；2018年5月12日之前创建的DDM实例如需支持该功能，请提交[工单申请](https://account.huaweicloud.com/usercenter/?locale=zh-cn#/userindex/customerfeedback)，由华为技术支持人员为您处理。  
>-   DDM本身不涉及用户敏感信息，使用DDM处理数据的目的、范围、处理方式、时限等请遵从当地适用的法律法规。  
>-   为了降低敏感信息的泄露风险，建议您先对敏感信息进行加密，再保存到数据库中。  

## 登录DDM管理控制台<a name="section13131654268"></a>

1.  使用账号登录管理控制台。
2.  在管理控制台左上角选择区域。
3.  在导航上选择“服务列表 \> 数据库 \> 分布式数据库中间件DDM”，进入总览页面。

## 购买DDM实例<a name="section1125791522710"></a>

1.  在右上角单击“购买数据库中间件实例”，进入“购买数据库中间件实例”页面。
2.  配置相关参数，详情请参见[表1](#table2075482652515)。

    **表 1**  参数说明

    <a name="table2075482652515"></a>
    <table><thead align="left"><tr id="row9751102692514"><th class="cellrowborder" valign="top" width="19%" id="mcps1.2.3.1.1"><p id="p675112613254"><a name="p675112613254"></a><a name="p675112613254"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="81%" id="mcps1.2.3.1.2"><p id="p47511726162513"><a name="p47511726162513"></a><a name="p47511726162513"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row167512026132518"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p77513265258"><a name="p77513265258"></a><a name="p77513265258"></a>计费模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p275110266252"><a name="p275110266252"></a><a name="p275110266252"></a>支持“包年/包月”和“按需付费”两种模式，购买后同时支持计费模式互转。</p>
    <a name="ul16899218268"></a><a name="ul16899218268"></a><ul id="ul16899218268"><li>包年/包月：用户选购完服务配置后，可以根据需要设置购买时长，系统会一次性按照购买价格对账户余额进行扣费。</li><li>按需计费：用户选购完服务配置后，无需设置购买时长，系统会根据消费时长对账户余额进行扣费。</li></ul>
    </td>
    </tr>
    <tr id="row1751726122517"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p775122672516"><a name="p775122672516"></a><a name="p775122672516"></a>当前区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p14751152662518"><a name="p14751152662518"></a><a name="p14751152662518"></a>DDM实例所在区域，可根据需要直接切换区域，或者在页面左上角切换区域。</p>
    </td>
    </tr>
    <tr id="row7751142652510"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p117511826132515"><a name="p117511826132515"></a><a name="p117511826132515"></a>可用区</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p157516264254"><a name="p157516264254"></a><a name="p157516264254"></a>可选择的可用区。</p>
    <p id="p1475152672520"><a name="p1475152672520"></a><a name="p1475152672520"></a>当前部分区域支持跨可用区部署，以增强DDM实例高可用性。</p>
    <p id="p14751172614258"><a name="p14751172614258"></a><a name="p14751172614258"></a>DDM以集群的方式部署您的实例，实例至少包含2个节点。如果您的实例需要跨可用区部署，可以选择多个可用区，DDM实例的节点将部署在不同的可用区中。</p>
    <div class="note" id="note45701042194119"><a name="note45701042194119"></a><a name="note45701042194119"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1557054224110"><a name="p1557054224110"></a><a name="p1557054224110"></a>跨可用区部署会产生一定的网络时延，请您综合考虑性能与高可用性，结合实际情况确定是否需要跨可用区部署。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row4753626102519"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p87511726112515"><a name="p87511726112515"></a><a name="p87511726112515"></a>实例规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p0753172642512"><a name="p0753172642512"></a><a name="p0753172642512"></a>DDM实例的规格，具体规格可参考<a href="https://support.huaweicloud.com/productdesc-ddm/zh-cn_topic_0063320865.html" target="_blank" rel="noopener noreferrer">产品规格</a>。</p>
    </td>
    </tr>
    <tr id="row1375302682515"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p575314262251"><a name="p575314262251"></a><a name="p575314262251"></a>实例名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p11753122672515"><a name="p11753122672515"></a><a name="p11753122672515"></a>DDM实例的名称。</p>
    <a name="ul1675322620259"></a><a name="ul1675322620259"></a><ul id="ul1675322620259"><li>名称不能为空。</li><li>只能以英文字母开头。</li><li>长度为4到64位的字符串。</li><li>可包含英文字母、数字和中划线（-）。</li></ul>
    </td>
    </tr>
    <tr id="row445614313295"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p184567319296"><a name="p184567319296"></a><a name="p184567319296"></a>企业项目</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p74563315295"><a name="p74563315295"></a><a name="p74563315295"></a>实例所属的企业项目。单击下拉框可选择一个企业项目。</p>
    </td>
    </tr>
    <tr id="row117531726192510"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p1975316269257"><a name="p1975316269257"></a><a name="p1975316269257"></a>描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p4753202612258"><a name="p4753202612258"></a><a name="p4753202612258"></a>对DDM实例的描述信息。长度不超过256个字符。</p>
    </td>
    </tr>
    <tr id="row1575302622517"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p1775342611257"><a name="p1775342611257"></a><a name="p1775342611257"></a>虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p4753226132519"><a name="p4753226132519"></a><a name="p4753226132519"></a>DDM实例所在的虚拟专用网络，可对不同业务进行网络隔离，方便地管理、配置内部网络，进行安全、快捷的网络变更。</p>
    <p id="p1875342618258"><a name="p1875342618258"></a><a name="p1875342618258"></a>单击“查看虚拟私有云”，系统跳转到虚拟私有云界面，可以查看相应的虚拟私有云，以及安全组的出方向规则和入方向规则。</p>
    </td>
    </tr>
    <tr id="row1775462614254"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p1475314263250"><a name="p1475314263250"></a><a name="p1475314263250"></a>子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p47531326132519"><a name="p47531326132519"></a><a name="p47531326132519"></a>子网名称与子网IP地址段。</p>
    <p id="p3753726202520"><a name="p3753726202520"></a><a name="p3753726202520"></a>应用程序所在的服务器，以及RDS实例物理库所在的服务器，需要与DDM实例所在的弹性云服务器属于相同虚拟私有云。</p>
    </td>
    </tr>
    <tr id="row197543269253"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p1675462615253"><a name="p1675462615253"></a><a name="p1675462615253"></a>安全组</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p4754162613256"><a name="p4754162613256"></a><a name="p4754162613256"></a>已创建的安全组。</p>
    <p id="p275419262254"><a name="p275419262254"></a><a name="p275419262254"></a>建议DDM实例与应用程序、RDS实例选择相同的安全组，三者网络访问不受限制。如果选择了不同的安全组，请注意添加安全组访问规则，开通网络访问。</p>
    </td>
    </tr>
    <tr id="row17754152662519"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p117548262252"><a name="p117548262252"></a><a name="p117548262252"></a>维护时间窗口</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p57541826182517"><a name="p57541826182517"></a><a name="p57541826182517"></a>在配置的时间段内，服务运维可以对该实例的节点进行维护操作，维护期间业务可以正常使用，可能会发生闪断，但很快会自动恢复正常，维护操作并非频繁发生（通常几个月一次）。</p>
    </td>
    </tr>
    <tr id="row1754102612259"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.3.1.1 "><p id="p9754132612514"><a name="p9754132612514"></a><a name="p9754132612514"></a>购买时长</p>
    </td>
    <td class="cellrowborder" valign="top" width="81%" headers="mcps1.2.3.1.2 "><p id="p175462682510"><a name="p175462682510"></a><a name="p175462682510"></a>购买DDM实例的时长。该参数仅当“计费模式”为“包年/包月”时才显示。</p>
    <p id="p8754726202516"><a name="p8754726202516"></a><a name="p8754726202516"></a>您可选择1个月、2个月、3个月、4个月、5个月、6个月、7个月、8个月、9个月和1年。</p>
    <p id="p6552119438"><a name="p6552119438"></a><a name="p6552119438"></a>勾选后实例自动续费，自动续费周期与原订单周期一致。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  填写完上述信息后，单击“立即购买”进入“规格确认”页面。

    页面显示购买的分布式数据库中间件的实例名称和实例规格等信息。

4.  确认信息无误后，勾选协议 ，进行下一步。
    -   如果您选择的是包年/包月付费模式，单击“去支付“按钮；
    -   如果您选择的是按需付费模式，单击“提交“按钮。

5.  创建DDM实例大约需要5分钟\~15分钟，DDM实例创建成功后，您可以在“DDM实例管理”页面，查看并管理自己的DDM实例。

    DDM实例购买完成后，还需要按照本章剩余章节继续操作，完成相关DDM服务配置，才能正常使用DDM服务。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >DDM实例创建成功后，正常情况下“实例状态”为“运行中”，如创建失败：  
    >-   对于“按需付费”模式的实例，可删除DDM实例后重新申请。如果重新申请仍然失败，请联系客服协助处理。  
    >-   对于“包年/包月”模式的实例，请联系客服取消订单。  
    >“包年/包月”模式的实例请遵循以下原则：  
    >-   付款成功后，才会创建DDM实例。  
    >-   包年/包月DDM实例不能直接删除，如需删除请通过“费用中心”的“退订管理”执行资源退订操作。  
    >-   若因选错参数等原因导致所建实例与原计划创建实例不符，可通过“费用中心”的“退订管理”执行资源操作。  
    >-   DDM实例的退订约束遵循“费用中心”中“退订管理”的退订说明。  


