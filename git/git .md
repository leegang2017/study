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