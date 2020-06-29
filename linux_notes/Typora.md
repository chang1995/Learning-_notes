# Typora

2020/6/19

Typora支持Windows、OS X 和 Linux多个操作系统，支持数学编辑，可与 Word、PDF直接格式转换，可以进行多种文档格式转换。

## 1. 下载

```
$ wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
```

```p
# add Typora's repository
$ sudo add-apt-repository 'deb https://typora.io/linux ./'
$ sudo apt-get update
```

```p
# install typora
$ sudo apt-get install typora
```

以上在为Linux上安装，其他操作系统请参考: https://www.typora.io/

## 2. 简单的使用方法

- 一级标题： `Ctrl + 1` 
- 二级标题： `Ctrl + 2`  -- 以此类推
- 加粗： `Ctrl + B`
- 标题： `Ctrl + H`
- 插入链接： `Ctrl + K`
- 行内代码： `Ctrl + Shift + K`  或  3个反引号（`） + 回车
- 插入图片： `Ctrl + Shift + I`
- 左侧显示目录：`Ctrl + Shift + L` 
- 撤销： `Ctrl + Z`
- 插入表格：`Ctrl + T`
- 水平分割线： 输入 `***` 或者 `---` 再按回车
- 删除线： 使用`~~删除线~~` 快捷键 `Alt + Shift + 5`   ~~删除线~~
- 生成目录：在需要生成目录的地方输入`[TOC]`或`[toc]`即可生成目录
