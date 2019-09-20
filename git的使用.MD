## 四个区域

1. 本地仓库 git init 初始化本地仓库
1. 暂存区 git add

##  上传笔记 (第一次)

1.  新建一个 github 仓库
2.   找到对应的保存笔记的文件夹 执行 git init
3.  添加笔记或者修改笔记
4.  git add . 把文件夹内的所有 文件 添加到 暂存区
5.  git commit -m'提示信息' 把暂存区的内容 提交到 git 本地仓库
6.  本地仓库和 远程仓库 建立联系 git remote add origin 仓库地址
7.  git push origin master 同步到远程仓库

##  修改
1.   git add .
2.   git commit -m'修改了文件'
3.   git push origin master
