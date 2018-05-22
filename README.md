init
===

personal linux init @ ubuntu 18.04 LTS

简述
---

包含 Zsh + Tmux + Vim + Python + Golang 环境

在所有的更新结束之后执行下面的命令修改默认的 shell

```
chsh -s `/bin/zsh`
```

tmux
---

PS: 当前的使用的 tmux 需要 1.9+ 的版本，不然有些功能用不了

prefix 是 `ctrl + x`

常用快捷键

### pane

| 快捷键 | 用法  | 备注 |
|--------|-------|------|
| prefix + % | 分成上下两个 pane |      |
| prefix + " | 分成左右两个 pane |      |
| prefix + [h j k l] | 选择 pane |      |
| prefix + [方向键] | 按方向改变 pane 大小 | 每次 10 个单位 |
| prefix + x | 删掉当前的 pane | 需要确认 |
| prefix + z | toggle pane zoom | |
| prefix + space | toggle between layouts | |
| prefix + t | 当前 pane 显示时间 | |

### window

| 快捷键 | 用法  | 备注 |
|--------|-------|------|
| prefix + [0 ~ 9] | 选择相应的 window |      |
| prefix + x | 删掉当前的 window | 需要确认 |
| prefix + w | 列出当前的 window | |

### 编辑

| 快捷键 | 用法  | 备注 |
|--------|-------|------|
| prefix + [ | 进入复制模式 | vi mode |
| prefix + ] | 粘贴刚复制的东西 | |

- 复制模式下按 enter 进行复制
- 复制模式下按 y 复制到系统粘贴版
- 需要 xclip 支持

zsh
---

使用 [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) 来管理 zsh 配置文件

目前设置了几个环境变量

1. Golang 的 `$GOPATH`
2. virtualenvwrapper 的 `$WORKON_HOME`

nodejs
---

现在使用的是下载然后编译安装的方式，路径为 `$HOME/bin/node`

```
git clone https://github.com/nodejs/node
cd node
./configure --prefix=$HOME/bin/node
make install

cd ..
git clone https://github.com/npm/npm
make install
```

other tips
---

### SSH

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

### 键盘大写锁定键

```
setxkbmap -layout us -option ctrl:nocaps
```
上述的代码重启后失效，也可通过 tweak 去修改


### GIT

```
git config --global user.name 'lycheng'
git config --global user.email example@example.com
git config --global core.editor vim
```

### GNOME

```
# 设置 GNOME 只在当前的 workspace 切换程序
gsettings set org.gnome.shell.app-switcher current-workspace-only true
```
