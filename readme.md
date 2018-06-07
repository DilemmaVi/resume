# 利用Github Pages搭建个人在线简历

----

#### 什么是 Github Pages？

> Github Pages 是 Github 的静态页面托管服务。它设计的初衷是为了用户能够直接通过 Github 仓库来托管用户个人、组织或是项目的专属页面。参考：https://help.github.com/articles/what-is-github-pages/

可以说相当于一个可直接用 git 管理内容的静态服务器，有许多人会用它来托管自己的个人博客（利用 Jekyll、Pelican 这一类静态页面生成工具）或是在这上面发布自己的 HTML5 小游戏。当然这么好的东西也是有限制的。


**Github Pages 的限制**：

- 仓库存储的所有文件不能超过 1 GB

- 页面的带宽限制是低于每月 100 GB 或是每月 100,000 次请求。

- 每小时最多只能部署 10 个静态网站。

对于发布自己的简历或是部署自己的博客的这一类需求我想是不用担心这些限制的，如果真的不小心超了，Github 那边不会采取什么强制措施，而是会发一份邮件提醒你应该找一个更适合你的托管对象的服务。



#### Quick Start

##### 1. 导入仓库

> 点击github头像旁边的 "+" 号 选择 Import repository克隆地址填 https://github.com/DilemmaVi/resume 项目名填 resume


##### 2. 编辑简历文件

将代码下载到本地

```
git clone https://github.com/你的用户名/resume.git
```

a. 用浏览器打开index.html文件，你会发现这份模板是可编辑的，所有的文字栏目都是可以随意编辑的,点击图片可以通过图片的url地址替换。

b. 编辑完自己的简历以后，就把修改后的代码复制下来，替换掉原index.html里的代码。

c. Firefox 下：打开查看器->复制 html 标签的外部 HTML

d. 然后将index.html中的 html 标签的所有内容（包括 html 标签）替换掉即可。

不喜欢这样子的可以修改static/js下的script.js文件，操作非常简单，删除该文件下的所有内容，然后加上下面这一句。
```
$(document).ready(function($){
    $("*").removeAttr('contenteditable');        
})
```
这一句是为了去掉页面上所有元素的可编辑属性。

最后可以在 CSS 文件内再改改样式。

最后就是提交代码

```
git add .

git commit -m "update info"

git push origin master
```

##### 3. 部署github pages

a. 打开github上的项目，点击右上角的setting

b. 往下拉找到GitHub Pages，source选择master branch，然后点击save

> 现在你可以访问https://你的用户名.github.io/resume  这个地址了，恭喜，简历页面已成功部署在了 Github Pages 上。