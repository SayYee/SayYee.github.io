# 安装+建站
需要安装git、node。
1. 使用npm安装hexo组件：`npm install -g hexo-cli`
2. 配置npm淘宝镜像
```
# 查看仓库
npm get registry
# 设置淘宝镜像
npm config set registry http://registry.npm.taobao.org/
```
3. 新建站点：新建文件夹，执行`hexo init`
4. 安装站点需要的组件：`npm install`。会根据`package.json`中的配置信息安装组件。也可以手动安装指定组件`npm install hexo-server --save`
5. 生成静态资源：`hexo g`
6. 启动站点：`hexo s`

# 新建文章
```
hexo new [layout] <title>
```
这种方式生成的文件，会自动应用已经配置好的模板文件，动态填充内容。编辑文章还是推荐使用Typora。

# wiki主题应用

https://github.com/zthxxx/hexo-theme-Wikitten

参照中文说明进行配置即可。

# 参考网址
- [使用 Hexo 生成静态博客过程记录 | Zthxxx's Blog](https://blog.zthxxx.me/posts/Hexo-Build-Static-Blog-Process/)