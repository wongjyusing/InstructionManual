## node.js安装
打开[node.js官网](https://nodejs.org/en/)下载左边的按钮。  
下载完成后，文件通常都是在Download目录下。  
把终端切换到Download里面。  
在/usr/local/lib下创建一个名为**nodejs**的目录  
`sudo mkdir /usr/local/lib/nodejs`  
解压下载的源代码到`/usr/local/lib/nodejs`中   
`sudo tar -xJvf node-`  
按下`tab`键自动补全成`sudo tar -xJvf node-v8.11.4-linux-x64.tar.xz`  
注意，不要按下回车 ，上面的版本是根据你下载的版本而有所不同。  
继续输入后续的内容，如下：   
`sudo tar -xJvf node-v8.11.4-linux-x64.tar.xz -C /usr/local/lib/nodejs`  
等待解压完成。  
把/usr/local/lib/nodejs下的目录进行更换目录名。  
`sudo mv /usr/local/lib/nodejs/node-node-v8.11.4-linux-x64 /usr/local/lib/nodejs/node-v8`  
注意上面的命令是一条命令，不要分开了。其中的版本号需要自行更改。  
### 加入环境变量  
`sudo vim ~/.profile`  
修改目录权限  
```bash
sudo chmod -R 777 /usr/local/lib/nodejs
```
在末尾根据安装的路径自行更改目录  
```bash
export NODEJS_HOME=/usr/local/lib/nodejs/node-$VERSION/bin
export PATH=$NODEJS_HOME:$PATH
```
加载配置  
`. ~/.profile`  
注意，上面命令开头有个句点。   
输入`node -V`检查是否安装成功。  
