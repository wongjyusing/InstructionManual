## 新系统的配置
### 目录语言
通常情况下，我们在安装桌面系统的时候会选择**简体中文**作为系统语言。  
而导致我们平时使用终端，会出现中文路径。  
经常需要切换输入法。  
举个例子，我想在桌面创建一个名为test的目录。  
而我们在终端则需要输入
```bash
mkdir /home/username/桌面/test
```  
这个很不符合我们日常的使用。  
所以，需要依次执行下面的步骤。  
```bash
#将语言环境设为英文。
export LANG=en_US
#更新配置  
xdg-user-dirs-gtk-update

#然后会出现一个对话框，问你是否把目录转为英文，点击同意。  
#将语言环境设为简体中文  
export LANG=zh_CN
```
收藏这个页面后，重启电脑。  
重启进入电脑后会出现一个对话框，系统会问你是否把目录设为中文，  
**勾选不再提示**，点击保留原来的目录。ok，搞掂。
### 更换软件源
命令行方式太麻烦了，用图形界面更换吧。  
按下Win键，输入`setting`点击齿轮的图标   
看到系统栏有个**软体和更新**，点击它。  
里面有个**下载自：中国的服务器**， 点击它，选择其他站点。  
然后找到阿里云的链接**mirrors.aliyun.com**,选择它，输入密码后，关闭。  
最后点击**重新载入**，等待运行完毕即可。  
### 设置root用户密码   
打开终端
按下：`Ctrl` + `Alt` + `T`  
输入`sudo passwd root`  
输入两次你要设置root账户的密码  
再输入`su root`测试是否能进入root模式  
出现‘#’号说明成功了  
切换到普通用户 `su username`这里的username是你自己装机时设定的用户名。  
## 优化  
### 删除不常用的软件
输入命令：  
`sudo apt-get remove thunderbird totem rhythmbox simple-scan gnome-mahjongg aisleriot gnome-mines cheese transmission-common gnome-orca webbrowser-app gnome-sudoku onboard deja-dup`  
上面的内容要一次复制完哦。   
### 升级软件包  
执行下方的命令，以免后续安装某些软件出现错误   
`sudo apt update && sudo apt upgrade`  
## 安装常用的软件  
输入下面的命令会安装git、tree、gdebi、vim。  
```bash
sudo apt install git tree gdebi vim
```  
这里讲一下**gdebi**，它是一个deb包的安装软件。  
可以减少安装deb文件的出错几率的同时会安装deb包所需要的依赖。   
## 美化  
### 安装unity-tweak-tool
`sudo apt-get install unity-tweak-tool`  
可以到这位博主写的文章[不美翻怎么开发!Ubuntu 16.04 LTS深度美化!(2017年度定稿版)](https://www.jianshu.com/p/4bd2d9b1af41)
里面有很多漂亮的主题和字体可以预览再选择下载，然后通过**unity-tweak-tool**进行设置。  
### 安装oh-my-zsh
**安装zsh**  
`sudo apt-get install zsh`  
**设置zsh为默认shell，如果提示权限不够，在开头加上sudo**  
`chsh -s $(which zsh)`   
请确认没有在下载文件，有文件修改未保存的，不然后果就是这篇博文就写了两次。  
重启电脑。      
**安装curl**  
 这里需要curl下载oh-my-zsh  
 `sudo apt-get install curl`  
 **下载oh-my-zsh**  
 `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`  
**更换oh-my-zsh主题**  
 安装完成后，选择喜欢的主题吧，可到[oh-my-zsh主题](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)进行预览，选择好喜欢的主题，把名字记下。  
 `sudo gedit  ~/.zshrc`  
 然后按下`Ctrl` + `F` 搜索**ZSH_THEME="robbyrussell"**，把robbyrussell替换成喜欢的主题名字，我选择的时**ys**这个主题。
