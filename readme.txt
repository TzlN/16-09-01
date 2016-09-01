git 笔记整理

1.首先你需要一个github账号,安装一个git

安装成功的标志就是右键有 git bash ,点击进去就ok了

2.然后你就可以开始在本地high起来了,具体是这么high的
  2.1创建一个文件夹,路径不要有中文,没有为什么  e:/git/study
  2.2进入 git bash 输入框 转到新建目录 cd e:/git/study Windows复制的路径是反斜杠,要改过来
  2.3第一个命令,创建git本地库 git init
  2.4在刚刚新建的目录下创建一个hello.txt文件,内容自拟
  2.5第二个命令 git add hello.txt   这是给文件加一个索引,让其能够被识别
  2.6第三个命令 git commit -m "这是描述"    这是将加了索引的文件提交到本地库
  2.7这些是另外的命令    
      git rm add.txt   
	  git status 
	  
3.接下来github账号来了,你需要在设置里面添加公钥,那么问题来了公钥是什么，哪来的
   3.1公钥和私钥分别对应 锁和钥匙  有了锁之后,你就可以拿钥匙去访问锁,这样就建立了访问通道
   3.2github上面可以建立repository 库,我们可以通过ssh方式拿私钥去访问公钥
   3.3获取公钥和私钥的命令  ssh-keygen -t rsa -C "18721394619@163.com" 输入命令 之后一直回车就很好
      ok 生成了这些东西,你需要在%window%/administrator/.ssh目录找到id_rsa.pub 打开复制内容到github设置sshkey
	  这样就ok了
	  
4.模拟开发
   4.1那么你本地的代码也该提交了 
      git remote add origin git@github.com:TzlN/16-09-01.git   没有错,这是添加远程库的命令
	  origin  是连接的名称 --随意就好 最好是默认
	  算是创建了链接了
	  git push -u origin master 这就是提交了
   4.2是时候再来一个同事了，新来的同事需要和你开发同一个项目,你就需要让他也能访问你的项目(这里不是git服务器)
      先创建一个目录 ,命令转到新建目录, git clone git@github.com:TzlN/16-09-01.git 这样就有项目了
	  创建一个新文件 git add new.jsp   
	  git commit -m "new.jsp"
	  git push -u git@github.com:TzlN/16-09-01.git
	  
	  再回到你自己的目录,新建文件去提交
	  git add new1.jsp
	  git commit -m "heihei"
	  git push -u git@github.com:TzlN/16-09-01.git 提示不能过
	  这里需要先pull主分支的代码
	  可能会有冲突,有就解决,没有就ok
	  然后再次push
	 