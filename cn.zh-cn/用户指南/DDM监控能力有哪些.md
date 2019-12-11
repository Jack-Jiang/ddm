# DDM监控能力有哪些<a name="ddm_04_0002"></a>

DDM当前提供云监控查看指标和DDM管理控制台监控管理的能力，您可以根据监控结果对数据库进行调优，保障性能。

## 云监控<a name="section20613161434516"></a>

云监控提供DDM实例节点的监控，可查看指标如[表1](#table16486135553411)所示，您可以配置告警规则。

**表 1**  云监控指标

<a name="table16486135553411"></a>
<table><thead align="left"><tr id="row24871155173413"><th class="cellrowborder" valign="top" width="24%" id="mcps1.2.3.1.1"><p id="p1048725543411"><a name="p1048725543411"></a><a name="p1048725543411"></a>监控参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="76%" id="mcps1.2.3.1.2"><p id="p18487145515343"><a name="p18487145515343"></a><a name="p18487145515343"></a>监控参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row104872550343"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p6487205518347"><a name="p6487205518347"></a><a name="p6487205518347"></a>CPU使用率</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p124871655103417"><a name="p124871655103417"></a><a name="p124871655103417"></a>用于统计数据面core的CPU利用率。</p>
</td>
</tr>
<tr id="row4487555143410"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p548717556342"><a name="p548717556342"></a><a name="p548717556342"></a>内存使用率</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p17621143811368"><a name="p17621143811368"></a><a name="p17621143811368"></a>用于统计数据面core的内存使用率。</p>
</td>
</tr>
<tr id="row348785593410"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p14487105511340"><a name="p14487105511340"></a><a name="p14487105511340"></a>网络输入吞吐量</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p048755514349"><a name="p048755514349"></a><a name="p048755514349"></a>用于统计数据面core平均每秒的输入流量。</p>
</td>
</tr>
<tr id="row1748717552346"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p548719554343"><a name="p548719554343"></a><a name="p548719554343"></a>网络输出吞吐量</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1248795543420"><a name="p1248795543420"></a><a name="p1248795543420"></a>用于统计数据面core平均每秒的输出流量。</p>
</td>
</tr>
<tr id="row859315537367"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p968213446421"><a name="p968213446421"></a><a name="p968213446421"></a>连接数</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p16292118134317"><a name="p16292118134317"></a><a name="p16292118134317"></a>用于统计数据面服务core的连接数。</p>
</td>
</tr>
<tr id="row13661115413615"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p1357414524219"><a name="p1357414524219"></a><a name="p1357414524219"></a>请求数</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p52921812439"><a name="p52921812439"></a><a name="p52921812439"></a>用于统计数据面服务core的每秒请求数。</p>
</td>
</tr>
<tr id="row44735683614"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p7430246174219"><a name="p7430246174219"></a><a name="p7430246174219"></a>慢SQL数</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p10292198114313"><a name="p10292198114313"></a><a name="p10292198114313"></a>用于统计数据面服务core的慢SQL条数。</p>
</td>
</tr>
<tr id="row022485719365"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p12804184710423"><a name="p12804184710423"></a><a name="p12804184710423"></a>读占比</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p7292198124315"><a name="p7292198124315"></a><a name="p7292198124315"></a>用于统计每个DDM节点的总体的读写比例。</p>
</td>
</tr>
</tbody>
</table>

## DDM管理控制台监控管理<a name="section92691519204516"></a>

管理控制台提供了对DDM实例的监控管理，包括读占比查看与慢SQL查看，用户可以根据监控反馈结果，对数据库进行调优。

1.  登录管理控制台。
2.  在导航上选择“数据库 \> 分布式数据库中间件”，进入总览页面。
3.  单击左侧菜单栏的“DDM实例管理”，进入“DDM实例管理”页面。
4.  选择需要操作的实例，单击右边操作栏“更多 \> 查看监控”链接，进入实例监控管理页面。

