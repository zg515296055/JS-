### 配置用户信息
git config --global user.name "zfpx"
git config --global user.email "1323682239@qq.com"
git config --list 查看配置是否成功


linux 命令
 - ls  当前目录下有哪些文件
 - cd 文件夹 
 - cd .. 回到上级目录
 - mkdir test2 创建文件夹
 - touch aa.txt 创建文件
 - cat aa.txt 查看文件
 - vi aa.txt  编辑文件  i 进入可编辑状态 退出编辑状态 esc
   :q!  强制退出
   :wq  保存退出
 - rm -rf 删除文件
 
### 创建本地的git仓库
- 进入需要操作的文件夹 右键git bash here 在当前文件夹下打开git命令窗口
- git init 
- git status 查看提交的状态
- 提交到暂存区
  git add .  
- 提交到历史区
  git commit -m "备注信息" 
  
  
## 本地仓库内容提交到远程仓库
远程仓库地址 ：https://github.com/zfpx/201804JS.git
① 关联本地仓库和远程仓库
git remote add zfpx(远程仓库名) https://github.com/zfpx/201804JS.git 
git remote -v 查看关联的远程仓库
git remote rm zfpx  删除关联的远程仓库

② 推送本地仓库内容到远程仓库
 git push zfpx master  推送到远程仓库的主分支
 
 
复习：
git config credential.helper '' 清除配置的用户信息

git config --global user.name "zfpx"
git config --global user.email "1323682239@qq.com"

1. 进入文件夹 打开git命令窗口 -> git  init   初始化本地git仓库
2. git add . 提交到暂存区
3. git commit -m "提交的信息"
3. 去github新建仓库  点+号->new respository->create respository 
   会生成一个远程仓库地址  https://github.com/zfpx/201804JS.git
4. 进入本地仓库文件夹  关联本地仓库和远程仓库
  git remote add origin https://github.com/zfpx/201804JS.git
5. git push origin master  把本地仓库内容推送到远程仓库
6. 若遇到远程仓库内容和本地仓库内容不一样时 
    先需要把远程仓库内容拉取下
    git pull origin master --allow-unrelated-histories  强制先合并远程仓库和本地仓库的内容 
    
    
## 另外一种提交本地项目的方式    
- git clone https://github.com/zfpx/test.git
 相当于做了三件事：
  1.建了一个本地git仓库，仓库名和远程仓库名一样
  2.本地仓库和远程仓库关联起来了
  3.远程仓库的内容已经拉取到本地仓库
- git add .
- git commit -m""
- git push origin master  
> 远程仓库内容和本地仓库内容不一样时，需要两个仓库保持同步后，才能往远程仓库推送内容，
同步的做法就是git pull origin master 把远程仓库内容先拉取到本地仓库  


获取老师的课件
第一次时 git clone  https://github.com/zfpx/201804JS.git
从第二次开始每次进入到201804JS文件夹，git pull origin master

## 组长把作业提交到老师仓库（201804JS）
1.用你的用户名，密码登录github 
2.https://github.com/zfpx/201804JS(别人的仓库) 复制到地址栏按回车
3.点击fork，201804JS仓库就会克隆到你的github上 






