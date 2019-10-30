# kz-cli-commit

实现`kz-commit`功能，自带检测是否初始化

```
> kz commit --init
```

* `options` 配置
  * `--init` 初始化commit

执行后，用`kz-commit`或者`npm run kz-ci`替换`git commit`操作

```
 $ npm run kz-ci
   or
 $ npx kz-commit
```

*不能直接kz commit做提交，`commitizen` 默认第一个为cli命令，后面皆为参数，commit被当做参数执行报git commit的错误*

## release

关于发布，当前以`dev`为默认分支，在`dev`分支做日常开发和测试。谨记包的发布需切换`master`分支。

先切换到`master`分支，再合并`dev`分支，执行`npm run release` 发版后，再以`master`作为基点版本。

```
> git branch
$ * dev
> git add .
> git commit -m "feature:xxx"
> git checkout master
> git merge dev
> npm run release
> git checkout dev
> git rebase master
> git push origin dev
```
