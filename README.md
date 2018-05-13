# learnGit
1、git init 将当前目录初始化为一个git可以管理的仓库  
2、git add filename 将名为filename的文件添加到暂存区  
### git add -A/-u/.三者区别：  
* git add -u 将文件的修改、删除添加到暂存区  
* git add . 将文件的修改、新建添加到暂存区	  
* git add -A 将文件的修改、新建、删除添加到暂存区


3、git commit 将add到暂存区的文件提交到仓库  
    
    git commit -m "" 双引号内修改说明
4、git status 查看当前git仓库状态  
5、git diff 

    git diff 不加参数，比较工作区与暂存区的不同
    git diff --cached 比较暂存区与最新本地版本库（最近一次commit的内容）
    git diff commit-id 比较工作区与指定commit-id的不同
    git diff commit-id commit-id 比较两个commit-id的差异
    
6、git log 显示从最近到最远的提交日志 加上--pretty=oneline参数，在一行内显示一次提交的简略信息  
7、git reset命令    

    git reset --soft 回退到某个版本，只回退了commit的信息，不会到暂存区
    git reset --hard 彻底回退到某个版本本地源码也会变为上一个版本的内容
    git reset HEAD^回退到上一个版本，git reset HEAD^^回退到上上个版本
    HEAD~100表示往上100个版本
    git reset commit-id回退到指定版本
    
 8、git checkout -- file 撤销修改，让文件回到最近一次add或者commit时的状态     
 9、git rm 删除文件  
     
     git rm test.txt 删除文件test.txt
     确认是要删除文件test.txt 接着就可以提交 git commit -m "",
     如果是删错了可以用 git checkout -- test.txt恢复文件
     
  10、关联远程仓库
  
      git remote add origin 远程仓库地址
      git push -u origin master将本地master分支推送至远程仓库，
      第一次推送需添加-u参数，以后只用 git push origin master就可以了
      
  11、从远程仓库克隆
  
      git clone 远程地址 将远程仓库clone到本地
      
  12、分支管理
  
      git branch 显示当前分支
      git branch dev 创建dev分支
      git checkout dev 切换至 dev分支
      git checkout -b dev 创建并切换至 dev分支
      git merge dev 将dev分支的工作合并到master上
      git branch -d dev删除dev分支
      
   13、git tag 给分支打标签
   
       git tag <name>给分支添加标签（首先要先切换到要打标签的分支）
       git tag -a <tagname> -m "……"指定标签信息
       git tag -s <tagname> -m "……"用PGP签名标签
       git tag 查看所有标签
       git tag -d 删除标签
       git push origin <tagname> 推送标签到远程
       git push origin --tags 一次性推送所有尚未推送到远程的本地标签
       
    
             