# monkey-vim

* **xterm vim**

![xterm vim](https://raw.githubusercontent.com/QMonkey/monkey-vim/master/pictures/xterm_vim.png "xterm vim")

* **gvim**

![gvim](https://raw.githubusercontent.com/QMonkey/monkey-vim/master/pictures/gvim.png "gvim")

## 简介

也许你也有这样的经历：IDE不够强大，于是你给你的IDE装上各种各样的插件。随着插件增多，你发现IDE变得越来越卡，占用越来越多系统资源（我的Atom曾经占用了2G内存！！！）。最后，你不得不在强大和轻量之间权衡。

monkey-vim项目，旨在打造一个强大，快速，并且占用少量系统资源的IDE。

## 安装步骤

### 1. clone到本地

```
git clone https://github.com/QMonkey/monkey-vim.git
```

### 2. 安装依赖

#### 2.1 工具依赖

```
# Ubuntu
sudo apt-get install ctags
sudo apt-get install ack-grep

# OpenSUSE
sudo zypper install ctags
sudo zypper install ack

# CentOS
sudo yum install ctags
sudo yum install ack
```

#### 2.2 fonts

* [powerline-font](https://github.com/powerline/fonts)
* [nerd-font](https://github.com/ryanoasis/nerd-fonts)

#### 2.3 C/C++

```
# Ubuntu
sudo apt-get install gcc
sudo apt-get install g++
# x取决于你要安装的版本
sudo apt-get install clang-3.x

# OpenSUSE
sudo zypper install gcc
sudo zypper install gcc-c++
sudo zypper install llvm-clang

# CentOS
sudo yum install gcc
sudo yum install gcc-c++
sudo yum install clang
```

#### 2.4 Javascript

```
sudo npm install -g jslint
sudo npm install -g js-beautify
sudo npm install -g tern
```

#### 2.5 JSON

```
sudo npm install -g jsonlint
```

#### 2.6 HTML

```
sudo npm install -g jshint
```

#### 2.7 CSS

```
sudo npm install -g csslint
```

#### 2.8 Python

```
sudo pip install pyflakes
sudo pip install autopep8
sudo pip install pep8
sudo pip install jedi
```

#### 2.9 Golang

```
# Ubuntu
sudo apt-get install golang

# OpenSUSE
sudo zypper install go

# CentOS
sudo zypper install golang

# monkey-vim 安装成功后，执行以下vim命令
:GoInstallBinaries
```

#### 2.10 Java

```
# Ubuntu
sudo apt-get install astyle
sudo apt-get install openjdk-8-jdk

# OpenSUSE
sudo zypper install astyle
sudo zypper install java-1_8_0-openjdk-devel

# CentOS
sudo yum install astyle
sudo yum install java-1.8.0-openjdk-devel.x86_64
```

#### 2.11 Shell

```
# Ubuntu
sudo apt-get install devscripts

# OpenSUSE
sudo zypper install checkbashisms

# CentOS
sudo yum install rpmdevtools
```

#### 2.12 Markdown

```
sudo npm install -g instant-markdown-d
sudo gem install mdl
```

### 3. 安装

```
cd monkey-vim
cp .vimrc ~/.vimrc
vim
```

## 快捷键

```
以下所有“Leader”键，都代表“\”键
```

### 1. 正常模式

#### 1.1 按键修改

```
Y       复制到行尾，相当于“y$”命令
U       Redo，相当于“Ctrl-r”
;       进入命令行模式，相当于“:”键
q       退出窗口，相当于命令“:q”
Ctrl+c  退出当前模式，并返回到正常模式，相当于<ESC>键
```

#### 1.2 F2 ~ F10

```
F2      打开/关闭NERDTree
F3      打开/关闭Tagbar
F4      打开/关闭Gundo
F5      打开/关闭paste模式
F6      运行当前项目（可用:Focus注册执行的命令，如:Focus gcc % -o a.out）
F7      异步运行当前项目
F8      显示F6或F7运行结果
F9      预览Markdown
F10     打开/关闭RainbowParentheses
F11     全屏切换（仅在gui模式下有效）
```

#### 1.3 分屏

```
Leader+s    输入打开文件的路径，并创建一个水平分屏的窗口
Leader+v    输入打开文件的路径，并创建一个垂直分屏的窗口

Ctrl+h      跳转到左窗口
Ctrl+j      跳转到下窗口
Ctrl+k      跳转到上窗口
Ctrl+l      跳转到右窗口

Ctrl+up     窗口垂直方向伸展
Ctrl+down   窗口垂直方向收缩
Ctrl+left   窗口水平方向伸展
Ctrl+right  窗口水平方向收缩
Leader+z    窗口放大/恢复

Leader+ww   交换两个窗口（两个窗口都需要执行该命令）
```

#### 1.4 Tab

```
Ctrl+t      输入打开的文件路径，并创建一个新tab窗口

H           切换到上一个tab窗口
L           切换到下一个tab窗口
Leader+1~9  切换到第1~9个tab窗口
Leader+[    切换到第一个tab窗口
Leader+]    切换到最后一个tab窗口
```

#### 1.5 替换

```
Leader+R    替换光标所在的单词（非整词，不需要逐一确认）
Leader+rw   替换光标所在的单词（整词，不需要逐一确认）
Leader+rc   替换光标所在的单词（非整词，需要逐一确认）
Leader+rwc  替换光标所在的单词（整词，需要逐一确认）
```

#### 1.6 语言相关

```
K       查看光标所在的单词在文档（目前只支持man, godoc, pydoc, ri, vim help）中的解释。

gd      GoDef
gi      GoImports
gt      GoTest，执行当前go文件的单元测试
gf      GoTestFunc，执行光标所在的单元测试函数
```

#### 1.7 ctags

```
Ctrl+]  跳转到符号定义处，如有多处定义，则跳到第一处
g]      选择一处符号定义并跳转
```

#### 1.8 marks

```
m[a-zA-Z]   标记当前行
dm[a-zA-Z]  删除标记[a-zA-Z]

'[a-zA-Z]   跳转到标记行

m/          在Location List里，查看当前buffer的所有标记
m-          删除当前行的所有标记
m<space>    删除当前buffer的所有标记
```

#### 1.8 代码补全，定义、声明跳转插件：[YouCompleteMe](https://github.com/Valloric/YouCompleteMe)

```
Leader+jd   跳转到定义
Leader+jc   跳转到声明
Leader+ji   跳转到头文件
```

#### 1.9 静态语义语法检查插件：[Syntastic](https://github.com/scrooloose/syntastic)

```
Leader+e    打开/关闭错误信息窗口
```

#### 1.10 快速移动插件：[EasyMotion](https://github.com/easymotion/vim-easymotion)

```
Leader+Leader+j     跳转到当前屏幕，光标后任何指定行
Leader+Leader+k     跳转到当前屏幕，光标前任何指定行
Leader+Leader+w     跳转到当前屏幕，光标后任何指定单词
Leader+Leader+b     跳转到当前屏幕，光标前任何指定单词
Leader+Leader+s     搜索字符，并跳转到当前屏幕指定字符
```

#### 1.11 buffer、tab切换，保存/恢复workspace插件：[Vim-CtrlSpace](https://github.com/vim-ctrlspace/vim-ctrlspace)

```
Leader+ss   保存workspace
Leader+rs   恢复workspace
```

#### 1.12 项目文件搜索插件：[CtrlP](https://github.com/ctrlpvim/ctrlp.vim)

```
Ctrl+p      打开CtrlP
```

#### 1.13 其它

```
bd              删除当前buffer
'.              最后一次变更的地方
''              跳回来的地方（最近两个位置跳转）
Ctrl+o          跳回，可用于多种类型跳转（符号跳转，定义跳转，屏幕跳转等）
Ctrl+i          继续上次跳转（与Ctrl+o操作相反），可用于多种类型跳转（符号跳转，定义跳转，屏幕跳转等）
Leader+/        取消搜索高亮
Leader+space    去除行尾空白字符
```

### 2. 插入模式

#### 2.1 按键修改

```
Ctrl+c  退出当前模式，并返回到正常模式，相当于<ESC>键
```

### 3. 可视化模式

#### 3.1 按键修改

```
Y       复制到行尾
U       Redo
;       进入命令行模式，相当于“:”键
Ctrl+c  退出当前模式，并返回到正常模式，相当于<ESC>键
```

#### 3.2 替换

```
Leader+R    替换选中的字符串（不需要逐一确认）
Leader+rc   替换选中的字符串（需要逐一确认）
```

#### 3.3 语言相关

```
K       查看所选字符串在文档（目前只支持man, godoc, pydoc, vim help）中的解释。
```

#### 3.3 快速移动插件：[EasyMotion](https://github.com/easymotion/vim-easymotion)

```
Leader+Leader+j     跳转到当前屏幕，光标后任何指定行
Leader+Leader+k     跳转到当前屏幕，光标前任何指定行
Leader+Leader+w     跳转到当前屏幕，光标后任何指定单词
Leader+Leader+b     跳转到当前屏幕，光标前任何指定单词
Leader+Leader+s     搜索字符，并跳转到当前屏幕指定字符
```

### 4. 命令行模式

```
Ctrl+j  下一条命令
Ctrl+k  上一条命令
Ctrl+a  跳到命令行最前
Ctrl+e  跳到命令行最后

w!!     使用root权限写文件
```

## 常用命令

### TODO

## 注意事项

* monkey-vim默认tab的缩进为8个字符，不使用space替代tab。如果你喜欢tab缩进为4个字符，并且使用space替代tab。你可以将以下vim配置

```
set tabstop=8
set softtabstop=8
set shiftwidth=8
set noexpandtab
```

改为

```
set tabstop=4
set softtabstop=4
set shiftwidth=4
set expandtab
```

* 为了让运行在xterm上的vim可以与系统共享剪贴板，请安装gvim，并在~/.bashrc中加入以下Shell命令：

```
if [ -x $(which gvim) ]
then
    alias vi='gvim -v'
    alias vim='gvim -v'
    alias view='gvim -v -R'
    alias vimdiff='gvim -v -d'
fi
```

* 如果你觉得打开/保存go文件需要较长时间，或者你不希望保存go文件时，自动生成可执行文件，你可以将以下vim配置

```
let g:syntastic_go_checkers = ['go', 'golint', 'govet', 'errcheck']
```

改为

```
let g:syntastic_go_checkers = ['golint', 'govet', 'errcheck']
```

## 推荐设置

### 设置方法：在~/.bashrc中加入以下Shell命令

* 使用vman命令，可在vim中下查看man文档

```
vman() {
    vim -R -c "Ref man $*" ~/.vimrc -c "if line('$') == 1 | cquit | endif" -c "silent only" -c "setlocal nomodifiable"
    if [ "$?" != "0" ]; then
        echo "No manual entry for $*"
    fi
}
```

* 使用dirdiff命令，可在vimdiff中查看，比较和编辑两个文件夹

```
dirdiff() {
    if [ $# -ne 2 ]; then
        echo "Invalid arguments, please pass two arguments"
        return
    fi

    vim -c "DirDiff $*" ~/.vimrc -c "execute 'bdelete ' . bufnr('~/.vimrc')"
}
```
