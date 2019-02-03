# hexo_theme_next
Personalized setting  about hexo_theme_next, attach the blog config setting and you can use it directly!
## 1. hexo的next主题个性化打造炫酷网站之在右上角或者左上角实现fork me on github
点击[这里](https://github.blog/2008-12-19-github-ribbons/)挑选自己喜欢的样式，并复制代码。 例如，我是复制如下代码：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190128112024874.png)
然后粘贴刚才复制的代码到themes/next/layout/_layout.swig文件中(放在`<div class="headband"></div>`的下面)，并把href改为你的github地址

```css
<a href="https://github.com/violet227">
<img width="149" height="149" 
style="position: absolute; top: 0; right: 0; border: 0;" 
src="https://github.blog/wp-content/uploads/2008/12/forkme_right_darkblue_121621.png?resize=149%2C149" class="attachment-full size-full" alt="Fork me on GitHub" data-recalc-dims="1">
</a>
```
 **注意：须手动输入style放置自己想要的位置**
 偶然的我又发现了另一款挂饰
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190128205041335.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZseV93dA==,size_16,color_FFFFFF,t_70)
方法同上，网址链接[在这](http://tholman.com/github-corners/)
