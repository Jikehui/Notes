# 认识Github
----------
`一个国际代码托管平台，非常有用`
`从终端完成代码在工作区到远程仓库的传递与加载 `
# 安装Git
-----------
* msysgit是Windows版的Git，从https://git-for-windows.github.io下载，然后按默认选项安装即可。安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西
* 安装完成后，还需要最后一步设置，在命令行输入：
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"

# 建版本库(本地仓库)
-----------
* 选择一个合适的地方，创建一个空目录
* 把这个目录变成Git可以管理的仓库：$ git init


## 从终端完成代在工作区到远程仓库的传递与加载
- 下载git工具到本地
- use git下载项目：clone with https
- 进入该项目文件夹目录：cd 文件名
- 文件放入暂存区：git add 文件名
- 文件放入本地仓库：git commit -m "对文件操作的注释"
- 查看文件状态：git status
- 上传到github：git push origin master
- 从远程仓库获取：git pull origin master
## 绘制流程图

```seq
工作区->本地暂存区: git add A
代码
本地暂存区->本地仓库: git commit -m ""
本地仓库->远程仓库: git push origin master
```
=======
 # SSH
----------
`本地Git仓库和GitHub仓库之间的传输是通过SSH加密的`
#### 创建 SSH Key
* $ ssh-keygen -t rsa -C "youremail@example.com"一路回车，使用默认值即可

* 在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

* 登陆GitHub，打开“Account settings”，“SSH Keys”页面,
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容

#### 本地仓库连接远程仓库
-----------
  #### 方法一：  添加远程库
  `在本地创建了一个Git仓库后，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步`
* 登陆GitHub，然后，在右上角找到“Create a new repo”按钮，创建一个新的仓库
* 在本地的仓库下运行命令：$git remote add origin git@server-name:path/repo-name.git

 #### 方法二：  从远程库克隆
  `上面是 先有本地库，后有远程库的时候，如何关联远程库。
现在，假设我们从零开发，那么最好的方式是先创建远程库，然后，从远程库克隆。`
* 登陆GitHub，创建一个新的仓库,勾选Initialize this repository with a README，这样GitHub会自动为我们创建一个README.md文件
* 使用git clone命令克隆:$ git clone git@github.com:michaelliao/gitskills.git
(Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快)

### 从终端完成文件在工作区到远程库的传递与加载
代码
-----------
`工作区->本地暂存区->本地仓库`
* 文件放入暂存区（Stage）：git add 文件名
* 文件提交到分支（master）：git commit -m "对文件操作的注释"
* 推送到远程库（github）：git push origin master
* 从远程仓库获取：git pull origin master
* 查看文件状态：git status
>>>>>>> e339935447613da85e990bede1153fb66546d926
