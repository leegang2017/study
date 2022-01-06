### 1. [Git远程操作详解](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)

### 2. [常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)

### 3. [Git 使用规范流程](http://www.ruanyifeng.com/blog/2015/08/git-use-process.html)

跳过本次构建
git commit -m '[ci skip] to prod'

### Git修改远程仓库地址
方法一：通过命令行修改远程地址
> cd json
> git remote set-url origin https://gitee.com/jouypub/json.git
方法二：先删除原有仓库地址，然后添加新地址
> cd json
> git remote rm origin
> git remote add origin https://gitee.com/jouypub/json.git

修改commit作者
git commit --amend --author="Author Name <email@address.com>"

初次运行 Git 前都要进行用户名和邮件地址配置，一般使用下面命令进行配置：

git config --global user.name "John Doe"
git config --global user.email johndoe@example.com

通过--global参数设置后，配置文件放置在~/.gitconfig，对当前系统用户所有工程适用，配置完成后可以通过git config user.name和git config user.email查看

针对每个工程使用不同的配置，则需要在当前工程根目录下运行命令
git config user.email "xxx@qq.com"
git config user.name "xxx"

