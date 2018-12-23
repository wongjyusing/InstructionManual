## 配置python
由于ubuntu16.04自带的python3是3.52版本。  
无法使用`f'hello {name}!'`特性。（这个是python3.6之后才有的特性）  
而删除自带的3.52版本呢，又很容易出现各种错误。  
且系统自带的python在后续安装和使用Django、Scrapy、Pandas等库的时候出现各种问题。  
虽然之前记录过修改的方法和流程。配置下来也要两三个小时。  
故此，选择了[Anaconda](https://www.anaconda.com/)（注意，右键，在新的标签页打开，gitbook上不知道怎么设置新的标签页打开）  
在[Anaconda](https://www.anaconda.com/)的官网选择对应的版本进行下载。  
这里只介绍在linux上安装方法。   
下载完成后，文件通常都是在`/home/username/Download`里面。  
把终端切换到Download里面。  
输入`bash Ana`，然后按一下`tab`键，就可以自动补全命令了。  

如果是安装了**zsh**的话执行下面的做法。   
输入`zsh Ana`，然后按一下`tab`键，就可以自动补全命令了。  

命令会补全成  
`bash Anaconda3-5.2.0-Linux-x86_64.sh`  
或  
`zsh Anaconda3-5.2.0-Linux-x86_64.sh`  
这个会根据下载的版本号来决定的。   
运行代码后，根据提示按下回车，直到提示你输入**yes or no**,  
这里毫无意外肯定是输入**yes**
等待它安装，中途会询问你安装到那个文件夹，正常按下`回车`即可，安装到用户的根目录下。  
如果你有其他需求可以设定其他的目录下。  
继续等待安装，然后又出现一个对话框问你是否把Anaconda添加到环境变量中，选择**yes**  
最后，Anaconda安装完成后会询问你是否安装**VScode**，这个根据自身需求吧。我没有安装，输入**no**即可。  
## 检查是否安装成功  
关闭当前终端，新开一个终端。  
输入`python`  
可以看到python变成3.61了。  
当然未来的你可能会看到3.7或3.8甚至4.x。   
如需使用3.6版本。  
只需要执行下面的命令即可。  
`conda install python=3.6`  
## python仍然是2.7的处理方法   
原因是因为，安装了**zsh**的情况下仍然执行`bash Anaconda3-5.2.0-Linux-x86_64.sh` 进行安装。  
导致Anaconda的环境变量未加入到zsh中。   
需要依次执行下方命令。（注意，需要把下面路径中的username替换成你的用户名）   
`echo 'export PATH="/home/username/anaconda3/bin:$PATH"' >> ~/.zshrc`    
重新加载配置文件  
`source ~/.zshrc`
