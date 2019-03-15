# SonarQube安装

> 7.6版本

## 下载

前往[官网](https://www.sonarqube.org/)下载压缩包

## 数据库配置

### 数据库要求

[数据库要求](https://docs.sonarqube.org/latest/requirements/requirements/)

mysql
- 5.6、5.7版本
- `UTF-8`字符集

Oracle
- 11G、12G
- 需要自行提供驱动。按照配置文件中的说明。驱动需要放在指定目录内`extensions/jdbc-driver/oracle/`
- `UTF-8`字符集

数据库必须满足要求，否则会启动失败，提示断开连接。

### 配置

[连接信息配置](https://docs.sonarqube.org/latest/setup/install-server/)

在`conf/sonar.properties`中配置连接信息
```properties
sonar.jdbc.username=
sonar.jdbc.password=
sonar.jdbc.url=
```

## 启动

`bin`中根据系统选择对应的启动方式。

默认9000端口，可以在`conf/sonar.properties`中修改
```properties
sonar.web.port=9000
```

默认管理员账号密码：`admin/admin`

## 汉化

登陆后，`Administration > Marketplace`，搜索`Chinese Pack`，安装重启即可。

# 与Jenkins集成
获取授权信息

安装插件

添加构建配置