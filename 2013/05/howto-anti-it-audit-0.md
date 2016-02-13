<!DOCTYPE.md>
.md xmlns="http://www.w3.org/1999/...md" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text.md; charset=utf-8" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>如何对付公司的监控[0]：概述 - 编程随想的博客</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="回到首页">如何对付公司的监控[0]：概述</a></h1>
<div class="post-info"><span class="date-header">2013-05-09</span><a href="../../tags/IT.md" class="tag">IT</a> <a href="../../tags/IT.E4BFA1E681AFE5AE89E585A8.md" class="tag">IT.信息安全</a> </div>
<hr>
<div class="post">
<h3>★引子</h3>&#12288;&#12288;最近2-3年，俺写了一个系列博文《<a href="../../2010/04/howto-cover-your-tracks-0.md">如何隐藏你的踪迹，避免跨省追捕</a>》，教大家如何对付朝廷的走狗。这个系列广受关注，看来不少同学都挺注重上网的隐匿性。近期，又有若干读者来信或博客留言，建议介绍一下公司上网监控的问题。貌似关注的人挺多，所以俺就着手写了这方面的扫盲教程。<a name='more'></a><!--program-think--><br /><br /><h3>★写在前面的话</h3>&#12288;&#12288;先声明：<b>俺写这方面的技术内容，出发点是基于保护个人隐私。</b><br />&#12288;&#12288;做这个声明是考虑到：肯定会有一些从事公司管理的同学，责怪俺传播了这些招数，是教唆网友“学坏”。其实俺也知道，很多人关心这个话题属于动机不纯——企图在公司打游戏、看有颜色的视频、上网瞎逛、干私活、等等。这样的动机，俺是不太赞同滴。<br />&#12288;&#12288;但是捏，技术向来是一把双刃剑，既可以用来干好事，也可以用来干坏事。这样的现状，可能永远也改变不了。不能因为技术可能被滥用，就阻碍技术的传播。另外，好的公司管理，是不会单纯依赖技术手段来约束员工的。这么干永远是“治标不治本”。<br /><br /><h3>★常见的监控手段</h3>&#12288;&#12288;扯蛋完毕，言归正传。从技术层面讲，公司对员工的监控，如下三种比较常见：<br />1. 网络行为监控——基于网络流量的监控<br />2. 主机行为监控——基于操作系统的监控<br />3. 摄像头监控<br />&#12288;&#12288;接下来会针对这三个方面分别介绍。包括：各自的原理、优缺点、规避措施。考虑到本博客的读者中，非 IT 领域的越来越多。所以俺尽量讲得通俗一点，避免使用太专业的术语。<br />&#12288;&#12288;本来想一篇博文搞定，写完第一部分发现已经挺长了。怕大伙儿看长篇太累，拆成 3 篇博文。<br /><br /><a name="index"> </a><br />为了方便阅读，把链接整理如下：<br />1. <a href="../../2013/05/howto-anti-it-audit-1.md">如何对付公司的监控——规避“网络行为审计”</a><br />2. <a href="../../2013/05/howto-anti-it-audit-2.md">如何对付公司的监控——规避“主机行为审计”</a><br />3. 如何对付公司的监控——规避“摄像头监控”<br /><br /><b>俺博客上，和本文相关的帖子（需翻墙）</b>：<br /><a href="../../2010/04/howto-cover-your-tracks-0.md">如何隐藏你的踪迹，避免跨省追捕</a><div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>版权声明</h4>
本博客所有的原创文章，作者皆保留版权。转载必须包含本声明，保持本文完整，并以超链接形式注明作者<a href="mailto:program.think@gmail.com">编程随想</a>和本文原始网址：<br>
<a href="2013/05/howto-anti-it-audit-0.md">2013/05/howto-anti-it-audit-0.md</a>
</div>
</div>
</body>
<.md>