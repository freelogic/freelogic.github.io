---
layout: post
title: 2018-05-27-computer-using-hints-电脑使用帮助
key: 20180527
tags: ubuntu cuda cudnn tensorflow gym qq ssh
modify_date: 2018-05-27
---

# 2018-05-27-computer-using-hints-电脑使用帮助


说明：
* 本文发布于: [gitee](http://freelogic.gitee.io/webpost/),[github](https://freelogic.github.io/),[博客园](http://www.cnblogs.com/taichu/)
* 转载和引用请指明原作者和连接及出处.


内容和使用:
* 此文为了将hints做成静态页面而方便大家查看及互相链接,您还可以访问它的源码项目(多个相同的镜像):
  * [gitee(https://gitee.com/freelogic/computer-using-hints.git)](https://gitee.com/freelogic/computer-using-hints.git);
  * [github(https://github.com/freelogic/computer-using-hints.git)](https://github.com/freelogic/computer-using-hints.git);
  * [gitlab(https://gitlab.com/freelogic/computer-using-hints.git)](https://gitlab.com/freelogic/computer-using-hints.git);
* 建议您通过本page的页内搜索来查找关键字及相关内容,当前主流浏览器都有"页内搜索"功能;


正文:

## Content
* 1-Basic OS Hints
  * 1.1-Ubuntu
    * 1.1.1-Ubuntu18.04如何切换默认的python版本?
    * 1.1.2-Ubuntu18.04如何安装摆渡云盘客户端(不是摆渡云同步客户端)?
    * 1.1.3-如何通过ssh终端(比如在WIN10)登录Ubuntu18.04平台?
    * 1.1.4-Ubuntu18.04如何安装QQ?
    * 1.1.5-Ubuntu18.04如何安装chrome?
    * 1.1.6-Ubuntu18.04如何安装pycharm?
    * 1.1.7-Ubuntu下如何安装循环依赖的lib库?
    * 1.1.8-Ubuntu18.04解决USB无线鼠标插入后无法使用的问题? 
    * 1.1.9-Ubuntu18.04下计算SHA1和MD5值? 
    * 1.1.10-Ubuntu18.04下文件目录比较工具(类似beyondcompare)?     
    * 1.1.11-Ubuntu18.04下安装类似notepad++的文本工具   
    * 1.1.12-Ubuntu18.04下安装OCR工具(tesseract)
    * 1.1.13-Ubuntu18.04下调节字体和鼠标样式及大小
    * 1.1.14-Ubuntu18.04下测网速
    * 1.1.15-查看Ubuntu18.04的硬件配置
    * 1.1.16-Ubuntu18.04的apt-get命令如何安装指定版本?
    * 1.1.17-Ubuntu18.04的ufw的简易防火墙操作
* 2-Special Topic Hints
  * 2.1-Programming
    * 2.1.1-版本管理
      * 2.1.1.1-GIT 
        * 2.1.1.1.1-如何从本地PUSH分支改动到多个远端GIT仓库(假设远端GIT仓库为多个备份镜像库且内容相同) ?
      * 2.1.1.2-GIT仓库
        * 2.1.1.2.1-无法注册新GITLAB帐号且忘记老帐号密码怎么办?
    * 2.1.2-JAVA
      * 2.1.2.1-JDK 
        * 2.1.2.1.1-JDK安装
    * 2.1.3-DataBase
      * 2.1.3.1-MYSQL 
        * 2.1.3.1.1-MYSQL的安装
    * 2.1.4-Testing
      * 2.1.4.1-JMeter 
        * 2.1.4.1.1-JMeter的安装
        * 2.1.4.1.2-JMeter的分布式测试
  * 2.2-机器学习
    * 2.2.1-环境安装 
      * 2.2.1.1-ubuntu   
        * 2.1.1.1.1-ubuntu18.04环境安装机器学习环境TF的三件套CUDA-CUDNN-TENSORFLOW    
        * 2.1.1.1.2-ubuntu18.04环境安装OpenAI的GYM的强化学习环境 
  * 2.3 大数据
    * 2.3.1-日志 
      * 2.3.1.1-ELK   
        * 2.3.1.1.1-安装ELK   
* 3-END




## 1. Basic OS Hints

### 1.1 Ubuntu

#### 1.1.1 Ubuntu18.04如何切换默认的python版本?
* ubuntu18.04切换默认python的方法:
  * 参考: [https://segmentfault.com/q/1010000003713912](https://segmentfault.com/q/1010000003713912)
  * 命令:
  
    ```
    
    # 定义2种python版本
    sudo update-alternatives --install /usr/bin/python python /usr/bin/python2 100     
    sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 150
    
    # 如下命令用来切换
    sudo update-alternatives --config python
    
    ```

#### 1.1.2 Ubuntu18.04如何安装摆渡云盘客户端(不是摆渡云同步客户端)?
* ubuntu18.04安装摆渡云盘客户端(不是摆渡云同步客户端)
  * 参考:[https://blog.csdn.net/tao_627/article/details/45007637](https://blog.csdn.net/tao_627/article/details/45007637)
    * 这个链接有bcloud3.9.1安装包,它是能找到的最新版本,已放入个人云盘"我的程序\ubuntu\"位置;
    * bcloud其实都是社区和个人自己维护的源码!3.9.1版本已测可用;
  * 安装参考:[https://blog.csdn.net/qq_37163122/article/details/78169072](https://blog.csdn.net/qq_37163122/article/details/78169072) 

#### 1.1.3 如何通过ssh终端(比如在WIN10)登录Ubuntu18.04平台?
* 用ssh登录ubuntu18.04
  * 原理:默认ubuntu系统安装后有ssh,而没有sshd,所以其他服务器/PC无法通过ssh协议来远超登录ubuntu,需要如下操作:
  
  ```
  
    安装参考:https://jingyan.baidu.com/article/359911f5a5b74857fe0306c4.html
    # 查看Ubuntu是否已经安装或启用了ssh服务
    ps -e |grep ssh
    # 如果只有ssh-agent,则它是ssh-client客户端进程;
    # 如果没有sshd进程,则需要继续安装ssh的server模块,他是OS的一部分;
    
    # 安装sshd
    sudo apt install openssh-server

    #开启/关闭ssh服务命令：
    sudo service ssh start  #手动启动服务
    sudo service ssh stop   #手动关闭服务
    sudo service ssh status #查询服务状态
    
  ```

#### 1.1.4 Ubuntu18.04如何安装QQ?
* install QQ
  * Best way is use "[WEBQQ(http://web2.qq.com/)](http://web2.qq.com/)" instead of install local program;
  * WEBQQ is an URL, you can make a URL link icon on desktop of ubuntu;

#### 1.1.5 Ubuntu18.04如何安装chrome?
* install chrome
  * Best way is to download chrome's deb package and use "sudo dpkg -i google-chrome-stable_current_amd64.deb" to install;
  * Notes: after 'deb' downloaded, don't click on it to install automaticly, it maybe report error and use command above suggested to install it in terminal;

#### 1.1.6 Ubuntu18.04如何安装pycharm?
* install pycharm
  * ubuntu18.04的最新的"软件/software"当中可以搜到"pycharm",但是双击自动安装多次失败,所以建议用如下普通方式安装;
  * 下载免费社区版本的pycharm包,然后执行"\bin\pycharm.sh"脚本,就启动了图形界面,建议拖动到ubuntu的desktop做个链接,方便下次启动;
  * 配置python解析器: 从"setting"配置界面,搜索关键字或直接找到"Project Interperter",然后根据情况选择;
    * 一般安装完pycharm后它自动感知OS系统,可能会发现多个python解析其, 比如ananconda,或系统的python3,或python2等等;
    * 建议你选anaconda或os自带, 然后pycharm会自动探测其依赖库的更新,每次启动pycharm,一般会更新index,其实就是"扫库"看是否安装了新lib库;
    * 比如: 你anaconda命令行下用"conda"命令安装了python模块AAA,而os的python3下这个模块AAA没有安装,则pycharm如果使用os的python3则不会重建lib的index;
    * 参考:https://www.cnblogs.com/fanmu/p/8010580.html
    
#### 1.1.7 Ubuntu下如何安装循环依赖的lib库?  
* 解决ubuntu下用命令"apt-get"安装有循环依赖的一组lib库的问题
  * 问题:ubuntu下使用"apt-get"来安装lib1库,但lib1依赖lib2,而lib2又依赖lib3和lib4,但最终lib4可能还依赖lib1,循环了;
  * 解决:其实,你没法单独安装lib库;只要"sudo apt-get install lib1,lib2,lib3,lib4" //将循环依赖库一并写上,同时安装就行

#### 1.1.8 Ubuntu18.04解决USB无线鼠标插入后无法使用的问题? 
* 解决UBUNTU18.04插入USB无线鼠标无效的问题
  * 问题: ubuntu18.04可能默认在电池模式会关闭USB端口,则USB鼠标插入无法使用;
  * 解决: 插入电源,笔记本电脑就能堆新接入的无线USB鼠标感知并能使用了;
  * TODO:暂未找到如何设定ubuntu18.04在电源模式下禁用或弃用USB设备(如USB的WIFI鼠标)的配置;

#### 1.1.9 Ubuntu18.04下计算SHA1和MD5值? 
* ubuntu下计算sha1/md5值
  * 参考: [http://blog.sina.com.cn/s/blog_15e13208d0102w54j.html](http://blog.sina.com.cn/s/blog_15e13208d0102w54j.html)
  * 命令: md5sum ./hoek-2.16.3.tgz > ./hoek-2.16.3.tgz.md5.txt    //假设你下载了tgz到当前目录
  * 命令: sha1sum ./hoek-2.16.3.tgz > ./hoek-2.16.3.tgz.sha1.txt   //假设你下载了tgz到当前目录

#### 1.1.10 Ubuntu18.04下文件目录比较工具(类似beyondcompare)?
* Ubuntu下有免费工具meld,它非常类似beyondcompare,可以比较目录和文件,很好用!
  * 安装: 在ubuntu搜索关键字"软件",打开"软件"(类似app store或安装应用商店)后,在它里面搜索关键字"meld",直接安装和启动;

#### 1.1.11 Ubuntu18.04下安装类似notepad++的文本工具 
* ubuntu下不能直接安装notepad++,但可以安装其家族的名为"notepadqq"的linux版本;
  * 参考:[Ubuntu 16.04安装Notepadqq编辑器替代Notepad++](https://www.cnblogs.com/EasonJim/p/7225861.html)
  * 安装:
  
  ```
    sudo add-apt-repository ppa:notepadqq-team/notepadqq
    sudo apt-get update
    sudo apt-get install notepadqq
  ```

#### 1.1.12 Ubuntu18.04下安装OCR工具(tesseract)
* ubuntu下的OCR工具不多(至少没有win下的金山OCR,汉王OCR,紫光OCR等等),但免费预装的tesseract就非常好!
  * ubuntu18.04自带tesseract4.00版本,可以识别中英文(中文识别需如下安装中文包),测试效果还不错,超过一些在线OCR网站(收费或免费),它是最新LSTM的神经网络及机器学习的内容,可以进一步学习;
  * 安装:
  
  ```
  
    sudo apt-get install tesseract-ocr  //发现ubuntu18.04已经安装了最新的4.00版本
    sudo apt-get install tesseract   //同上
    sudo apt-get install tesseract-ocr-chi-sim //安装额外的中文简体识别包
    tesseract //查看命令的格式和参数
    tesseract --list-langs //查看支持的语言
    tesseract ./yangpu-xiaoxue.jpg yangpu-xiaoxue.txt -l chi_sim  //进行识别命令并输出结果txt文件;
    # 性能说明: 中文识别(4MB的JPG包含2列450行文字)运用到了4个core,大约30秒左右,未查是否使用了GPU,仅供参考;
  
  ```
  
  * 参考1:[https://blog.csdn.net/dcrmg/article/details/78128026](https://blog.csdn.net/dcrmg/article/details/78128026)
  * 参考2(详细):[https://blog.csdn.net/yimingsilence/article/details/51353772](https://blog.csdn.net/yimingsilence/article/details/51353772)
  * 第三方UI界面软件: 在ubuntu的"软件/software"中查找"gimagereader"关键字并安装它,它是tesseract的一个UI界面,非常好用!
  * 缺陷:tesseract不能自动转换为带表格的XLS文件格式,而某些在线OCR(如下),或win下的OCR支持中文版面识别,能将table转换为XLS的表格导出;
  * 其他OCR: 在线OCR有免费和收费版本,较多,推荐这个,它自持表格识别并转换为xls表格,免费的最大能识别10MB以上的JPG;
    * [https://zhcn.109876543210.com/](https://zhcn.109876543210.com/)

#### 1.1.13 Ubuntu18.04下调节字体和鼠标样式及大小
* 配置ubuntu18.04的字体大小和鼠标大小
  * 参考: [https://jingyan.baidu.com/article/a681b0de6ad12c3b1943466d.html](https://jingyan.baidu.com/article/a681b0de6ad12c3b1943466d.html)
  * 说明: 虽说据悉ubuntu18.04弃用了unity界面,但还是根据参考资料,尝试并确认了如下方法可用;
    * 命令: sudo apt-get install unity-tweak-tool  //安装了untiy tweak配置台;
    * 完成后请搜索"tweak"关键字, 找到并打开tweak后,可以font样式大小,也可以配置鼠标样式大小(但大小不能自由调节);

#### 1.1.14 Ubuntu18.04下测网速
* ubuntu18.04的网络测速
  * 问题: 因网络不稳定,尤其是路由器滚烫,网络连不上,所以想测试网速,而ubuntu没有类似win下360的宽带测速器,方法如下;
  * 参考: [https://www.cnblogs.com/linuxprobe/p/5728126.html](https://www.cnblogs.com/linuxprobe/p/5728126.html)
  * 命令: 
    
    ```
    
    sudo apt-get install speedtest-cli  //安装speedtest-cli, 及设你是python3且升级到pip3命令
    speedtest-cli --h  //查看帮助
    speedtest-cli --share  //执行网络测速命令
    speedtest-cli --list   //获取测速使用的speedtest网站配置的各个目标网站的名字和距离公里数的大列表;
    
    ```
  * 在线UI界面: speedtest也提供在线界面供查看测试过程和结果:[http://www.speedtest.cn/]()http://www.speedtest.cn/)

#### 1.1.15 查看Ubuntu18.04的硬件配置
* 查看ubuntu硬件配置
  * 方法1: 命令sudo lshw  //返回CPU/MEM/DISK/GPU/USB等信息
  * 方法2: 在搜索中输入"system", 打开"system profiler and benchmark", 其实就是将lshw的图形化,看起来方便而已;
* 特别主义,ubuntu这个linux系统,对于笔记本电脑的充电模式或电池模式的切换处理,及USB设备的激活等,不是特别好,建议:
  * 如果无线USB/WIFI鼠标,甚至touchpad和键盘无效了,请插入电源再试试看;
  * 或者因为电源模式变化,导致无法登录,鼠标动但键盘无效无法输入密码,则可以尝试短按power键来休眠并恢复,尝试激活键盘;

#### 1.1.16 Ubuntu18.04的apt-get命令如何安装指定版本?
* apt-get安装指定版本
  * 命令: sudo apt-get install package=version
  
#### 1.1.17 Ubuntu18.04的ufw的简易防火墙操作
* ubuntu的ufw安装和使用
  * TODO: ubuntu的ufw安装和使用  


## 2. Special Topic Hints

### 2.1 Programming

#### 2.1.1 版本管理

##### 2.1.1.1 GIT 

###### 2.1.1.1.1 如何从本地PUSH分支改动到多个远端GIT仓库(假设远端GIT仓库为多个备份镜像库且内容相同) ?
* 参考: 请自查摆渡/谷歌/BING,关键字"git push到多个远端仓库";
* 方法: 项目目录下有个隐藏的".git"目录,修改其下的配置文件".git\config":
   
   ```
   
   # 在.git\config文件添加如下独立小节,"<>"之间内容需根据实际情况变化,以下是举例:
     [remote "all-remote-git(gitee/github/gitlab)"]
     url = https://gitee.com/<user-account>/<repo-name>.git
     url = https://github.com/<user-account>/<repo-name>.git
     url = https://gitlab.com/<user-account>/<repo-name>.git

   ```

##### 2.1.1.2 GIT仓库

###### 2.1.1.2.1 无法注册新GITLAB帐号且忘记老帐号密码怎么办?
* 如果无法注册GITLAB帐号,可能是因为register new account需要用到google的认证图形识别控件,但国内被墙了,请翻墙再测试;
  * 你也可以用github帐号,授权其登录gitlab,一样用,还更方便和一致,忘记密码也可以恢复如下描述;
* 如何进入gitlab帐号(忘记密码和关联email的情况下)?
  * 如果gitlab帐号和github同名或绑定; 那么用github帐号登录到gitlab当中, 然后可以修改password和关联email;

#### 2.1.2 JAVA

##### 2.1.2.1 JDK 

###### 2.1.2.1.1 JDK安装
* ubuntu18.04 安装JDK1.8
  * 参考: [https://blog.csdn.net/u010307119/article/details/52081429](https://blog.csdn.net/u010307119/article/details/52081429);
    * 含多版本JDK的默认配置修改,最后部分描述,如果只安装一个版本的JDK就不需要设定默认级别并启用了.
  * 下载: http://www.oracle.com/technetwork/java/javase/downloads/java-archive-javase8-2177648.html
    * 需注册oracle帐号,随意用一个email注册就行;
  * 安装: 
  
  ```
  
  sudo tar xvzf jdk-8u102-linux-x64.tar.gz //解压二进制安装包(非源码包需要编译)
  sudo chmod 777 /etc/profile   //如果profile文件是644模式,可以先转变为777,修改完了再chmod回去;
  sudo vi /etc/profile  //配置环境文件
  #在profile文件尾部添加
      #set java environment
      export JAVA_HOME=/home/goodong/Downloads/jdk1.8.0_162 
      export JRE_HOME=${JAVA_HOME}/jre  
      export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
      export PATH=${JAVA_HOME}/bin:$PATH

  java -vesion 或 javac //测试java安装是否正常,显示出版本号则算完成; 

  #多JDK版本设定:
    sudo update-alternatives --install "/usr/bin/java" "java" "/home/youraccount/tool/jdk1.8.0_162/bin/java" 1 
    设置JRE可用: sudo update-alternatives --install "/usr/bin/javac" "javac" "/home/youraccount/tool/jdk1.8.0_162/bin/javac" 1 
    设置JDK可用: sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/home/youraccount/tool/jdk1.8.0_162/bin/javaws" 1 
    设置Java Web可用: sudo update-alternatives --set java /home/youraccount/tool/jdk1.8.0_162/bin/java 
    设置Java运行时环境: sudo update-alternatives --set javac /home/youraccount/tool/jdk1.8.0_162/bin/javac 
    设置Javac编译器:  sudo update-alternatives --set javaws /home/youraccount/tool/jdk1.8.0_162/bin/javaws

  # 其他JDK版本情况: JDK9据悉不太好用,JDK10目前较新,用的人不多,还需要观察!

  ```
  
#### 2.1.3 DataBase

##### 2.1.3.1 MYSQL 

###### 2.1.3.1.1 MYSQL的安装
* ubuntu下安装mysql
  * 参考: [https://ask.csdn.net/questions/376087](https://ask.csdn.net/questions/376087), 释放tar.gz版本并安装;
  * 错误1: /usr/local/mysql3306/bin/mysqld: error while loading shared libraries: libaio.so.1: cannot open shared object file: No such file or directory;
    * 则需安装 sudo apt-get install libaio-dev  //安装mysql需要的库

```

    修改默认密码: mysql安装的时候会提示,其默认root的密码是"#P;eijqF<1Y6",千万别忘记,记录下来,
                然后登录后mysql会会被要求必须马上修改密码并提示错误如下：You must reset your password using ALTER USER statement before executing this statement. 
                你可以执行如下命令(参考:https://blog.csdn.net/dotalee/article/details/72576667)
    ALTER USER 'root'@'localhost' IDENTIFIED BY '12345678' PASSWORD EXPIRE NEVER;	//重设密码且永不过期
    ./mysqladmin -u root -p shutdown //关闭mysql (参考链接:https://blog.csdn.net/zyc_love_study/article/details/74347977)
    ps -ef|grep mysql  //查看mysql进程;

```

#### 2.1.4 Testing

##### 2.1.4.1 JMeter 

###### 2.1.4.1.1 JMeter的安装
* 参考: [https://www.cnblogs.com/EasonJim/p/7443875.html]()https://www.cnblogs.com/EasonJim/p/7443875.html)
* 官网老版本下载链接: [ https://archive.apache.org/dist/jmeter/binaries/](https://archive.apache.org/dist/jmeter/binaries/)
* 安装: 
    
    ```
    
    tar -zxvf apache-jmeter-4.0.tgz    //解压缩二进制包
    sudo mv apache-jmeter-4.0 /usr/local/apache-jmeter-4.0/        //拷贝到合适的目录
    sudo ln -s /usr/local/apache-jmeter-4.0/ /usr/local/jmeter     //建立软链接,是调用时候不用了解版本,方便以后升级,方法类似cuda的安装和配置
    /usr/local/jmeter/bin/jmeter.sh  //启动jmeter
    ps -ef|grep jmeter   //查看进程并可kill杀掉无用jmeter进程
    
    ```

###### 2.1.4.1.2 JMeter的分布式测试
* 分布式JMETER使用指南
  * A.场景: 
    * 1台win10(master兼slave)；1台linux的slave; 两者同一网段,能ping通(如果不同网段TCP包能路由到也行);
      * master是主控jmeter,slave(也叫agent)是受控jmeter,master自己也可以作为一个slave被自己控制;
    * master如果独自自己使用,直接启动"../bin/jmeter"就行(win10下是运行"..\bin\jmeter.bat");
    * agent需要被控制,则应该先自行启动"../bin/jmeter-server"就行(win10下是运行"..\bin\jmeter-server.bat");并等待被master控制和启停任务;
    * 如果master自己也做为一个agent来运行测试脚本,而且自己也作为主控master,则必须先参照agent启动"jmeter-server"命令,然后再启动用于主控的"jmeter"命令;
    * 以上是简述场景情况及启动顺序,具体配置如下,配置妥当方能启动命令,执行主控和被控的多个jmeter来分布式执行test脚本,联合压测;

  * B.配置agent(slave)受控jmeter端:
    * 在agent机器上需修改"..\jmeter\bin\jmeter.properties",如下:
      * remote_hosts=10.30.33.121:1099   //121是agent本机内网IP,端口一般为1099,不清楚则不要修改;
      * server.rmi.ssl.disable=true  //默认是注释掉的,如果不想要设定ssl(安全但配置复杂),则必须在这行显式的设定为true,以便jmeter知道关闭ssl的使用!
    * 在agent机器上还要修改启动脚本"..\jmeter\bin\jmeter-server",如下:
      * RMI_HOST_DEF=-Djava.rmi.server.hostname=10.30.33.121  //默认是注释掉的,因jmeter可能有BUG,会报错,则需打开,并添加agent的IP;
      * ${DIRNAME}/jmeter ${RMI_HOST_DEF} -Dserver_port=${SERVER_PORT:-2099} -s -j jmeter-server.log "$@"  //仅修改为2099端口,为了不合1099端口冲突;
        * 如果是win环境,则"..\jmeter\bin\jmeter-server"内容和ubuntu下不同,也不能如此配置,目前看win下没有bug,无需修改此命令文件;
    * 启动agent机器,运行"..\jmeter\bin\jmeter-server"  //用&结尾放在后台运行也行,但看不到log输出,建议前台运行;
      * terminal里面看到"Created remote object: UnicastServerRef2 [liveRef: [endpoint:[10.30.33.121:32881](local),objID:[-a8824d7:16390698d96:-7fff, 3759878571045247869]]]"则agent启动正常,等待master管理；
      * master机器自己也作为agent的话,同样需要先配置如上并启动,等待自己的另一个主控进程接管;
      * agent收到master的任务的下发和任务结束式,会打印log"...start..."和"...finish";
      * 可以将agent的log级别调为debug模式,方便排错;具体配置文件是"log4j2.xml"
  
  * C.配置master主控jmeter端:
    * master机器上需修改"..\jmeter\bin\jmeter.properties",如下:
      * remote_hosts=10.30.33.121:2099, 10.30.33.122:1099   //2099是匹配上述agent121的,而1099是master自己也作为agent用的默认1099,两者也可以一样;
      * server.rmi.ssl.disable=true  //这个配置和agent一样,都显式关闭ssl;   
      * win10版本的jmeter4.0的jmeter-server.bat没有bug,无需修改!而如果是linux做agent,则脚本jmeter-server就要如上述agent来修改!
    * master机器也希望能作为agent工作,那么需先启动"jmeter-server.bat"命令;
      * win操作系统下的"jmeter-server.bat"命令无BUG,所以无需像上述B当中的描述来修改linux下的"../jmeter/bin/jmeter-server"命令;
    * 启动jmeter.bat主控程序;
      * 启动分布式测试任务: 在"start remote"菜单的子菜单看到了所有agent的列表(举例有121和122自己)；可以单个或全部启动agent；
        * remote的操作,容易超时,容易返回错误,建议一个个启动agent,如果数量不多的话;网络好,机器快,脚本简单则可以一起启动;
      * 启动单机模式测试任务: 即便在以上情况,agent都在线能看见受控,但也可以不用菜单"start remote", 而直接用"start"菜单来忽略分布式任务下发,而让master当作单机模式使用,自己执行脚本;
      * 分布式模式下,主控master机器上,建议用"聚合报告"查看测试结果,并确认多个agent的CPU/MEM;并用"结果树"只看偶发错误;

  * D.问题排查: 
    * 如果master可以下任务给slave,能通,但debug级别日志报错(jmeter-server.log),可能网络复杂,举例如下:
      * 比如master或slave开了虚拟机和虚拟网卡导致多个IP地址,网络情况复杂,你需要关闭和禁用其他IP,并重新下发任务到agent来尝试;
    * 分布式测试情况下,主控master会分发脚本任务给多个agent,但不会下发数据,需自己拷贝数据(尤其是大量数据);
    * 如果master和agent上面目录不一样,或者1个win和1个ubuntu linux,则测试脚本一旦配置了路径,则格式不对,肯定报错,文件名是通用的;
      * 建议将数据放在"..\jmeter"或"..\jmeter\bin"下,而在脚本中不要配置path,这样就做到了脚本在多个OS下兼容;
    * 如果端口1099,2099等没有通,主控master无法发任务到agent,而不是任务执行时候debug的log日志报错,则多半是防火墙屏蔽了端口port;
      * 建议如果是WIN,进入控制面板,可以设定防火墙的路由规则,可以放开port口的出入,也可以将master/agent的ip都列为全部放开!
      * 如果是linux,比如ubuntu,则可以用iptables防火墙设定规则来放开PORT或IP,因为最新ubuntu18.04简化了iptables,用工具UFW来控制防火墙,请查相关脚本,UFW使用较为方便!

### 2.2 机器学习

#### 2.2.1 环境安装 

##### 2.2.1.1 ubuntu   
   
###### 2.2.1.1.1 ubuntu18.04环境安装机器学习环境TF的三件套CUDA-CUDNN-TENSORFLOW
* 1.查看nvidia显卡配置

  ```
  
    # 查看N卡GPU的配置
    nvidia-smi
    
    # 查看N卡的图形界面配置
    nvidia-settings 
    
    # 命令:查看nvidia卡型号;
    $ lspci | grep -i nvidia
    # 返回内容: 01:00.0 VGA compatible controller: NVIDIA Corporation GM107M [GeForce GTX 960M] (rev a2)
    
  ```  

* 2.安装cuda的折腾过程
  * 参考(较好): [http://www.zhimengzhe.com/bianchengjiaocheng/qitabiancheng/415560.html](http://www.zhimengzhe.com/bianchengjiaocheng/qitabiancheng/415560.html)
  * 过程简述:
    * 首先尝试记忆中GTX960M显卡只能支持的最高CUDA6+CUDNN5的组合配置安装;
    * 官网查了硬件型号,匹配的就是CUDA6+CUDNN5,因为CUDNN是神经网络NN加速库,主要看cuda;
    * 但很快发现tf官网说即将最低支持cuda8,这怎么办?
    * 查帖子发现也有人在GTX960M上安装CUDA8,所以猜测:只要N卡安装上驱动driver,而driver版本关联到CUDA,cuda关联到cudnn,tf也关联CUDA版本,大胆猜测是这个逻辑;
    * 按照以上逻辑,贪心下载了CUDA9.1,越到了安装问题,解决后发现TF不支持,惨;
    * 找贴发现可以安装多个CUDA版本,只要路径配置得当就行了,不像WIN系统有个黑盒子注册表!
    * 查了TF的GITHUB管网的release里面1.8.0等最新几个release-note信息,并查关键字CUDA,发现只支持到CUDA9.0;于是下决心安装它;
    * NVIDIA官网不用注册就能随意下载CUDA(但CUDNN需要注册下载),速度都很快,于是下载runfile(目前发现,我忘记安装patch补丁,只安装了CUDA9.0的主程序,目前也能用!)
    * 按照上述神贴方法,考虑到ubuntu18.04已经将GTX960M的显卡升级到最新的390的drvier驱动,而且神贴说只要driver版本接近(帖子说AAA.BB小版本BB可以不一样),但我发现CUDA9.0只支持到387,和390很接近,大胆尝试,居然安装上去了.主要安装CUDA9.0的时候不要第一步就安装它自带的才387的driver显卡驱动,否则显卡驱动的安装将极其复杂!
    * 顺利安装完CUDA9.0,按提示和神贴设定路径,然后注册NVIDA官网,下载配套CUDNN712,并同样runfile安装,并参考另外帖子(下面详述)复制文件和做链接及path等;
    * 最后pip3 install tensorflow-gpu
    * 需要keras的就pip3 install tensorflow-gpu

* 3.安装cuda9.1/CUDA9.0/CUDA较高版本(cuda安装包提示最高支持ubuntu17.10,别管它,其实18.04照样安装!没事!)

    ```
    
      A.执行cuda9.X的run安装文件出现问题
    
        Error: unsupported compiler: 7.3.0. Use --override to override this check.
        sudo sh ./cuda_9.1.85_387.26_linux.run --override   //添加这个参数来屏蔽这个报错! 于是可以继续安装了! 看到如下结果,基本OK.
    
    = Summary =
    ===========
    
    Driver:   Not Selected
    Toolkit:  Installed in /usr/local/cuda-9.1
    Samples:  Installed in /home/ya/cuda9-samples
    
    Please make sure that
     -   PATH includes /usr/local/cuda-9.1/bin
     -   LD_LIBRARY_PATH includes /usr/local/cuda-9.1/lib64, or, add /usr/local/cuda-9.1/lib64 to /etc/ld.so.conf and run ldconfig as root
    
    To uninstall the CUDA Toolkit, run the uninstall script in /usr/local/cuda-9.1/bin
    
    Please see CUDA_Installation_Guide_Linux.pdf in /usr/local/cuda-9.1/doc/pdf for detailed information on setting up CUDA.
    
    WARNING: Incomplete installation! This installation did not install the CUDA Driver. A driver of version at least 384.00 is required for CUDA 9.1 functionality to work.
    To install the driver using this installer, run the following command, replacing <CudaInstaller> with the name of this run file:
        sudo <CudaInstaller>.run -silent -driver
    
    Logfile is /tmp/cuda_install_13322.log
    Signal caught, cleaning up
    
    ---------------------
    
    
      B 设定配置(参照上面提示)
    
    $ sudo vim /etc/profile
    在打开的文件末尾，添加以下两行。
    
    64位系统：
    $ export PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}}
    $ export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}} 
    
    32位系统：
    $ export PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}}
    $ export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib ${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
    
      C 安装完毕CUDA9.x,还需安装如下lib
    
    sudo apt-get install freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev
    
      D 最后reboot,并用如下命令测试,看是否安装CUDA9.X正确
    
    $ nvcc -V
    nvcc: NVIDIA (R) Cuda compiler driver
    Copyright (c) 2005-2017 NVIDIA Corporation
    Built on Fri_Nov__3_21:07:56_CDT_2017
    Cuda compilation tools, release 9.1, V9.1.85
    
    ```

* 4.安装cudnn7.1.2(配套CUDA9.X)
  * [官网下载](https://developer.nvidia.com/rdp/cudnn-archive) (需免费注册nvidia会员)
  * 释放后做些拷贝和路径设定就行,参考以上CUDA的神贴,较简单.


* 5.安装TF-CUDA-CUDNN经验
  * 首先,目前GPU做的最好的是N卡(NIVIDA显卡),不仅硬件好,驱动,CUDA平台,CUDNN神经网络加速库都好,远超其他显卡;目前其他显卡无法加速神经网络!!!
  * 其次,你有幸买了N卡,且准备搞深度学习,最著名的开源框架TF(Tensorflow),Pytorch,以及高级库keras等等,一般都支持CUDA/CUDNN,先选其一学习吧;
  * 再则,有了N卡,比如我的GTX960M(游戏本的,但是不打游戏),关键是配套驱动driver要不断升级,比如跟着ubuntu18.04,最新升级到了390.xx的版本;
    * N卡的驱动driver版本AAA.XX(比如390.xx),它配套CUDA,也就是说CUDA库会说明需要drvier升级到何版本,一般xx不同没关系,AAA最好一样;
      * 笔者经验:AAA相差小的没关系,而且新的driver一般向下兼容,旧的AAA就必须升级了;(如果上N卡官网查你的硬件比如GTX960M,它自动匹配的CUDA很低,不要信!否则绝望!)
    * CUDNN是配套cuda的版本的;
    * TF也是配套cuda的版本的;
  * 安装依赖路径: GTX960M-->DRIVER FOR UBUNTU18.04(390.XX) -->CUDA9.0(9.X)-->CUDNN7.1.2/TF1.8.0-->KERAS
    * TF马上最低支持cuda8.0了,请尽快升级driver,以便升级到cuda8/9/..,来使用配套的TF/CUDNN,老硬件N卡照样用!
  * 这里仅仅是我这种硬件软件配置的成功案例,供看管参考,不代表原理和其他软硬件配置都能成功,还需尝试!!!
    * 另外,我CUDA的几个patch忘记安装了,估计是它修改兼容性和BUG的,目前不出其他问题,我就不安装了,怕有问题;

###### 2.2.1.1.2 ubuntu18.04环境安装OpenAI的GYM的强化学习环境
* 1.安装GYM环境
  * 通常做法,用命令: pip3 install gym[all]  //这里假设ubuntu已经安装升级了python3和pip3,且按照上述方法切换默认python为PY3而不是PY2;
  * 问题:一般你会遇到结果提示,Box2D和atari-py安装失败,重复上述命令,再次安装全部gym[all],就更清晰的看到只有此2模块没有安装成功(和win10一致);

* 2.安装swig
  * 如上述2个模块安装失败,发现一个错误是没有swig,和win10一样,到官网下载对应的swig版本,win10下是exe(能成功),ubuntu用命令(能成功);
  * sudo apt-get install swig
  * [swig下载:http://www.swig.org/download.html](http://www.swig.org/download.html)

* 3.安装gym的Box2D-kengz的物理引擎
  * gym是个全家桶,里面包含了多种物理引擎Box2D等,游戏环境Atari等,是个用于研发和调测强化学习RL的好环境;
  * 先再次安装,改个名字: pip3 install gym[Box2D]   //单独命令安装Box2D,而不是all,也不是原来过时的Box2D-kengz
  * 安装成功后,如下测试:

  ```
  测试Box2D物理引擎是通过激活如下的小游戏CartPole:
  
  用如下命令来测试Box2D是否安装成功,如果失败,只会出现白框,而没有杆子!
  python //进入python,最好是PY3
  import gym  //load gym库,这里不能有报错
  env = gym.make("CartPole-v0")  //新建一个树立杆子的游戏环境
  env.reset() //初始化
  env.render()  //渲染,此时会弹出dialog,里面有杆子!就算OK了!
  env.close()  //关闭env环境,dialog不能被gui关闭,只能用本行命令关闭!
  
  ```

* 4.安装gym的Atari-py的小游戏强化环境集合
  * 单独安装: pip3 install gym[atari-py]   //报错一样,显示可能cmake有问题(win10下就需要安装MingGW等环境,最终没时间弄下去)
  * 安装cmake: sudo apt-get install cmake  //cmake是ubuntu操作系统lib库,不是python库,所以用apt而不是pip3来安装;
  * 然后再安装atari-py: pip3 install gym[atari]   //成功
  * 如果报错如下,请进入该报错提示的目录,需要额外手动生成缺漏的so文件,src源码在atari该目录,进入该目录直接make就能生成!
    * OSError: /home/ya/atari-py/atari_py/ale_interface/build/libale_c.so: cannot open shared object file: No such file or directory
    * 请进入/home/youraccount/atari-py/atari_py/ale_interface/    //此时没有build目录和文件libale_c.so
    * 在该目录看到了makefile文件和src目录,猜测是没有编译出so文件!
    * 在该目录直接运行命令make,它自动编译同目录的makefile编译编辑脚本,于是so文件有了,再次测试!!!通过了!!!
    * atari 安装完成!!!!

    ```
    测试:
    python //进入python,最好是PY3
    import gym  //load gym库,这里不能有报错
    env = gym.make("SpaceInvaders-v0")  //新建一个打飞机游戏环境(这里可能会报错如下!!!)
    env.reset() //初始化
    env.render()  //渲染,此时会弹出dialog,里面有飞机!就算OK了!
    env.close()  //关闭env环境,dialog不能被gui关闭,只能用本行命令关闭!
    ```

* 5.运行RL强化学习的例子
  * 强化学习RL很有趣,最近在学习,看了一些morvan的教程(github查找关键字"morvan"得到的第一个结果)
  * 跑一个普通RL例子,虽然import里面不需要纯python的图形库tkinter,但是matplotlib著名py的画图库需要,则要做如下安装:
    * 安装tkinter: sudo apt install python3-tk   //特别注意,不是 sudo apt install python-tk!!!


### 2.3 大数据

#### 2.3.1 日志 

##### 2.3.1.1 ELK   
   
###### 2.3.1.1.1 安装ELK
* ubuntu18.04下安装ELK日志分析套件
  * 官网: [https://github.com/elastic](https://github.com/elastic), 它维护了多个ELK组件,包括xpack(即将开源)机器学习组件;
  * TODO: 带添加安装ELK步骤;


## 3. END


