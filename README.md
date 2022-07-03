# Neovim

## 安装 Neovim

[Click here to learn how to install Neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim).

安装成功后，可以输入 `nvim` 查看是否安装成功。

## 创建 Neovim 配置文件

在命令行中，输入 `nvim`，然后输入 `:help vimrc`，查看配置文件的路径。这里以 Unix 系统为例。

到 `~` 路径：

```bash
cd ~
```

查看是否有 `.config` 文件：

```bash
ls -a | grep .config
```

如果没有 `.config` 路径，就创建后再进入；如果有 `.config` 文件，就直接进入：

```bash
mkdir -p .config
cd .config
```

然后，同理，查看是否有 `nvim` 路径：

```bash
mkdir -p nvim
cd nvim
```

创建 Neovim 配置文件：

```bash
nvim init.vim
```

简单的 Neovim 配置：

```
" set number
:set nu
" set relative number
:set rnu

" 支持中文
set encoding=UTF-8 
" set langmenu=zh_CN
language message zh_CN.UTF-8
set fileencoding=utf-8
```

## 安装 vim-plug

具体的安装方法可以查看 [junegunn/vim-plug](https://github.com/junegunn/vim-plug)，这里以 Unix 为例。

进入 Neovim 配置文件的路径：

```bash
cd ~/.config/nvim
```

创建 `autoload` 路径，并进入：

```bash
mkdir -p autoload
cd autoload
```

输入下面这行命令后，即可下载成功：

```bash
curl https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim -o plug.vim
```

现在，打开 Neovim 的配置文件：

```bash
nvim ~/.config/nvim/init.vim
```

输入：

```
" not compatible with older versions of vi or vim
set nocompatible

" require this
filetype off

" begin: vim-plug 设置
call plug#begin('~/.config/nvim/plugged')

" 插件就放置在这些地方

" end：vim-plug 设置
call plug#end()
```

插件放置在上面标识的位置即可。比如安装 (morhetz/gruvbox)[https://github.com/morhetz/gruvbox]，可以输入：

```
Plug 'morhetz/gruvbox'
```

在保存完成后，再次进入 `init.vim`，然后使用下面的命令进行安装：

```
:PlugInstall
```

安装完成后，就可以使用 gruvbox 了。比如更换当前的主题颜色，可以直接在 `init.vim` 中添加：

```
colorscheme gruvbox
```

## Neovim 的使用

使用 `:terminal` 可以打开终端

## 参考资料

- [Awesome Neovim Setup From Scratch](https://www.youtube.com/watch?v=JWReY93Vl6g)
- [Command Line: Neovim Installation and Configuration](https://www.youtube.com/watch?v=ZEFXeRIFvN0)
