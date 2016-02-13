<!DOCTYPE.md>
.md xmlns="http://www.w3.org/1999/...md" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text.md; charset=utf-8" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>CSDN及人人网的用户密码分析 - 编程随想的博客</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="回到首页">CSDN及人人网的用户密码分析</a></h1>
<div class="post-info"><span class="date-header">2011-12-24</span><a href="../../tags/IT.md" class="tag">IT</a> <a href="../../tags/IT.E4BFA1E681AFE5AE89E585A8.md" class="tag">IT.信息安全</a> </div>
<hr>
<div class="post">
本周，互联网上的一大新闻就是：多个知名网站被脱库，上千万用户资料侧漏。对俺这种长期在安全圈混的人，自然最关心泄漏出来的用户口令啦。这可是活生生的第一手材料啊。今天正好周末，俺就抽空分析了一下CSDN和RenRen的用户密码。毕竟这两个网站名气大，CSDN可以代表技术人员的圈子，人人网的用户据说高校学生居多。考虑到俺博客的读者不少，或许有些人热衷于网络安全，没准也对密码分析感兴趣，干脆就把分析结果分享到博客上。<!--program-think--><br /><br />　　对于CSDN被泄露的600多万用户数据，俺多罗嗦几句：<br />　　据CSDN官方的说法，这仅仅是2009年的数据。不过，据圈内的小道消息，其实黑客拿到了所有用户数据，这次只是公布了其中一部分。俺查了一下公布的数据，里面没有俺的帐号——可是俺 program_think 这个帐号在2009年1月份就在CSDN注册了。另外，里面也没有刘未鹏同学的帐号（pongba）——他更加是CSDN的老用户了。而有些网友是2010年注册的帐号，却出现在公布的数据中。所以，CSDN官方的说法很可疑。<br /><br /><h2>★样本的说明</h2><br />　　CSDN的样本，总共是3列数据，分别是用户名、口令、邮箱。格式比较严谨，所有数据都可用。数据量大约是642万8千。<br />　　RenRen的样本，总共2列，分别是用户名（同时也是邮箱）和口令。此样本的格式不太严谨。俺去掉了大约3万无效数据（比如用户名不是合法的邮箱地址），还剩大约473万5千。<br /><br /><h2>★密码长度分布</h2><br /><table border="1" cellspacing="0"><tbody><tr><th>长度范围</th><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>[1,6]</td><td>1.92</td><td>31.89</td></tr><tr><td>[7,12]</td><td>90.80</td><td>65.86</td></tr><tr><td>[13,18]</td><td>7.17</td><td>1.70</td></tr><tr><td>[19, ]</td><td>0.21</td><td>0.55</td></tr></tbody></table><br /><br /><table border="1" cellspacing="0"><tbody><tr><th>长度</th><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>5</td><td>0.51</td><td>3.10</td></tr><tr><td>6</td><td>1.29</td><td>25.28</td></tr><tr><td>7</td><td>0.26</td><td>18.11</td></tr><tr><td>8</td><td>36.38</td><td>20.17</td></tr><tr><td>9</td><td>24.14</td><td>12.01</td></tr><tr><td>10</td><td>14.48</td><td>7.34</td></tr><tr><td>11</td><td>9.78</td><td>6.79</td></tr></tbody></table><br /><br />点评：<br />　　（从平均水平看）CSDN用户的密码长度显然大于人人网用户。<br /><br /><h2>★密码类型分布</h2><br /><table border="1" cellspacing="0"><tbody><tr><th>类型</th><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>纯数字</td><td>45.01</td><td>52.97</td></tr><tr><td>纯小写字母</td><td>11.64</td><td>19.96</td></tr></tbody></table><br /><br />点评：<br />　　纯数字的口令，比例太高，不是好现象。<br />　　对于同样长度的口令，纯小写字母相比纯数字，其组合的可能性更多，更难暴力破解。<br /><br /><h2>★使用手机作密码</h2><br /><table border="1" cellspacing="0"><tbody><tr><th><br /></th><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>手机号</td><td>2.18(约14万)</td><td>2.91(约13万8)</td></tr></tbody></table><br /><br />点评：<br />　　作为口令的手机号，多半就是本人的手机号。<br />　　手机的稳定性远高于电子邮箱。因此，这个信息的价值还是挺大滴。如果有人想搜罗手机号的话，这下可有福了。<br /><br /><h2>★使用生日作密码</h2><br /><table border="1" cellspacing="0"><tbody><tr><th>日期格式</th><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>YYMMDD</td><td>0.14</td><td>3.59</td></tr><tr><td>YYYYMMDD</td><td>5.92(38万)</td><td>2.67</td></tr><tr><td>MMDDYYYY</td><td>0.06</td><td>0.11</td></tr><tr><td>YYYY-MM-DD</td><td>小于0.01</td><td>小于0.01</td></tr><tr><td>YYYY.MM.DD</td><td>小于0.01</td><td>小于0.01</td></tr><tr><td>YYYY/MM/DD</td><td>小于0.01</td><td>0</td></tr></tbody></table><br /><br />点评：<br />　　用生日做口令，表面上看，位数还挺多（少的有6位，多的有8位，加分隔符的话甚至有10位）。<br />　　但其实这种口令很弱。因为可能的生日个数是很有限的——生日通常分布在1940年以来——大约是365×70=25550。即便算上不同的格式，也就十多万种。如果是程序来穷举，用不了一柱香的功夫。<br /><br /><h2>★密码和用户名相关</h2><br /><table border="1" cellspacing="0"><tbody><tr><th>类型</th><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>直接拿用户名做密码</td><td>4.55(约29万2)</td><td>0.04</td></tr><tr><td>密码包含用户名</td><td>0.25</td><td>小于0.01</td></tr><tr><td>密码是用户名的一部分</td><td>2.04(约13万1)</td><td>1.57</td></tr></tbody></table><br /><br />点评：<br />　　很奇怪，CSDN居然有这么多人拿用户名作口令，比例远远高于人人网用户。这有点不合逻辑啊。<br />　　本文发出后，不少CSDN的用户留言，解释此原因：因为网友经常需要上CSDN下载东西（比如电子书）。但是CSDN不提供匿名下载。所以就临时注册一个用户。为了省事，口令就设置成跟用户名一样了。<br /><br /><h2>★用英文单词作密码</h2><br />俺拿四级词汇作为字典，测试了一番。比例如下：<br /><table border="1" cellspacing="0"><tbody><tr><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>0.11</td><td>0.19</td></tr></tbody></table><br /><br />点评：<br />　　两个网站的比例都不算高，表扬一下。<br />　　顺便说一下，在作密码的单词里，排名第一的是 password。这个习惯跟老外是一致的。<br /><br /><h2>★用数字作密码</h2><br />　　前面给出的按类型统计中，纯数字的比例是很高的。纯数字密码，常见的组合有如下。<br /><br /><table border="1" cellspacing="0"><tbody><tr><th>类型</th><th>CSDN (%)</th><th>RenRen (%)</th></tr><tr><td>123456789</td><td>3.91(约25万1)</td><td>0.72(约3万4)</td></tr><tr><td>12345678</td><td>3.31(约21万2)</td><td>0.25(约1万2)</td></tr><tr><td>1234567</td><td>小于0.01</td><td>0.11(约5千)</td></tr><tr><td>123456</td><td>0.03(约2千)</td><td>3.73(约17万7)</td></tr><tr><td>12345</td><td>小于0.01</td><td>0.31(约1万5)</td></tr><tr><td>全是0</td><td>0.65(约4万2)</td><td>0.61(约2万9)</td></tr><tr><td>全是1</td><td>1.41(约9万1)</td><td>0.91(约4万3)</td></tr><tr><td>全是2</td><td>0.04</td><td>0.05</td></tr><tr><td>全是3</td><td>0.03</td><td>0.04</td></tr><tr><td>全是4</td><td>0.01</td><td>0.02</td></tr><tr><td>全是5</td><td>0.03</td><td>0.05</td></tr><tr><td>全是6</td><td>0.09(约6千)</td><td>0.11(约5千)</td></tr><tr><td>全是7</td><td>0.03</td><td>0.05</td></tr><tr><td>全是8</td><td>0.25(约1万6)</td><td>0.13(约6千)</td></tr><tr><td>全是9</td><td>0.06</td><td>0.05</td></tr></tbody></table><br /><br />点评：<br />　　上述这些组合，都属于弱爆了的口令——极易被入侵者攻破。<br />　　使用这些组合的用户比例还挺高。这下，口令攻击者可就爽了。<br />另外，全8的口令明显要高一些，而全4的比例明显低。貌似迷信的因素也体现到口令设置了。<br /><br /><h2>★名人的口令</h2><br />　　CSDN上有不少知名博客（也叫专家博客）。本来，俺以为：既然号称专家，那安全意识应该不会太差吧。所以，俺今天抱着偷窥明星隐私的丑恶心态，查了几个名人的密码。<br />　　结果，看下来很令人失望啊——很多知名人士的密码，貌似也很弱啊！为了避免让某些人难堪，俺就不举例说明了。<br />　　说到专家博客，顺便插一句：俺也曾经也是CSDN的专家博客之一。今年8月份，CSDN要搞专家实名制。但是俺死活不肯公开真实身份。所以，俺的专家资格已经被取消啦 :-(<br /><br /><h2>★俺的忠告</h2><br />　　经过这次脱库事件，希望诸位能意识到密码的重要性。强烈建议看一下俺去年写的帖子——《<a href="../../2010/06/howto-prevent-hacker-attack-3.md" target="_blank">如何防止黑客入侵[2] - 如何构造安全的口令/密码</a>》。<br />　　还有，无论如何也不要在多个地方共用<b>相同或相似</b>的密码。<div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>版权声明</h4>
本博客所有的原创文章，作者皆保留版权。转载必须包含本声明，保持本文完整，并以超链接形式注明作者<a href="mailto:program.think@gmail.com">编程随想</a>和本文原始网址：<br>
<a href="2011/12/csdn-renren-password-analysis.md">2011/12/csdn-renren-password-analysis.md</a>
</div>
</div>
</body>
<.md>