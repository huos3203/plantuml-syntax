# Vim PlantUML Syntax/Plugin/FTDetect

This is a vim syntax file for [PlantUML](http://plantuml.com).

The `filetype` will be set to `plantuml` for *.pu, *.uml or *.plantuml files or if the
first line of a file contains `@startuml`.

Additionally the `makeprg` is set to `plantuml` assuming you have this
executable in your path.  This file could contain something like

````sh
#!/bin/bash
java -jar $HOME/lib/java/plantuml.jar -tsvg $@
````

You can change the name of this file by setting `g:plantuml_executable_script`



## 定义语法规则
`syntax`目录中定义了`pluntuml.vim`语法规则,该文件名指定了语法类型`pluntuml`。

## 后缀识别文件类型
`ftdetect`目录定义了文件后缀的相关定义在读入`*.pu, *.uml or *.plantuml `文件时，自动识别其语法为刚才定义语法类型`pluntuml`。
将`ftdetect/pluntuml.vim`拷贝到目录`~/.vim/ftdetect`即可
```
autocmd BufRead,BufNewFile *.pu,*.uml,*.plantuml setfiletype plantuml | set filetype=plantuml
```
`filetype`的名字即为上一步新建的文件的文件名。

## 给定义的语法变量指定颜色
在vim中输入`:colorscheme`查看当前使用的color文件名
1. 进入命令模式 `shift + :`
2. 输入指令:`colorscheme`
3. 输出：当前使用的颜色主题
![](colorscheme.png)

## 设置代码缩进

## 目录介绍

|目录|功能介绍|
|:-------|:-------|
|~/.vim/colors/ |是用来存放vim配色方案的|
|~/.vim/syntax/ |语法描述脚本|
|~/.vim/ftdetect/ |ftdetect代表的是“filetype detection（文件类型检测）”。此目录中的文件应该用自动命令（autocommands）来检测和设置文件的类型|
|~/.vim/ftplugin/ | 用户的默认文件类型相关脚本文件的存放目录|
|~/.vim/indent/ |相关文件类型的缩进。例如python应该怎么缩进，java应该怎么缩进等等。其实放在ftplugin中也可以，但单独列出来只是为了方便文件管理和理解。|
|~/.vim/colors/ |是用来存放vim配色方案的|
