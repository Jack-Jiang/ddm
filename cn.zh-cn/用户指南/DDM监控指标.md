# DDM监控指标<a name="zh-cn_topic_0205209631"></a>

## 功能说明<a name="section12730145515814"></a>

本节定义了分布式数据库中间件服务上报云监控的监控指标的命名空间，监控指标列表和维度定义，您可以通过云监控提供的API接口来检索DDM产生的监控指标信息。

## 命名空间<a name="section4132551608"></a>

SYS.DDM

## 监控指标<a name="section14105162914016"></a>

<a name="table16486135553411"></a>
<table><thead align="left"><tr id="row24871155173413"><th class="cellrowborder" valign="top" width="14.038596140385962%" id="mcps1.1.7.1.1"><p id="p7726935313"><a name="p7726935313"></a><a name="p7726935313"></a>指标</p>
</th>
<th class="cellrowborder" valign="top" width="12.898710128987101%" id="mcps1.1.7.1.2"><p id="p1048725543411"><a name="p1048725543411"></a><a name="p1048725543411"></a>指标名称</p>
</th>
<th class="cellrowborder" valign="top" width="32.516748325167484%" id="mcps1.1.7.1.3"><p id="p18487145515343"><a name="p18487145515343"></a><a name="p18487145515343"></a>含义</p>
</th>
<th class="cellrowborder" valign="top" width="10.108989101089891%" id="mcps1.1.7.1.4"><p id="p494162813554"><a name="p494162813554"></a><a name="p494162813554"></a>取值范围</p>
</th>
<th class="cellrowborder" valign="top" width="13.86861313868613%" id="mcps1.1.7.1.5"><p id="p149411328155515"><a name="p149411328155515"></a><a name="p149411328155515"></a>测量对象和监控对象</p>
</th>
<th class="cellrowborder" valign="top" width="16.56834316568343%" id="mcps1.1.7.1.6"><p id="p13942142820551"><a name="p13942142820551"></a><a name="p13942142820551"></a>监控周期（原始指标）</p>
</th>
</tr>
</thead>
<tbody><tr id="row104872550343"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p172703512118"><a name="p172703512118"></a><a name="p172703512118"></a><span>cpu_usage</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p6487205518347"><a name="p6487205518347"></a><a name="p6487205518347"></a>CPU使用率</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p124871655103417"><a name="p124871655103417"></a><a name="p124871655103417"></a>该指标用于统计数据面虚拟机的CPU利用率。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p18942142825511"><a name="p18942142825511"></a><a name="p18942142825511"></a>0~100%</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p1494262812559"><a name="p1494262812559"></a><a name="p1494262812559"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p18942122865512"><a name="p18942122865512"></a><a name="p18942122865512"></a>1分钟</p>
</td>
</tr>
<tr id="row4487555143410"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p3727173510118"><a name="p3727173510118"></a><a name="p3727173510118"></a><span>memory_usage</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p548717556342"><a name="p548717556342"></a><a name="p548717556342"></a>内存使用率</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p17621143811368"><a name="p17621143811368"></a><a name="p17621143811368"></a>该指标用于统计数据面虚拟机的内存使用率。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p1094292835517"><a name="p1094292835517"></a><a name="p1094292835517"></a>0~100%</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p1794292820550"><a name="p1794292820550"></a><a name="p1794292820550"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p894242814552"><a name="p894242814552"></a><a name="p894242814552"></a>1分钟</p>
</td>
</tr>
<tr id="row348785593410"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p1772715351119"><a name="p1772715351119"></a><a name="p1772715351119"></a><span>net_in_throughput</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p14487105511340"><a name="p14487105511340"></a><a name="p14487105511340"></a>网络输入吞吐量</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p048755514349"><a name="p048755514349"></a><a name="p048755514349"></a>该指标用于统计数据面虚拟机平均每秒的输入流量。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p1894232812552"><a name="p1894232812552"></a><a name="p1894232812552"></a>≥ 0 bytes/s</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p14942192865510"><a name="p14942192865510"></a><a name="p14942192865510"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p994292813555"><a name="p994292813555"></a><a name="p994292813555"></a>1分钟</p>
</td>
</tr>
<tr id="row1748717552346"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p1272715351115"><a name="p1272715351115"></a><a name="p1272715351115"></a><span>net_out_throughput</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p548719554343"><a name="p548719554343"></a><a name="p548719554343"></a>网络输出吞吐量</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p1248795543420"><a name="p1248795543420"></a><a name="p1248795543420"></a>该指标用于统计数据面虚拟机平均每秒的输出流量。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p119421428115510"><a name="p119421428115510"></a><a name="p119421428115510"></a>≥ 0 bytes/s</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p1794212815510"><a name="p1794212815510"></a><a name="p1794212815510"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p394272813557"><a name="p394272813557"></a><a name="p394272813557"></a>1分钟</p>
</td>
</tr>
<tr id="row7680154464217"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p9727135317"><a name="p9727135317"></a><a name="p9727135317"></a><span>connections</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p968213446421"><a name="p968213446421"></a><a name="p968213446421"></a>连接数</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p16292118134317"><a name="p16292118134317"></a><a name="p16292118134317"></a>该指标用于统计数据面服务Core的连接数。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p19942192845517"><a name="p19942192845517"></a><a name="p19942192845517"></a>≥ 0 counts</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p594216283557"><a name="p594216283557"></a><a name="p594216283557"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p2094216285555"><a name="p2094216285555"></a><a name="p2094216285555"></a>1分钟</p>
</td>
</tr>
<tr id="row18574184516429"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p2072716352013"><a name="p2072716352013"></a><a name="p2072716352013"></a><span>requests</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p1357414524219"><a name="p1357414524219"></a><a name="p1357414524219"></a>QPS</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p52921812439"><a name="p52921812439"></a><a name="p52921812439"></a>该指标用于统计数据面服务Core的每秒请求数。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p994292816553"><a name="p994292816553"></a><a name="p994292816553"></a>≥ 0 counts</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p15944162845517"><a name="p15944162845517"></a><a name="p15944162845517"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p1944202825512"><a name="p1944202825512"></a><a name="p1944202825512"></a>1分钟</p>
</td>
</tr>
<tr id="row543019467425"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p1072715351815"><a name="p1072715351815"></a><a name="p1072715351815"></a><span>slow_SQL</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p7430246174219"><a name="p7430246174219"></a><a name="p7430246174219"></a>慢SQL</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p10292198114313"><a name="p10292198114313"></a><a name="p10292198114313"></a>该指标用于统计数据面服务core的慢SQL条数，详见<a href="#table6617217154212">表1</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p15944142855512"><a name="p15944142855512"></a><a name="p15944142855512"></a>≥ 0 counts</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p1944192855515"><a name="p1944192855515"></a><a name="p1944192855515"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p39471928105517"><a name="p39471928105517"></a><a name="p39471928105517"></a>1分钟</p>
</td>
</tr>
<tr id="row1980474774214"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p1072713514118"><a name="p1072713514118"></a><a name="p1072713514118"></a><span>read_write_ratio</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p12804184710423"><a name="p12804184710423"></a><a name="p12804184710423"></a>读占比</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p7292198124315"><a name="p7292198124315"></a><a name="p7292198124315"></a>该指标用于统计每个DDM节点读请求的个数与写请求的个数比例，详见<a href="#table06152175427">表2</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p119474286555"><a name="p119474286555"></a><a name="p119474286555"></a>0-100%</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p15947162885511"><a name="p15947162885511"></a><a name="p15947162885511"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p494719288550"><a name="p494719288550"></a><a name="p494719288550"></a>1分钟</p>
</td>
</tr>
<tr id="row1825514505617"><td class="cellrowborder" valign="top" width="14.038596140385962%" headers="mcps1.1.7.1.1 "><p id="p19727193518119"><a name="p19727193518119"></a><a name="p19727193518119"></a><span>rt_avg</span></p>
</td>
<td class="cellrowborder" valign="top" width="12.898710128987101%" headers="mcps1.1.7.1.2 "><p id="p925718501760"><a name="p925718501760"></a><a name="p925718501760"></a>平均响应时延</p>
</td>
<td class="cellrowborder" valign="top" width="32.516748325167484%" headers="mcps1.1.7.1.3 "><p id="p225745013615"><a name="p225745013615"></a><a name="p225745013615"></a>该指标用于统计数据面服务Core的SQL平均响应时延。</p>
</td>
<td class="cellrowborder" valign="top" width="10.108989101089891%" headers="mcps1.1.7.1.4 "><p id="p12947152885519"><a name="p12947152885519"></a><a name="p12947152885519"></a>≥ 0 ms</p>
</td>
<td class="cellrowborder" valign="top" width="13.86861313868613%" headers="mcps1.1.7.1.5 "><p id="p10948162810550"><a name="p10948162810550"></a><a name="p10948162810550"></a>DDM节点</p>
</td>
<td class="cellrowborder" valign="top" width="16.56834316568343%" headers="mcps1.1.7.1.6 "><p id="p8948162819558"><a name="p8948162819558"></a><a name="p8948162819558"></a>1分钟</p>
</td>
</tr>
</tbody>
</table>

**表 1**  慢SQL监控

<a name="table6617217154212"></a>
<table><thead align="left"><tr id="row1261615173421"><th class="cellrowborder" valign="top" width="24%" id="mcps1.2.3.1.1"><p id="p861681716429"><a name="p861681716429"></a><a name="p861681716429"></a>监控参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="76%" id="mcps1.2.3.1.2"><p id="p761614172429"><a name="p761614172429"></a><a name="p761614172429"></a>监控参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row106161172425"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p19616141714212"><a name="p19616141714212"></a><a name="p19616141714212"></a>DDM账号</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1261601794220"><a name="p1261601794220"></a><a name="p1261601794220"></a>执行慢SQL的DDM账号。</p>
</td>
</tr>
<tr id="row14616111794215"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p161671712427"><a name="p161671712427"></a><a name="p161671712427"></a>逻辑库</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p166161817174214"><a name="p166161817174214"></a><a name="p166161817174214"></a>实例逻辑库名称。</p>
</td>
</tr>
<tr id="row9616171794218"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p961601784213"><a name="p961601784213"></a><a name="p961601784213"></a>SQL</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1161617177429"><a name="p1161617177429"></a><a name="p1161617177429"></a>DDM实例上执行时长比较耗时的慢SQL语句。</p>
</td>
</tr>
<tr id="row1961610176422"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p1561611178427"><a name="p1561611178427"></a><a name="p1561611178427"></a>开始执行时间</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p16161117154212"><a name="p16161117154212"></a><a name="p16161117154212"></a>选择的时间范围内第一条业务慢SQL语句开始执行的时间。</p>
</td>
</tr>
<tr id="row16616317174213"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p196168173426"><a name="p196168173426"></a><a name="p196168173426"></a>执行时长</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p15616171712429"><a name="p15616171712429"></a><a name="p15616171712429"></a>单位：ms。</p>
</td>
</tr>
<tr id="row3616121734219"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p2616817174216"><a name="p2616817174216"></a><a name="p2616817174216"></a>分片</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p961631764215"><a name="p961631764215"></a><a name="p961631764215"></a>SQL执行涉及的所有分片。</p>
</td>
</tr>
<tr id="row1361710177428"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p361651744211"><a name="p361651744211"></a><a name="p361651744211"></a>影响行</p>
</td>
<td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p11617151710427"><a name="p11617151710427"></a><a name="p11617151710427"></a>SQL执行涉及的行数。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  读占比监控

<a name="table06152175427"></a>
<table><thead align="left"><tr id="row561417179422"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.3.1.1"><p id="p1461416172422"><a name="p1461416172422"></a><a name="p1461416172422"></a>监控参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="78%" id="mcps1.2.3.1.2"><p id="p1861451715425"><a name="p1861451715425"></a><a name="p1861451715425"></a>监控参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row19614317124211"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.3.1.1 "><p id="p18614181734217"><a name="p18614181734217"></a><a name="p18614181734217"></a>逻辑库</p>
</td>
<td class="cellrowborder" valign="top" width="78%" headers="mcps1.2.3.1.2 "><p id="p2614191719428"><a name="p2614191719428"></a><a name="p2614191719428"></a>实例逻辑库名称。</p>
</td>
</tr>
<tr id="row56147177427"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.3.1.1 "><p id="p1661411724211"><a name="p1661411724211"></a><a name="p1661411724211"></a>逻辑表</p>
</td>
<td class="cellrowborder" valign="top" width="78%" headers="mcps1.2.3.1.2 "><p id="p4614121754213"><a name="p4614121754213"></a><a name="p4614121754213"></a>逻辑表名称，读占比监控以逻辑表为单位，统计一段时间内的事务操作次数。</p>
</td>
</tr>
<tr id="row206141917124210"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.3.1.1 "><p id="p6614817124219"><a name="p6614817124219"></a><a name="p6614817124219"></a>读次数</p>
</td>
<td class="cellrowborder" valign="top" width="78%" headers="mcps1.2.3.1.2 "><p id="p1261431794217"><a name="p1261431794217"></a><a name="p1261431794217"></a>对该逻辑表的读操作次数。您可在界面上选择指定时间段进行查询和统计。</p>
</td>
</tr>
<tr id="row12615161744212"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.3.1.1 "><p id="p12614917114215"><a name="p12614917114215"></a><a name="p12614917114215"></a>写次数</p>
</td>
<td class="cellrowborder" valign="top" width="78%" headers="mcps1.2.3.1.2 "><p id="p126151417174214"><a name="p126151417174214"></a><a name="p126151417174214"></a>对该逻辑表的写操作次数。您可在界面上选择指定时间段进行查询和统计。</p>
</td>
</tr>
<tr id="row1362991223814"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.3.1.1 "><p id="p1463014121386"><a name="p1463014121386"></a><a name="p1463014121386"></a>读占比</p>
</td>
<td class="cellrowborder" valign="top" width="78%" headers="mcps1.2.3.1.2 "><p id="p4630151215386"><a name="p4630151215386"></a><a name="p4630151215386"></a>读请求的个数与写请求的个数之间的比例。</p>
</td>
</tr>
<tr id="row561531720422"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.3.1.1 "><p id="p76151817174211"><a name="p76151817174211"></a><a name="p76151817174211"></a>关联表</p>
</td>
<td class="cellrowborder" valign="top" width="78%" headers="mcps1.2.3.1.2 "><p id="p1861517174423"><a name="p1861517174423"></a><a name="p1861517174423"></a>如果读操作涉及到关联查询操作，关联表名称一起显示。</p>
</td>
</tr>
<tr id="row20615131718428"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.3.1.1 "><p id="p1261561754210"><a name="p1261561754210"></a><a name="p1261561754210"></a>最后执行时间</p>
</td>
<td class="cellrowborder" valign="top" width="78%" headers="mcps1.2.3.1.2 "><p id="p14615181718426"><a name="p14615181718426"></a><a name="p14615181718426"></a>选择的时间范围内最后一条业务SQL语句的执行时间。</p>
</td>
</tr>
</tbody>
</table>

## 维度<a name="section198057249316"></a>

<a name="table37373500320"></a>
<table><thead align="left"><tr id="row673810501330"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p821512111541"><a name="p821512111541"></a><a name="p821512111541"></a>Key</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p154175811312"><a name="p154175811312"></a><a name="p154175811312"></a>Value</p>
</th>
</tr>
</thead>
<tbody><tr id="row1373815507314"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17728647413"><a name="p17728647413"></a><a name="p17728647413"></a>ddm_node_id</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p97286413418"><a name="p97286413418"></a><a name="p97286413418"></a>DDM节点</p>
</td>
</tr>
</tbody>
</table>

