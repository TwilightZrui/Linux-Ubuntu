# Software
## terminator
```bash
sudo apt install terminator
```
gedit ~/.config/terminator/config
```bash
[global_config]
  inactive_color_offset = 0.71
  suppress_multiple_term_dialog = True
  title_font = Ubuntu Mono 11[keybindings]
[keybindings]
  copy = <Primary><Shift>c
  switch_to_tab_1 = <Alt>1
  switch_to_tab_2 = <Alt>2
  switch_to_tab_3 = <Alt>3
  switch_to_tab_4 = <Alt>4
  switch_to_tab_5 = <Alt>5
  switch_to_tab_6 = <Alt>6
  switch_to_tab_7 = <Alt>7
  switch_to_tab_8 = <Alt>8
  switch_to_tab_9 = <Alt>9
[layouts]
  [[default]]
    [[[child1]]]
      parent = window0
      type = Terminal
    [[[window0]]]
      parent = ""
      type = Window
[plugins]
[profiles]
  [[default]]
    background_color = "#002b36"
    background_darkness = 0.92
    background_image = None
    background_type = transparent
    font = Ubuntu Mono 10
    foreground_color = "#f9fbf8"
    scroll_on_output = False
    scrollback_lines = 500000
    show_titlebar = False
    use_system_font = False
```
gedit ~/.bashrc
```bash
# uncomment for a colored prompt, if the terminal has the capability; turned
# off by default to not distract the user: the focus in a terminal window
# should be on the output of commands, not on the prompt
#force_color_prompt=yes

if [ -n "$force_color_prompt" ]; then
    if [ -x /usr/bin/tput ] && tput setaf 1 >&/dev/null; then
	# We have color support; assume it's compliant with Ecma-48
	# (ISO/IEC-6429). (Lack of such support is extremely rare, and such
	# a case would tend to support setf rather than setaf.)
	color_prompt=yes
    else
	color_prompt=
    fi
fi

if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
unset color_prompt force_color_prompt

# If this is an xterm set the title to user@host:dir
case "$TERM" in
xterm*|rxvt*)
    # PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"
    PS1="\[\e[01;32;36m\]\u\[\e[37;33m\]@\h: \[\e[36;32m\]\w\[\e[0m\]\\$ "
    ;;
*)
    ;;
esac
```
## SSR
```bash

```
## chrome
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
## VScode
```bash
```
[VsCode通过SSH连接远程服务器开发](https://www.cnblogs.com/chnmig/p/12160248.html)

## sogou 
```bash
sudo apt install fcitx
wget https://ime.sogouimecdn.com/202108250027/b6abc77d89542b7352010c7cd7e88b36/dl/index/1612260778/sogoupinyin_2.4.0.3469_amd64.deb
sudo dpkg -i sogoupinyin_2.4.0.3469_amd64.deb
sudo apt -f install
```
[Ubuntu搜狗输入法安装指南](https://pinyin.sogou.com/linux/help.php)
[ubuntu18.04安装搜狗输入法](https://jingyan.baidu.com/article/6c67b1d6d304f76687bb1e94.html)

## VPN
### v2ray
[Linux配置v2ray详细教程-Ubuntu为例](https://mahongfei.com/1776.html)
如果需要不挂VPN访问外网，需要在setting network中disable代理

### ssr electron-ssr
download: [electron-ssr-backup](https://github.com/qingshuisiyuan/electron-ssr-backup/releases)
用ubuntu software安装
导入链接
在ubuntu setting network中设置代理

### 利用proxychains让命令走代理
```bash
sudo apt install proxychains
sudo vim /etc/proxychains.conf
socks5 127.0.0.1 1080 #端口需要根据代理软件设置
proxychains wget https://www.google.com
```
## Anaconda
```bash
wget https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
./Anaconda3-2021.05-Linux-x86_64.sh
```
## miniconda
```bash
wget -c https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh

vim ~/.bashrc
export PATH=$PATH:/home/twilight/miniconda3/bin
```
[【Linux】conda: command not found解决办法](https://blog.csdn.net/weixin_38705903/article/details/86533863)
[conda activate激活环境出错的解决办法](https://blog.csdn.net/qq_33825817/article/details/88959785)

uninstall miniconda
```bash
cd ~/
rm -rf miniconda
code ~/.bashrc
delete conda initiation
```
## sogou 
```bash
sudo apt install fcitx
wget https://ime.sogouimecdn.com/202108250027/b6abc77d89542b7352010c7cd7e88b36/dl/index/1612260778/sogoupinyin_2.4.0.3469_amd64.deb
sudo dpkg -i sogoupinyin_2.4.0.3469_amd64.deb
sudo apt -f install
```
[Ubuntu搜狗输入法安装指南](https://pinyin.sogou.com/linux/help.php)
[ubuntu18.04安装搜狗输入法](https://jingyan.baidu.com/article/6c67b1d6d304f76687bb1e94.html)

```bash
```
```bash
```
```bash
```
```bash
```
```bash
```
```bash
```
```bash
```
```bash
```
```bash
```
```bash
```
