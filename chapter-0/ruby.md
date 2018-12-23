## 安装Ruby  
安装ruby最好是使用RVM进行安装。  
先到[rvm的官网](https://rvm.io/)复制依次复制两条命令。   
```bash
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

\curl -sSL https://get.rvm.io | bash -s stable
```
安装完成后，选择稳定的版本进行安装  
`rvm list known`  
目前选择是2.5.1  
`rvm install 2.5.1`  
安装完成后，输入`ruby -v`  
如果出现错误。说明没有配置环境变量。   
终端下的依次输入下面的语句即可成功。（注意，需要把下面路径中的username替换成你的用户名）    
`echo 'export PATH="/home/username/.rvm/rubies/ruby-2.5.1/bin:$PATH"' >> ~/.zshrc`  
加载配置文件   
`source ~/.zshrc`  
