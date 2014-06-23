<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [更新 custom-icon 操作流程](#更新-custom-icon-操作流程)
	- [一、 生成](#一、-生成)
	- [二、 使用](#二、-使用)
- [更多待完善](#更多待完善)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 更新 custom-icon 操作流程

- 优先到 http://www.bootcss.com/p/font-awesome/ 查找有没有可以直接使用的 icon。
- 没有找到对于icon则使用自定义的font icon,步骤如下：


##一、 生成
  
- 打开 http://icomoon.io/app/#/select ，点击 ```Import Icons```, 把本次需要用到的所有 svg 文件导入。全部选中，点击下方font。
- 点击 ``Preferences``, Font Name: ``your-font-icon-name``, Class Prefix: ``your-font-icon-prefix-``。(注意不同的 font-icon 取不同的名字。)
- 点击 ``Codes`` ，可以看到类似 ```Start with U+ e600```,  换一个 code，比如  ``f300``，``a100`` 等等避免缓存。
- 然后下载。


##二、 使用
  下载文件解压后，用 fonts 文件夹里的四个文件覆盖项目对应的(同名)字体文件。打开解压文件夹里的 ``style.css`` 以及项目中的字体```scss```文件 ,```scss```文件应该有如下结构：
  
```javascript
    [@import "your/mixins";]
    @include xxx-font-face("xxx-icon", font-files('xxx-icon/xxx-font-icon.ttf','xxx-icon/xxx-font-icon.woff'), "xxx-icon/xxx-font-icon.eot");

// step 1
.xxx-icon-home,.xxx-icon-camera,.xxx-icon-check {
    font-family: 'xxx-icon';
    content: attr(data-icon);
    speak: none;
    font-style: normal;
    font-weight: normal;
    font-variant: normal;
    text-transform: none;
    line-height: 1;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}
    
// step 2
.xxx-icon-home:before {
  content: "\e200";
}
.xxx-icon-camera:before {
  content: "\e201";
}
.xxx-icon-check:before {
  content: "\e201";
}

```
  
- 把本次新增的几个 icon 的 className 添加到``scss ``文件的 ```step 1```。
  
- ```step 2``` 下面的全部内容，用 style.css的对应内容覆盖。

- 在相关的文件中引入本```scss```文件。 ``@import "xxx/xxx-fonts/xxx-icon";``。

- 使用你的自定义字体类名。 如 ``xxx-icon-share``, ``xxx-icon-home``。


# 更多待完善
