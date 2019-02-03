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
## 2. Hexo NexT主题添加点击爱心效果
### 2.1 创建js文件
在/themes/next/source/js/src下新建文件 `clicklove.js` ，接着把下面的代码拷贝粘贴到 clicklove.js 文件中。
```javascript
!function(e,t,a){function n(){c(".heart{width: 10px;height: 10px;position: fixed;background: #f00;transform: 
rotate(45deg);-webkit-transform: rotate(45deg);-moz-transform: 
rotate(45deg);}.heart:after,.heart:before{content: '';width: inherit;height: inherit;background: 
inherit;border-radius: 50%;-webkit-border-radius: 50%;-moz-border-radius: 50%;position: 
fixed;}.heart:after{top: -5px;}.heart:before{left: -5px;}"),o(),r()}function r(){for(var 
e=0;e<d.length;e++)d[e].alpha<=0?(t.body.removeChild(d[e].el),d.splice(e,1)):(d[e].y-
-,d[e].scale+=.004,d[e].alpha-
=.013,d[e].el.style.cssText="left:"+d[e].x+"px;top:"+d[e].y+"px;opacity:"+d[e].alpha+";transform:scale("+d[
e].scale+","+d[e].scale+") rotate(45deg);background:"+d[e].color+";z-
index:99999");requestAnimationFrame(r)}function o(){var t="function"==typeof 
e.onclick&&e.onclick;e.onclick=function(e){t&&t(),i(e)}}function i(e){var 
a=t.createElement("div");a.className="heart",d.push({el:a,x:e.clientX-5,y:e.clientY-
5,scale:1,alpha:1,color:s()}),t.body.appendChild(a)}function c(e){var 
a=t.createElement("style");a.type="text/css";try{a.appendChild(t.createTextNode(e))}catch(t)
{a.styleSheet.cssText=e}t.getElementsByTagName("head")[0].appendChild(a)}function s()
{return"rgb("+~~(255*Math.random())+","+~~(255*Math.random())+","+~~(255*Math.random())+")"}var 
d=[];e.requestAnimationFrame=function(){return 
e.requestAnimationFrame||e.webkitRequestAnimationFrame||e.mozRequestAnimationFrame||e.oReque
stAnimationFrame||e.msRequestAnimationFrame||function(e){setTimeout(e,1e3/60)}}(),n()}
(window,document);
```
### 2.2修改_layout.swig
打开\themes\next\layout\_layout.swig文件,在末尾（在前面引用会出现找不到的bug） ，引用`clicklove.js`

```javascript
<!-- 页面点击小红心 -->
<script type="text/javascript" src="/js/src/clicklove.js"></script>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190128171156368.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZseV93dA==,size_16,color_FFFFFF,t_70)
