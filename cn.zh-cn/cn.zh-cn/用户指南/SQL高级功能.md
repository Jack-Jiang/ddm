# SQL高级功能<a name="ddm_03_0036"></a>

**表 1**  SQL高级功能的限制

<a name="table174811126823"></a>
<table><thead align="left"><tr id="zh-cn_topic_0169506650_row185011158101618"><th class="cellrowborder" valign="top" width="18.91%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0169506650_p150105817165"><a name="zh-cn_topic_0169506650_p150105817165"></a><a name="zh-cn_topic_0169506650_p150105817165"></a>SQL高级功能</p>
</th>
<th class="cellrowborder" valign="top" width="81.08999999999999%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0169506650_p950111587165"><a name="zh-cn_topic_0169506650_p950111587165"></a><a name="zh-cn_topic_0169506650_p950111587165"></a>限制条件</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0169506650_row6501115814168"><td class="cellrowborder" valign="top" width="18.91%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0169506650_p1650185810162"><a name="zh-cn_topic_0169506650_p1650185810162"></a><a name="zh-cn_topic_0169506650_p1650185810162"></a>SQL高级功能</p>
</td>
<td class="cellrowborder" valign="top" width="81.08999999999999%" headers="mcps1.2.3.1.2 "><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_ul20319837651"></a><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_ul20319837651"></a><ul id="zh-cn_topic_0169506650_zh-cn_topic_0077295716_ul20319837651"><li>暂不支持Prepare\EXECUTE语法。</li><li>暂不支持用户自定义数据类型、自定义函数。</li><li>暂不支持视图、存储过程、触发器、游标。</li><li>暂不支持 BEGIN…END、LOOP…END LOOP、REPEAT…UNTIL…END REPEAT、WHILE…DO…END WHILE 等复合语句。</li><li>暂不支类似 IF ，WHILE 等流程控制类语句。</li><li>暂不支持的预处理类型：<pre class="codeblock" id="zh-cn_topic_0169506650_cef9bbff750364676a9bea5dc93ce919e"><a name="zh-cn_topic_0169506650_cef9bbff750364676a9bea5dc93ce919e"></a><a name="zh-cn_topic_0169506650_cef9bbff750364676a9bea5dc93ce919e"></a><strong id="zh-cn_topic_0169506650_zh-cn_topic_0077295716_b61444361"><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_b61444361"></a><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_b61444361"></a>PREPARE</strong><span id="zh-cn_topic_0169506650_zh-cn_topic_0077295716_text16128342"><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_text16128342"></a><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_text16128342"></a> Syntax</span></pre>
<pre class="codeblock" id="zh-cn_topic_0169506650_c5ff0a3f6f082447cb47dfdaf3f78be06"><a name="zh-cn_topic_0169506650_c5ff0a3f6f082447cb47dfdaf3f78be06"></a><a name="zh-cn_topic_0169506650_c5ff0a3f6f082447cb47dfdaf3f78be06"></a><strong id="zh-cn_topic_0169506650_zh-cn_topic_0077295716_b31327292"><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_b31327292"></a><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_b31327292"></a>EXECUTE</strong><span id="zh-cn_topic_0169506650_zh-cn_topic_0077295716_text13510176"><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_text13510176"></a><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_text13510176"></a> Syntax</span></pre>
</li><li>不支持在建表语句中，对索引增加COMMENT形式的注释。</li><li>不支持进行用户权限相关的设置。<p id="zh-cn_topic_0169506650_zh-cn_topic_0077295716_p466823514620"><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_p466823514620"></a><a name="zh-cn_topic_0169506650_zh-cn_topic_0077295716_p466823514620"></a>例如grant all on *.* to 'test'@'%' identified by 'test123'等用户权限设置均不支持，请在前台console设置。</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

