---
title: NVM简明指南
date: 2016-10-26 22:01:29
tags:
---
 <font color="red">本教程适用于windows用户</font>

### 安装操作步骤
1. **下载 [nvm-windows](http://pan.baidu.com/s/1c2C77sk "nvm-windows")**

2. **解压到一个全英文目录(建议存放在C盘)**

3. **修改settings文件**
  - root => nvm.exe 的位置
  - path => nodejs的快捷方式的位置（与nvm文件夹平行或自选）
  - arch => 32/64 （你操作系统位数）

4. **加入环境变量**
  - win + r => 输入sysdm.cpl => 高级-环境变量-用户变量
  - 新建 NVM_HOME = root
  - 新建 NVM_SYMLINK = path

5. **测试变量是否成功**
  - cmd 输入`PATH`查看所有的用户变量是否有更新

  - cmd 输入`set xx`查看你想要查看的变量地址是否正确，如`set NVM_HOME`

6. **测试nvm是否安装成功**
  - `$nvm` => nvm help ... OK

  - `$nvm ls` => 列出所有安装的node版本

  - `$nvm use` => 使用需要的node版本

  - `$nvm install/uninstall` => 安装卸载
