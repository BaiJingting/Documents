###装gensim遇到的坑
**一**、安装gensim，sudo pip install gensim (--user -U)，需要预安装numpy, scipy, six.  
&emsp;&emsp;在import gensim时，报错 ValueError: numpy.dtype has the wrong size, try recompiling。原因是numpy的版本和gensim要求的版本不同。但是sudo pip install -U numpy，结果还是不管用。  
&emsp;&emsp;网上有人说是System Integrity Protection的问题，解决的办法是关闭保护SIP（不懂）。  

&emsp;&emsp;具体操作：  
1. 重启电脑，电脑启动的时候按住command+R；  
2. 等画面上显示苹果logo的时候之后，你会看到「OS X 工具程式」的窗口，选择终端；  
3. 终端就打开了后输入csrutil disable，重启；  
4. 重启后重新执行sudo pip install -U numpy，

**二**、mac自带的six版本为1.4，numpy为1.8，都需要升级，要先将系统python扩展包目录里的packages删掉，再在外部目录里安装。  
因为模块的搜索路径为：  
1. 输入脚本的目录（当前目录）  
2. 环境变量PYTHONPATH表示的目录列表中搜索  
3. Ptyon的默认安装路径中搜索。

