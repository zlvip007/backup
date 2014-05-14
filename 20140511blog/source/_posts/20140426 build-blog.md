title: 该博客搭建笔记
date: 2014-04-26 11:14:41
categories: Tech
tags: 

---
`使用Hexo搭建博客，markdown写博客，生成的静态页面托管在Github，图床为七牛`
###1.搭建环境
* 安装[git](http://code.google.com/p/msysgit/ "mysysgit")，[node.js](http://nodejs.org/)，hexo(git bash中执行`$ npm install -g hexo
`)
* 新建文件夹blog，在其中执行git bash命令：`$ hexo init`-->`$ hexo generate`-->`$ hexo server` 访问[localhost:4000](http://localhost:4000)本地博客  <!--more-->
* 在github中新建一个repository:[zlvip007.github.io](https://github.com/zlvip007/zlvip007.github.io "'zlvip007'为github用户名")  
* 编辑_config.yml如下：  
    deploy:  
    type: github  
    repository: https://github.com/zlvip007/zvip007.github.io.git  
    branch: master

* `$ hexo generate`-->`$ hexo deploy` 完成部署，访问**zlvip007.github.io**

###2.写博客
* `$ hexo new "new post"` 生成blog/source/\_post/new\_post.md,用markdown编写后  
* `$ hexo deploy` 发布
* 完毕，访问  `zlvip007.github.io`    
  
---

# 个性化

####参考:[howiefh][3]   
1. google analytics  
2. RSS，sitemap  
3. 返回顶部   

---
####参考:[zipperary][1]  
1. 添加多说  
2. 添加百度分享  
3. 添加小图标  
4. 添加分类，标签云widget  
5. 添加微博秀  
6. 添加关于  
7. RSS,sitemap  
8. 百度统计，google analytics  
9. 购买域名，配置DNS  

---
####参考:[buru][4]   
1. 新文章中自带categories  
2. fancybox  
3. description  
4. 主题安装  
5. 多说评论  
6. 自定义页面“about”  
7. 404页面  
8. 域名配置  
9. 文件夹布局说明  
10. 百度统计/Google analytics  
11. 分享  
12. 网站图标  
13. 自定义挂件  
14. 插件：RSS,sitemap  
15. 搜索引擎  
16. 更新：hexo，themes，插件  

---
#附录
##[Hexo官方文档摘要](http://hexo.io/docs/)
###[Writing](http://hexo.io/docs/writing.html)
`$ hexo new [layout] "title"`  
    **[layout]**  
    **post**(Default) source/_posts  
    **draft** source/_draft  
    **page**  source    

`<!--more-->` 使文章显示前半部分  
###[Generating](http://hexo.io/docs/generating.html)
`$ hexo g` generate static files  
    deploy after generating  in two ways:  
    `$ hexo g -d`  
    `$ hexo d -g` 
###[Server](http://hexo.io/docs/server.html)
`$ hexo s` start server  
     server会自动更新file，但**public**中的不会，需`$ hexo g`  
     配置文件更新需重启
###[Deployment](http://hexo.io/docs/deployment.html)
`$ hexo d` deploy  
`$ rm -rf .deploy` remove **.deploy** folder
    在source中新建CNAME,放置自己的域名  
###[Configuration](http://hexo.io/docs/configuration.html)
	title: WIllDOne
	subtitle: connecting dots...
	description: //给搜索引擎用的描述 ie:head中的meta
	author: 
    email:
	language: zh-CN
	
	url: //域名
	root: /
	permalink: :year/:month/:day/:title/   //若取消日期，地址栏为域名+标题，但部署后在public下会为每一篇文章生成一个文件夹
	tag_dir: 标签包 tags
	archive_dir: archive directory archives
	category_dir: 类别包 categories
	code_dir: 代码存放包 downloads/code
	
	new_post_name: :title.md     //新建文章的名字，可变为:日期+title  :year/:month/:day/ :title/ 
	default_layout: post         //hexo new post "new post"
	auto_spacing: false
	titlecase: false
	max_open_file: 100
	multi_thread: true
	filename_case: 0
	render_drafts: false
	highlight:
	  enable: true
	  line_number: true   //代码显示行号
	  tab_replace:
	
	default_category: uncategorized
	category_map:
	tag_map:
	
	archive: 1 /*2为文章显示，1为标题显示，0为不显示 */
	category: 1
	tag: 1
	
	port: 4000
	logger: false
	logger_format:
	
	date_format: MMM D YYYY
	time_format: H:mm:ss
	
	per_page: 每页显示数 10
	pagination_dir: page
	
	disqus_shortname: zlvip007
	duoshuo_shortname: 

	theme: landscape
	exclude_generator:
	
	markdown:
	  gfm: true
	  pedantic: false
	  sanitize: false
	  tables: true
	  breaks: true
	  smartLists: true
	  smartypants: true
	
	stylus:
	  compress: false
	
	deploy:
	  type: github
      repository: https://github.com/zlvip007/zvip007.github.io.git  
      branch: master


 
[1]:http://zipperary.com/categories/hexo/ "zipperary`s blog"
[2]:http://hexo.io/ "hexo documentation"
[3]:http://howiefh.github.io/2014/02/07/hexo-note/ "howiefh`s blog "
[4]:http://ibruce.info/2013/11/22/hexo-your-blog/ "buru`s blog"