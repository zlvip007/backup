title: 常用指令
date: 2014-04-29 21:20:35
categories: Tech
tags: 

---

* Eclipse 常用快捷键
* git 常用指令
* native2ascii

<!--more-->
###Eclipse常用快捷键：  
1. `ctrl shift t` 打开类型(全是类)  
2. `ctrl shift r` 打开资源(图片.css.js.jsp.xml)
3. `F3`  打开声明
4. `alt —>/<—`  上/下一次打开的 文件夹
5. `ctrl q` 最后一次修改的地方
6. `ctrl shift f` 排版
7. `ctrl o` 快速outline，列出当前类的骨架
8. 注释：  
 + 单行注释： `ctrl /`
 + 多行注释： `ctrl shift /`
 + 取消多行注释：  `ctrl shift \`
9. `ctrl e = ctrl pageUp/pageDown` 编辑区快速切换
10. `alt shift r` 对该变量在该类中的所有地方进行重命名
11. `ctrl shift enter` 光标下面加空行
12. `shift enter` 光标上面加空行
13. `ctrl m` 当前窗口最大化
14. `alt 上下键` 当前行上下移动
15. `ctrl shift l` 看更多快捷键(两次能到preferences-->key)

---

###git 常用指令

1. 将github中repo克隆下来： `git clone https://github.com/zlvip007/people.git`
2. 将文件拷入people中，添加：`git add .`提交本地库：`git commit -m "first edition"`
3. 提交到远端库：
 * `git remote add origin https://github.com/zlvip007/people.git`
 * `git push origin gh-pages`

```
Q:  提交到远端出现：`fatal:remote origin already exists`  
A:  解决办法：`git remote rm origin`，再执行提交大到远端
```

####基础命令
* git init
* git status
* git add (./'*.txt')
* git commit -m "infomation"
* git log
* git remote add origin *https://github.com/zlvip007/people.git*
* git push origin master
* git pull origin master
* git diff head
* git diff --staged
* git reset *octofamily/octodog.txt*    [remove  octofamily/octodog.txt*]
* git checkout -- octocat.txt
* git branch *clean-up*  [new branch *clean-up*]
* git checkout *clean-up*  [turn to branch *clean-up*]
* git rm *'\*.txt'*
* git checkout master
* git merge *clean-up*
* git branch -d *clean-up*   [delete branch *clean-up*]
* git push


---

###native2ascii

**位置：**`jdk --> bin --> native2ascii.exe`  
**格式：**`native2ascii [option] before.txt after.txt`
	
	[option]  
	-reverse (-encoding GBK) : 将Unicode编码转为本地或者指定编码     
	-encoding (GBK) :   转换为指定(GBK)编码  

**实例：**  
 
D盘有befor.txt，内容为：“功不唐捐” 
 
	转换为Unicode 
	D:\>native2ascii before.txt after.txt
	  
D盘新建了after.txt，内容为:\u00b9\u00a6\u00b2\u00bb\u00cc\u00c6\u00be\u00e8  
（不指定after.txt则输出到控制台）


    转换为ISO8859-1  
    native2ascii -encoding ISO8859-1 before.txt

.

	转换为本地默认编码
	native2ascii -reverse before.txt

.

	转换为本地指定编码  
	native2ascii -reverse -encoding (GBK) before.txt