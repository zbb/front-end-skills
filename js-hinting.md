<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [两种 jshint 方式: grunt jshint 和 Sublime-JSHint](#两种-jshint-方式-grunt-jshint-和-sublime-jshint)
	- [grunt jshint](#grunt-jshint)
	- [Sublime-JSHint](#sublime-jshint)
	- [两种方式比较](#两种方式比较)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


# 两种 jshint 方式: grunt jshint 和 Sublime-JSHint 

##  grunt jshint 
 - 作为 grunt 插件。用法: ```media``` 目录下运行:   ```grunt: jshint```
 - 配置文件  ```media/.jshintrc```

   ```javascript
   {
    "...": true,
    "...": false,
    "unused": false,
    "...": true
   }
   ```
   
   ```unused```: 定义了但未使用的变量。现在默认false，即不检查这一项。
   
##  Sublime-JSHint 
 - 作为 Sublime-Text 的插件。
 - 安装:
```javascript
    Ctrl+Shift+P or Cmd+Shift+P in Linux/Windows/OS X
    type install, select Package Control: Install Package
    type js gutter, select JSHint Gutter
```
 - 配置执行 jshint 时机：编辑器内右键 -> JSHint -> Set Plugin Options.
 - 可以把 ```lint_on_save``` 设置为 ```true```。当保存 js 文件时自动执行 jshint.


 - 配置检测项：编辑器内右键 -> JSHint -> Set Linting Preferencess.
 - 把 ```undef``` 设置成 ```false``` 或者注释掉。

 - 用法：保存文件时会自动检测，并标记有错误的行数(如果设置了```lint_on_save``` 为 ```true```)。 ```cmd + shift + j``` 可以弹出相关错误信息。


##  两种方式比较

 -  ```grunt jshint```  一次性检测所有的文件。
 -  ```Sublime-JSHint```  检测当前文件。
 
 -  都可以通过设置相关参数检测特定项。
 -  对于检测一些语法格式、变量是否使用等等，可以用```Sublime-JSHint```在保存当前 js 文件时即时检测一下。
 -  如 混合使用 单/双引号, 定义了变量但未使用过。
 





