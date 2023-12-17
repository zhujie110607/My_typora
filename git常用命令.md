#### 设置远程仓库与本地仓库关联起来

- git remote add origin 远程仓库地址

#### 推送到远程仓库

- git push -u origin main

#### 从暂存区把文件删除

- git rm 文件名  (同时也会把本地文件也删除）
- git rm --cached 文件名  （只会从暂存区删除，不会删除本地文件）

#### 把一个文件从暂存区移出到生产车间,比如1.txt添加到暂存区了，又想要移出来

- git reset head 1.txt

#### 从暂存区移出后想要恢复到上一状态

- git checkout -- 1.txt

#### 把常用的命令设置简短点

- git config --global alias.a add

#### 创建分支

- git branch 分支名

#### 查看分支

- git branch

#### 切换分支

- git checkout 分支名

#### 查看已合并的分支

- git branch --merged

#### 查看未合并的分支

- git branch --no-merged

#### 删除分支

- git branch -d 分支名  （如果分支已合并，用-d)
- git branch -D 分支名  （如果分支未合并，用-D)

#### 下载分支到指定的文件夹中

- git clone -b 分支名 --single-branch 仓库地址

>比如要克隆名为ask分支到 D:/test 中,仓库地址是：git@github.com:zhujie110607/test.git
>1，打开git bash,先用cd切换到D:test
>2,使用以下命令克隆
> git clone -b ask --single-branch git@github.com:zhujie110607/test.git

#### 删除github项目中的某个分支

- git push origin --delete ask  

#### 把Notepad++设置为提交时默认打开的编辑器

- git config --global core.editor "'C:\Program Files\Notepad++\notepad++.exe' -multiInst -notabbar -nosession -noPlugin"