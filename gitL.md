# git
---
目录：
<a href="#git01">新建版本库</a>
<a href="#git02">传输文件</a>
<a href="#git03">远程仓库</a>
<a href="#git04">文件到达查看</a>
<a href="#git05">远程库克隆</a>
<a href="#git06">GitHub克隆</a>
<a href="#git07">多人协作</a>
从这个目录可以看出来,还会更新的。

---
<a name="git01"></a>
## 一、新建版本库
假设我们在D盘里的data目录（这个目录是自己手动新建过的）下新建一个版本库。

```git
$ cd E：
$ cd git
$ mkdir summary
$ cd summary
$ pwd(用于显示当前目录我们可以看到这个库到了 d:/git/summary/.git
)
```
再 把summary这个库变成可以管理的仓库
>$ git init 

<a name="git02"></a>
## 二、传输文件
我们把想放的文件（例：gitL.md）放到summary文件下，再在summary这个目录下打开git-bush。一般来说，我们只要看前三点就问题不大。
1. 放到暂存区
如果有**多个文件需要**一次提交的情况需要把他们先全add一下
>git add gitL.md
2. 将文件放到仓库中并注释
>git commit -m "此处为注释,**一个空格都不能少**"
3. 查看是否有文件未提交
>git status
   * 我变卦了，我改了gitL文件的内容
4. 再看看交没交
> git status //告诉我们我们的文件改了，但是还没提交
5. 我想知道改了什么
>git diff gitL.md
6. 重新提交再执行1.2.这两步,然后3.检查
   * 我又提交了个新文件（remove.md），但是我想删掉它
   >我们可以直接在目录里删掉它，或者
   > rm remove.md //不过在commit之前，仍可恢复此文件
   赶尽杀绝
   > git status
   git rm remove.md
   git commit -m  "remove remove.md"
   
7.我又想恢复这个新文件了(在commit之前)
> git chectout --remove.md
<a name="git02"></a>
## 三、远程仓库
我们已经在本地创建了一个git库，又想在GitHub创建一个git库，并希望这两个库远程同步。这样github的仓库可以作为备份，也可以其他人通过该仓库来协作。
1. 在GitHub上新建一个新的git库
2. 找到自己的库的地址(上面的链接)
>git remove add origin https://github.com/wangxiiiyu/Summary（这个是我的仓库地址）

3.推送master分支到远程          
>git push -u origin master
（第一次推送时加-u，不仅推送，还会关联）

4.本地master最新修改的推送
  * 只要本地做了提交，就可以通过这个来推送到版本库上了
  >git push origin master

5.之前出了点问题
<br>
![翻车现场](https://raw.githubusercontent.com/wangxiiiyu/Summary/master/pic/%E5%9B%BE%E7%89%873.png)
<br>
如果我在GitHub上的仓库里新建了README.md文件，并进行更改，那么我就无法提交我后续的文件了，我们需要先同步一下，把GitHub上多出来的文件放到本地，保持一致。
* 线上线下代码合并
>git pull --rebase origin master
* 再push
>git push origin master

