# 这是又一个开始...



## 前言

一直想做一个blog记录, 来记录经历过的点点滴滴. 现在来完成这个小想法.  想做, 就去做.  千万别等.

[Hugo]^(一个开源的静态网站生成工具)
<!--more-->


## 安装hugo

运行命令brew install hugo，结果界面一直卡在Updating Homebrew...上.
解决办法: 关闭brew的自动更新.

```text
vim ~/.bash_profile

# 新增一行
export HOMEBREW_NO_AUTO_UPDATE=true
```

## 安装[LoveIt](https://github.com/dillonzq/LoveIt)主题

参考官方[主题文档 - 基本概念](https://hugoloveit.com/zh-cn/theme-documentation-basics/)

## 添加网站、网页流量统计

参考[hugo LeaveIt主题优化二](https://www.jianshu.com/p/94563e7d232a)

1. 在[themes/LoveIt]目录下的layouts下的partials下的head.html中引入不蒜子js文件，代码为
```

<!-- 不蒜子 -->
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```

2. 在页面添加统计代码. [themes/LoveIt]目录下的layouts下的partials下的footer.html,添加以下代码

```html

<span id="busuanzi_container_site_pv">
    本站访问量：<span id="busuanzi_value_site_pv"></span>次
</span>
&nbsp;
<span id="busuanzi_container_site_uv">
    您是本站第 <span id="busuanzi_value_site_uv"></span> 位访问者
</span>
```


3. 在个别页面添加统计代码. [themes/LoveIt]目录下的layouts/下的_default下的fsingle.html,添加以下代码

```
<i class="far fa-eye fa-fw"></i><span id="busuanzi_value_page_pv"></span>&nbsp;{{ T "views" }}
```

