> 无pom安装，安装依赖的pom中不会携带除坐标以外的任何信息。因此一定要区别对待两种安装方式。如果是使用maven打包生成的依赖，务必使用第二种方式安装依赖

# 无pom

[插件使用说明](http://maven.apache.org/plugins/maven-install-plugin/usage.html)

```
mvn install:install-file -Dfile=your-artifact-1.0.jar \
                         [-DpomFile=your-pom.xml] \
                         [-Dsources=src.jar] \
                         [-Djavadoc=apidocs.jar] \
                         [-DgroupId=org.some.group] \
                         [-DartifactId=your-artifact] \
                         [-Dversion=1.0] \
                         [-Dpackaging=jar] \
                         [-Dclassifier=sources] \
                         [-DgeneratePom=true] \
                         [-DcreateChecksum=true]
```
必须包含的参数
- `-Dfile=`文件路径
- `-DgroupId=`
- `-DartifactId=`
- `-Dversion=`
- `-Dversion=`
# 有pom

[含pom依赖安装](http://maven.apache.org/plugins/maven-install-plugin/examples/custom-pom-installation.html)

指定pom文件
```
mvn org.apache.maven.plugins:maven-install-plugin:3.0.0-M1:install-file -Dfile=path-to-your-artifact-jar -DpomFile=path-to-pom
```

内置pom文件
```
mvn org.apache.maven.plugins:maven-install-plugin:3.0.0-M1:install-file -Dfile=<path-to-file>
```

#  安装依赖至指定本地仓库

[安装依赖至指定本地仓库](http://maven.apache.org/plugins/maven-install-plugin/examples/specific-local-repo.html)

```
mvn org.apache.maven.plugins:maven-install-plugin:3.0.0-M1:install-file  -Dfile=path-to-your-artifact-jar \
                                                                              -DgroupId=your.groupId \
                                                                              -DartifactId=your-artifactId \
                                                                              -Dversion=version \
                                                                              -Dpackaging=jar \
                                                                              -DlocalRepositoryPath=path-to-specific-local-repo
```
通过`-DlocalRepositoryPath`指定本地仓库路径