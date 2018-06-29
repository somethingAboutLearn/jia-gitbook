# 访问地址

[https://somethingaboutlearn.github.io/jia-gitbook/](https://somethingaboutlearn.github.io/jia-gitbook/)



# 创建项目


## 全局安装 gitbook-cli

- 首先需要安装 `nodejs` ，然后通过 `npm` 安装 `gitbook-cli`

	``` dos
	npm install -g gitbook-cli
	```
	
	
## 使用

- 初始化书籍目录

	``` dos
	gitbook init
	```

- 编译书籍

	``` dos
	gitbook serve
	```

- 生成静态资源 `_book`

    ``` dos
    gitbook build
    ```


## 项目目录

- 新建文件夹 `pages` ，用来存放资源文件

- 新建文件 `.gitignore` ，用来忽略不想上传到 git 仓库的文件

- 文件 `SUMMARY.md` 是目录文件，用来配置目录与页面



# 项目上传

``` dos
git init
git add .
git commit -m "first commit"
git remote add origin <url>
git push -u origin master
```



# 项目静态部署

## 创建 gh-pages 分支

- 创建分支，并且删除不需要的文件（只需要 `_book` 目录下的文件）

    ``` dos
    git checkout --orphan gh-pages
    git rm --cached -r .
    git clean -df
    rm -rf *~
    ```

- 新建文件 `.gitignore` ，忽略不想上传的文件（确保上传的只有 `_book` 下的文件）

    ``` dos
    echo "*~" > .gitignore
    echo "_book" >> .gitignore
    git add .gitignore
    git commit -m "Ignore some files"
    ```

- 将 `_book` 下的文件添加到分支

    ``` dos
    cp -r _book/* .
    git add .
    git commit -m "Publish book"
    ```

- 上传

    ``` dos
    git push -u origin gh-pages
    ```



# 项目地址


- 在 [github](https://github.com) 网站找到该仓库

- 进入该仓库的 `Settings` 页面

- 找到 `GitHub Pages` 模块，就看到 ` Your site is published at https://somethingaboutlearn.github.io/jia-gitbook/`