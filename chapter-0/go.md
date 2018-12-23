## 安装Go
首先到[官网的下载页面](https://golang.org/dl/)右键复制linux版本的链接。  
命令行输入`wget https://dl.google.com/go/go1.11.2.linux-amd64.tar.gz`  
这样下载比浏览器下载快多了。   
下载完成后解压到`/usr/local/`目录下。
`sudo tar -zxf go1.11.2.linux-amd64.tar.gz -C /usr/local/`
配置环境变量  
`sudo vim ~/.zshrc`  
写入以下内容
```bash
export GOPATH=/usr/local/go
export PATH=$GOPATH/bin:$PATH
export GOROOT=/usr/local/go
export GOPATH=$PATH:$GOROOT/bin
```
加载环境变量
`source ~/.zshrc `
输入`go version`查看版本
