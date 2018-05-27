---
layout: post
title: 2018-05-26-computer-using-hints-电脑使用帮助
key: 20180526
tags: ubuntu cuda cudnn tensorflow gym qq ssh
modify_date: 2018-05-26
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
* 2-Special Topic Hints
  * 2.1-Programming
    * 2.1.1-版本管理
      * 2.1.1.1-GIT 
        * 2.1.1.1.1-如何从本地PUSH分支改动到多个远端GIT仓库(假设远端GIT仓库为多个备份镜像库且内容相同) ?
  * 2.2 机器学习
    * 2.2.1-环境安装 
      * 2.2.1.1-ubuntu   
        * 2.1.1.1.1-ubuntu18.04环境安装机器学习环境TF的三件套CUDA-CUDNN-TENSORFLOW    
        * 2.1.1.1.2-ubuntu18.04环境安装OpenAI的GYM的强化学习环境    
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
  * TODO:暂未找到ubuntu18.04中调节鼠标大小的方法和命令;
  


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
   
### 2.2 机器学习

#### 2.2.1 环境安装 

##### 2.2.1.1 ubuntu   
   
###### 2.1.1.1.1 ubuntu18.04环境安装机器学习环境TF的三件套CUDA-CUDNN-TENSORFLOW
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

###### 2.1.1.1.2 ubuntu18.04环境安装OpenAI的GYM的强化学习环境
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






## END
