类似与Jenkins，但是所有的流程信息是在yml中配置。

# 配置

## .travis.yml文件设置

项目根目录下添加`.travis.yml`文件
```yaml
language: node_js # 指定语言环境
node_js: node
dist: trusty # 指定系统版本。Ubuntu 14.04 发行版
sudo: required # 是否需要sudo权限
branches: # 指定要构建的分支
	only: # 只构建以下分支
	- master
install: # 执行脚本文件
	- npm install -g hexo-cli
	- npm install
	- git config --global user.name "${GIT_USER_NAME}"
	- git config --global user.email "${GIT_USER_EMAIL}"
	- sed -i'' "s~git@github.com:~https://${GIT_REPO_TOKEN}@github.com/~" _config.yml
script: # 构建命令
	- hexo clean
	- hexo generate
after_success: # 构建成功后执行命令
    - hexo deploy
```
## Travis CI配置

添加仓库，设置执行脚本所需要的环境变量。Travis CI会根据yml文件中的配置信息，在指定环境执行构建脚本

# 推送权限

需要为Travis CI添加推送权限，用于页面部署。

## 获取授权信息

GitHub-用户-设置-开发者设置，添加个人验证信息，开启repo权限，获得的字符串用于设置Travis CI的环境变量值

## Travis CI添加环境变量

配合yml配置文件，需要将环境变量命名为GIT_REPO_TOKEN，值为验证信息。环境变量不在log中显示，避免泄漏

官方的关于推送权限的设置： <https://docs.travis-ci.com/user/customizing-the-build/>


# 参考文档

> [使用 Travis 自动构建 Hexo 到 GitHub | Zthxxx's Blog](https://blog.zthxxx.me/posts/Build-Hexo-Blog-by-Travis-CI/)