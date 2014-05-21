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

---
###OracleSQL
#####连接数据库
```sql
sqlplus /nolog
conn sys/train_2011@training as sysdba;
```

#####创建表空间
```sql
create tablespace training
logging
datafile 'c:\oracle\product\10.2.0\oradata\training\training.dbf'
size 100m
autoextend on next 50m maxsize 1024m
extent management local;
```

#####创建用户并指定表空间
```sql
create user training identified by train_2011
default tablespace training
temporary tablespace temp;
```

#####给用户授权
```sql
grant (create session/create table/create view/connect/resource/dba/ultimated tablespace/any procedure) to training;
```

#####查看所有用户
```sql
select * from (dba_users/all_users/user_users)
```

#####查看系统权限
```sql
select * from (dba_sys_privs/user_sys_privs)
```


#####查看所有角色
```sql
select * from dba_roles
```


#####unlock_user  (用户解锁)
```sql
alter user training account unlock;
```
#####table_structures  (描述表结构)
```sql
desc emp
```


#####备份表
```sql
create table backupTable as select * from  originTable;
```

#####查询前3行
```sql
select * from table where rownum<=3 //在oracle中只能用</<=
```

#####查询3到4行
```sql
select * from (
select id,name,salary,rownum r from (
select * from table order by salary desc
))where r<5 and r>=3  
//第一次查询排好序，第二次查询加入rownum列，第三次按照第二次中rownum作为判断条件
```

#####数据字典dictionary
```
user_indexs索引表
user_tables当前用户拥有的表
user_constraints约束表
user_view视图表
...
```

---



