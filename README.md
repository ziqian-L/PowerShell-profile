# PowerShell 配置

## 功能介绍

包含模块：

- posh-git

- PSReadLine

功能：

按键映射

F1、F7快捷键

智能引号、括号

随机密码

快速开启hosts文件

配置Powershell

## PowerShell配置过程

### 1.安装posh-git和PSReadLine模块
查看已安装的模块
```
Get-InstalledModule
```
安装[posh-git](https://github.com/dahlbyk/posh-git)
```
Install-Module posh-git
```

[PSReadLine](https://github.com/PowerShell/PSReadLine)已经内置在了PowerShell中，无需安装，可以使用以下命令来检测
```
Get-Module PSReadLine -ListAvailable
```
如果没有检测到，执行以下命令安装
```
Install-Module PSReadLine -Force
```
### 2.添加配置
如果安装了`VSCode`的直接使用`code`命令，否者使用`notepad`打开：
```
code $profile
notepad $profile
```
在配置文件中添加：
```
Import-Module posh-git ## 在当前打开的 PowerShell 终端中引入 posh-git（已安装，这里只是引入） 
Import-Module PSReadLine ## 这个工具主要做命令提示管理等操作，默认集成在了 PowerShell 中，不需要安装
```
### 3.删除模块
使用`Uninstall-Module`命令可以删除安装的模块，例
```
Uninstall-Module posh-git
```

`PSReadLine`模块的卸载不能通过`Uninstall-Module`命令完成
首先需要用以下命令来检测安装位置，然后删除对应的文件夹即可（不要乱删）
```
Get-Module PSReadLine -ListAvailable
```

删除模块后需要将配置文件中的相关配置项删除，否则在启动命令行时会报错
```
code $profile
notepad $profile
```
### 4.更多模块
可以在[[https://www.powershellgallery.com/]]获取到更多的模块





参考：https://blog.miniasp.com/post/2021/11/24/PowerShell-prompt-with-Oh-My-Posh-and-Windows-Terminal

