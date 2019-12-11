# DDL<a name="ddm-08-0003"></a>

DDM支持通用的DDL操作：建库，建表，修改表结构等，但实现方式与普通的MySQL数据库有所区别。

## 支持的DDL<a name="section9752355145117"></a>

**表 1**  支持的DDL操作

<a name="tee8dfc90a76349a3b892c58bbe7f7c0a"></a>
<table><thead align="left"><tr id="r28caa04b19d748a3b9a45a2530e2be05"><th class="cellrowborder" valign="top" width="20.82%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0077295631_p221657144616"><a name="zh-cn_topic_0077295631_p221657144616"></a><a name="zh-cn_topic_0077295631_p221657144616"></a>DDL</p>
</th>
<th class="cellrowborder" valign="top" width="25.019999999999996%" id="mcps1.2.5.1.2"><p id="a89da2358b2f14f4ab5f856bdb5e61930"><a name="a89da2358b2f14f4ab5f856bdb5e61930"></a><a name="a89da2358b2f14f4ab5f856bdb5e61930"></a>分片表</p>
</th>
<th class="cellrowborder" valign="top" width="29.160000000000004%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0077295631_p7226572465"><a name="zh-cn_topic_0077295631_p7226572465"></a><a name="zh-cn_topic_0077295631_p7226572465"></a>全局表</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0077295631_p9223579466"><a name="zh-cn_topic_0077295631_p9223579466"></a><a name="zh-cn_topic_0077295631_p9223579466"></a>单表</p>
</th>
</tr>
</thead>
<tbody><tr id="r04365e0461114ff9aa2f79b760752a87"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0077295631_p5224573468"><a name="zh-cn_topic_0077295631_p5224573468"></a><a name="zh-cn_topic_0077295631_p5224573468"></a>CREATE DATABASE Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><p id="a4d3f4ff3befe4961b217d3202a1481b4"><a name="a4d3f4ff3befe4961b217d3202a1481b4"></a><a name="a4d3f4ff3befe4961b217d3202a1481b4"></a>支持在DDM console执行。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0077295631_p12224571468"><a name="zh-cn_topic_0077295631_p12224571468"></a><a name="zh-cn_topic_0077295631_p12224571468"></a>支持在DDM&nbsp;console执行。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0077295631_p922125716467"><a name="zh-cn_topic_0077295631_p922125716467"></a><a name="zh-cn_topic_0077295631_p922125716467"></a>支持在DDM&nbsp;console执行。</p>
</td>
</tr>
<tr id="rba16e0f762d544aebb8c6506fd38cae5"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0077295631_p022175715466"><a name="zh-cn_topic_0077295631_p022175715466"></a><a name="zh-cn_topic_0077295631_p022175715466"></a>DROP DATABASE Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><p id="a29704940f4bf428bb60c3ac15adc916e"><a name="a29704940f4bf428bb60c3ac15adc916e"></a><a name="a29704940f4bf428bb60c3ac15adc916e"></a>支持在DDM&nbsp;console执行。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><p id="ab44731b170464e5cb6a8c203073a63c5"><a name="ab44731b170464e5cb6a8c203073a63c5"></a><a name="ab44731b170464e5cb6a8c203073a63c5"></a>支持在DDM&nbsp;console执行。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0077295631_p19224577467"><a name="zh-cn_topic_0077295631_p19224577467"></a><a name="zh-cn_topic_0077295631_p19224577467"></a>支持在DDM&nbsp;console执行。</p>
</td>
</tr>
<tr id="red33211337454e62b54999c5c1e0eff1"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="aedc290606f22460e97f8ae5c0a68d6f1"><a name="aedc290606f22460e97f8ae5c0a68d6f1"></a><a name="aedc290606f22460e97f8ae5c0a68d6f1"></a>CREATE TABLE Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><a name="ul15842129113216"></a><a name="ul15842129113216"></a><ul id="ul15842129113216"><li>支持在DDM&nbsp;console执行。</li><li>支持通过MySQL客户端连接到DDM执行。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><a name="ul1531701915204"></a><a name="ul1531701915204"></a><ul id="ul1531701915204"><li>支持在DDM&nbsp;console执行。</li><li>支持通过MySQL客户端连接到DDM执行。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="a0e5f2235ee464a7d854be2f752d650e3"><a name="a0e5f2235ee464a7d854be2f752d650e3"></a><a name="a0e5f2235ee464a7d854be2f752d650e3"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
</tr>
<tr id="r7d05e21ce0544b1db91ebede4d5c0600"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="a60992f78af30457b9e00db46c9046ccf"><a name="a60992f78af30457b9e00db46c9046ccf"></a><a name="a60992f78af30457b9e00db46c9046ccf"></a>DROP TABLE Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><a name="u5c8d02c10d3d4f30bdb5d3ade7afd0a5"></a><a name="u5c8d02c10d3d4f30bdb5d3ade7afd0a5"></a><ul id="u5c8d02c10d3d4f30bdb5d3ade7afd0a5"><li>支持在DDM console执行。</li><li>支持通过MySQL客户端连接到DDM执行。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><a name="u55bb0776d17d42459e77771a092335d2"></a><a name="u55bb0776d17d42459e77771a092335d2"></a><ul id="u55bb0776d17d42459e77771a092335d2"><li>支持在DDM console执行。</li><li>支持通过MySQL客户端连接到DDM执行。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0077295631_p3919111430"><a name="zh-cn_topic_0077295631_p3919111430"></a><a name="zh-cn_topic_0077295631_p3919111430"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
</tr>
<tr id="r3d90c6c005c04f9ebd2bbe92b9ab0aa0"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0077295631_p162212578462"><a name="zh-cn_topic_0077295631_p162212578462"></a><a name="zh-cn_topic_0077295631_p162212578462"></a>CREATE INDEX Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0077295631_p422057134619"><a name="zh-cn_topic_0077295631_p422057134619"></a><a name="zh-cn_topic_0077295631_p422057134619"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><p id="aa3680a7ca650481da6c827fea11a57f4"><a name="aa3680a7ca650481da6c827fea11a57f4"></a><a name="aa3680a7ca650481da6c827fea11a57f4"></a>支持，通过MySQL客户端连接到DDM执行。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="ad064c5db65f94ece986e537d9284c128"><a name="ad064c5db65f94ece986e537d9284c128"></a><a name="ad064c5db65f94ece986e537d9284c128"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
</tr>
<tr id="rfe31fe351bfd4190998ff8520b6484c2"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0077295631_p11221575467"><a name="zh-cn_topic_0077295631_p11221575467"></a><a name="zh-cn_topic_0077295631_p11221575467"></a>DROP INDEX Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0077295631_p151261928317"><a name="zh-cn_topic_0077295631_p151261928317"></a><a name="zh-cn_topic_0077295631_p151261928317"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><p id="a36a3b0c0236f439e80d9bd05b90f840a"><a name="a36a3b0c0236f439e80d9bd05b90f840a"></a><a name="a36a3b0c0236f439e80d9bd05b90f840a"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0077295631_p192295713467"><a name="zh-cn_topic_0077295631_p192295713467"></a><a name="zh-cn_topic_0077295631_p192295713467"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
</tr>
<tr id="r6b82c71d8bec44e5b2c119b62dc39bf8"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0077295631_p122218576462"><a name="zh-cn_topic_0077295631_p122218576462"></a><a name="zh-cn_topic_0077295631_p122218576462"></a>TRUNCATE Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0077295631_p4226575467"><a name="zh-cn_topic_0077295631_p4226575467"></a><a name="zh-cn_topic_0077295631_p4226575467"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><p id="a75eb0e2197ae4bdba5dea011e4ce3ea6"><a name="a75eb0e2197ae4bdba5dea011e4ce3ea6"></a><a name="a75eb0e2197ae4bdba5dea011e4ce3ea6"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0077295631_p32365715467"><a name="zh-cn_topic_0077295631_p32365715467"></a><a name="zh-cn_topic_0077295631_p32365715467"></a>支持通过MySQL客户端连接到DDM执行。</p>
</td>
</tr>
<tr id="r30e51b0edd0e4563ad01a6eeba3a2ef1"><td class="cellrowborder" valign="top" width="20.82%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0077295631_p71481255954"><a name="zh-cn_topic_0077295631_p71481255954"></a><a name="zh-cn_topic_0077295631_p71481255954"></a>ALTER TABLE Syntax</p>
</td>
<td class="cellrowborder" valign="top" width="25.019999999999996%" headers="mcps1.2.5.1.2 "><p id="a7cd261360b73414889699f400cbfc180"><a name="a7cd261360b73414889699f400cbfc180"></a><a name="a7cd261360b73414889699f400cbfc180"></a>只支持修改分片键以外的列的属性。</p>
</td>
<td class="cellrowborder" valign="top" width="29.160000000000004%" headers="mcps1.2.5.1.3 "><p id="ac595d0a3bd8642ae8e8ff7fe7eafa404"><a name="ac595d0a3bd8642ae8e8ff7fe7eafa404"></a><a name="ac595d0a3bd8642ae8e8ff7fe7eafa404"></a>支持修改所有列的属性。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="a58087c11f6a74d4f80b299aafb7f4c6e"><a name="a58087c11f6a74d4f80b299aafb7f4c6e"></a><a name="a58087c11f6a74d4f80b299aafb7f4c6e"></a>支持修改所有列的属性。</p>
</td>
</tr>
</tbody>
</table>

