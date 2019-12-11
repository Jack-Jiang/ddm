# 如何选择JDBC驱动方式的版本和参数<a name="ddm_04_0009"></a>

DDM暂不支持使用5.1.46版本的JDBC驱动连接DDM，建议您使用以下版本的JDBC驱动：5.1.35-5.1.45。

JDBC驱动下载地址：[https://dev.mysql.com/doc/index-connectors.html](https://dev.mysql.com/downloads/connector/j/)。

JDBC URL中推荐参数如[表1](#table127264441235)所示。

**表 1**  参数

<a name="table127264441235"></a>
<table><thead align="left"><tr id="row137266445234"><th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.1"><p id="p372644482318"><a name="p372644482318"></a><a name="p372644482318"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="51.839999999999996%" id="mcps1.2.4.1.2"><p id="p57261644192318"><a name="p57261644192318"></a><a name="p57261644192318"></a>参数说明</p>
</th>
<th class="cellrowborder" valign="top" width="29.160000000000004%" id="mcps1.2.4.1.3"><p id="p772644419235"><a name="p772644419235"></a><a name="p772644419235"></a>推荐取值</p>
</th>
</tr>
</thead>
<tbody><tr id="row11726134422316"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p1472684413236"><a name="p1472684413236"></a><a name="p1472684413236"></a>ip:port</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p5726244182318"><a name="p5726244182318"></a><a name="p5726244182318"></a>连接地址和端口，用于连接DDM。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p207261044112316"><a name="p207261044112316"></a><a name="p207261044112316"></a>在DDM管理控制台DDM实例管理中查看连接地址。</p>
</td>
</tr>
<tr id="row10726164411236"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p117266440237"><a name="p117266440237"></a><a name="p117266440237"></a>db_name</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p3726174417235"><a name="p3726174417235"></a><a name="p3726174417235"></a>连接逻辑库名称。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p20726144432315"><a name="p20726144432315"></a><a name="p20726144432315"></a>在DDM管理控制台，DDM实例管理 &gt; 逻辑库管理下查看逻辑库名称。</p>
</td>
</tr>
<tr id="row177272448232"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p47279444235"><a name="p47279444235"></a><a name="p47279444235"></a>loadBalanceAutoCommitStatementThreshold</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p2727044182314"><a name="p2727044182314"></a><a name="p2727044182314"></a>表示连接上执行多少个语句后会重新选择连接。</p>
<a name="ul1499414223287"></a><a name="ul1499414223287"></a><ul id="ul1499414223287"><li>若取值为5，则当执行5个sql后（Queries或者updates等），将会重新选择连接。</li><li>若取值为0，则表示“粘性连接，不重新选择连接”。</li></ul>
<p id="p13640154320295"><a name="p13640154320295"></a><a name="p13640154320295"></a>关闭自动提交时（autocommit=false）会等待事务完成再考虑是否重新选择连接。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p1272711448238"><a name="p1272711448238"></a><a name="p1272711448238"></a>5</p>
</td>
</tr>
<tr id="row1945033917443"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p1545018391442"><a name="p1545018391442"></a><a name="p1545018391442"></a>loadBalanceHostRemovalGracePeriod</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p8450139114417"><a name="p8450139114417"></a><a name="p8450139114417"></a>设置主机从负载均衡连接中移除的宽限时间。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p745083910442"><a name="p745083910442"></a><a name="p745083910442"></a>15000</p>
</td>
</tr>
<tr id="row440418468449"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p64041846154417"><a name="p64041846154417"></a><a name="p64041846154417"></a>loadBalanceBlacklistTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p204042046174416"><a name="p204042046174416"></a><a name="p204042046174416"></a>设置服务器在全局黑名单中存留的时间。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p940454613441"><a name="p940454613441"></a><a name="p940454613441"></a>60000</p>
</td>
</tr>
<tr id="row12890743184419"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p4890134313445"><a name="p4890134313445"></a><a name="p4890134313445"></a>loadBalancePingTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p889344317445"><a name="p889344317445"></a><a name="p889344317445"></a>使用负载均衡连接时，等待每个负载均衡连接ping响应的毫秒数。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p12893243114410"><a name="p12893243114410"></a><a name="p12893243114410"></a>5000</p>
</td>
</tr>
<tr id="row950412598289"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p13505125952816"><a name="p13505125952816"></a><a name="p13505125952816"></a>retriesAllDown</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p5506125916286"><a name="p5506125916286"></a><a name="p5506125916286"></a>当所有的连接地址都无法连接时，轮询重试的最大次数。</p>
<p id="p163824613299"><a name="p163824613299"></a><a name="p163824613299"></a>重试次数达到阈值仍然无法获取有效连接，将会抛出SQLException。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p1950635910289"><a name="p1950635910289"></a><a name="p1950635910289"></a>10</p>
</td>
</tr>
<tr id="row873834583916"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p117381645193920"><a name="p117381645193920"></a><a name="p117381645193920"></a>connectTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p136132530405"><a name="p136132530405"></a><a name="p136132530405"></a>和数据库服务器建立socket连接时的超时。</p>
<p id="p673854533911"><a name="p673854533911"></a><a name="p673854533911"></a>单位：毫秒，0表示永不超时，适用于JDK 1.4及更高版本。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p16738745113918"><a name="p16738745113918"></a><a name="p16738745113918"></a>10000</p>
</td>
</tr>
<tr id="row16571546123914"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.1 "><p id="p1657114653914"><a name="p1657114653914"></a><a name="p1657114653914"></a>socketTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="51.839999999999996%" headers="mcps1.2.4.1.2 "><p id="p89705284411"><a name="p89705284411"></a><a name="p89705284411"></a>socket操作（读写）超时。</p>
<p id="p7571104613917"><a name="p7571104613917"></a><a name="p7571104613917"></a>单位：毫秒， 0表示永不超时</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.4.1.3 "><p id="p25711746183918"><a name="p25711746183918"></a><a name="p25711746183918"></a>根据业务实际情况合理配置。</p>
</td>
</tr>
</tbody>
</table>

