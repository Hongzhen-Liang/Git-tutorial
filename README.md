# Git-tutorial
Git教程

0. 原理:
	1. VCS: 分布式版本控制
	2. 三阶段: modified -> staged -> commited
		* 更改后成为modified，add更改后成为staged，commit后成commited
	3. 离线使用，每一份copy都是全量的，分布式安全
1. 起步:
	1. 安装: `sudo apt-get install git-all`
	2. 配置:
		* list当前配置:`git config --list`
		* `--global`: 设定
		1. 登录配置: `git config --global user.name "sinscry"` && `git config --global user.email sinscryw@gmail.com`
		2. 编辑器设置: `git config --global core.editor vim`
2. 基础
	1. 开启Git Repository
		1. 初始化当前文件夹:
			1. 初始化:`git init`
			2. 添加版本:
				```
				git add *.c
				git add LICENSE
				git commit -m "initial project version
				```
		2. clone文件夹: `git clone [url]`
		3. 设置ignore文件:
			* 这可以避免commit部分本地文件
			1. 创建.gitignore文件:
				* 匹配所有.a和.o文件:`*.[oa]`
	2. 查看当前文件状态: 
		1. 标准：`git status`
		2. 简易：`git status -s`
			* A: 新增，M:修改, ??:未被tracked
		3. 详细查看变化: `git diff`
			* 只看被stage待commit的: `git diff --staged` || `git diff --cached`
			* 注意git diff只对比stage的，不是面向上一次commit
	3. 导入Staged状态: `git add .`
	4. commit stage: `git commit -m "消息"`
		* 自动stage模式: `git commit -a -m "消息"`
	5. 删除操作
		1. 删除stage里的文件: `git rm 文件名`
		2. 只删除stage里但保留在本地: `git rm --cached 文件名`
	6. 查看commit历史
		1. 查看更改日期: `git log`
		2. 参数: -p:显示具体不同, -2:限制两条, --stat:简短信息
		3. 限制时间：`git log --since=2.weeks` 或者 `2008-01-15`
		