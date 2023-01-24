---
title: 如何更换博客背景和音乐
---
##  说明：仅此备份
### 一、更换博客背景操作步骤

````bash
进入 themes\next\source\css 目录中
打开 main.styl 文件
在末尾添加 css 代码即可
````
<!--more-->
#### 备注：在原先打开博客的基础上进行，在网页中进入开发者工具,找到body的标签->main.css:xxx 
#### 复制修改如下：
````bash
body {
  background: url(/images/background.jpg);  //可更换网址
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: 50% 50%;
  color: var(--text-color);
  font-family: 'Lato', "PingFang SC", "Microsoft YaHei", sans-serif;
  font-size: 1em;
  line-height: 2;
}
````

### 二、更换背景音乐操作步骤
````bash
生成音乐HTML代码
修改 themes/next/layout/_macro/sidebar.swig文件
在 themes/next/_config.yml主题配置文件中添加音乐地址配置
设置全局播放：打开themes\next\layout\_layout.swig
````
#### 备注：2
````bash
<!-- 音乐播放器 -->
<div>
    {% if theme.background_music %}
        <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="{{ theme.background_music }}"></iframe>
    {% endif %}
</div>
````

#### 备注：3-后续只需更改URL链接
````bash
background_music: //
````

#### 备注：4 -head标签后
````bash
<!--pjax：防止跳转页面音乐暂停-->
 <script src="https://cdn.jsdelivr.net/npm/pjax@0.2.8/pjax.js"></script>
````

````
在next\_config.yml中找到pajx，将它设置为true
````
