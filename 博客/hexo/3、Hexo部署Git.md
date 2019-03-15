## 安装组件

需要安装插件：`npm install hexo-deployer-git --save`

实际是安装该组件，同时将组件信息写入package.json文件

## 配置部署信息

```
deploy:
	type: git
	repository: 仓库地址
    branch: 分支
```

## 执行部署
```
hexo d
```

需要生成静态文件再执行。

部署会完全覆盖原分支中的内容。