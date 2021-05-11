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
	4. commit stage: `git commit -m <"消息">`
		* 自动stage模式: `git commit -a -m "消息"`
	5. 删除操作
		1. 删除stage里的文件: `git rm <文件名>`
		2. 只删除stage里但保留在本地: `git rm --cached 文件名`
	6. 查看commit历史
		1. 查看更改日期: `git log`
			* `git log --pretty=oneline`
		2. 参数: -p:显示具体不同, -2:限制两条, --stat:简短信息
		3. 限制时间：`git log --since=2.weeks` 或者 `2008-01-15`
	7. 撤回操作:
		1. 覆盖last commit：`git commit --amend` (允许将当前add的东西覆写上一次commit)
		2. 撤销stage: `git restore --staged <文件名>`
		3. 撤销修改文件: `git restore <文件名>`
		4. 回退到某次commit: `git reset --hard <commit_id>`
	8. 远程仓库:
		1. 查看远程仓库url: `git remote -v` && `git remote show <仓库名>`
		2. 添加远程仓库: `git remote add <自定义仓库名> <url>`
		3. 下载远程仓库: `git fetch <自定义仓库名>`
		4. 上传到仓库: `git push <自定义仓库名> <分支名>`
		5. 更仓库名和改仓库名:
			* `git remote rename <旧名> <新名>`
			* 删除:`git remote rm <仓库名>`
	9. 标签重要升级:
		1. 查看标签: `git tag`
			* 带筛选版:`git tag -l "v1.8.5*`(列出所有带*之前的标签)
		2. 添加annotated标签: `git tag -a <版本> -m <"消息">`
			* 简单版（不带消息): `git tag <版本>`
		3. 显示标签信息: `git show <版本>`
		4. 补充标签:
			1. git log 找到对应commit
			2. git tag -a <版本> <commit的hash值>
		5. 上传tag: `git push <自定义仓库名> <版本>`
			* 所有tag上传: `git push <自定义仓库名> --tags`
		6. 将版本建立新分支: `git checkout -b <分支名> <版本>`
	10. 分支branch:
		* 默认分支名master
		1. 创建新branch: `git branch <分支名>` , HEAD指向当前branch
		2. 显示当前使用branch: `git log --oneline --decorate` || `git branch -v`, 显示已merge的branch: `git branch --merge`
		3. 更改branch: `git checkout <分支名>`
		4. 创建并同步更改branch:`git checkout -b <分支名>`
		5. 合并branch: `git merge <分支名>`
		6. 删除branch: `git branch -d <分支名>`
		
		
		
		
		
		
		
		
		