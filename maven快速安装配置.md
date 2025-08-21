# Maven快速安装配置



## Maven简介

Maven是一个依赖管理和项目构建的工具

Maven官网：https://maven.apache.org/

注意事项：

1. Maven需要JDK环境并且需要配置JAVA_HOME环境变量

2. 并对JDK版本有最低要求 请参照官网

## Maven下载安装

从官网下载解压即可。

或者使用资料中提供的zip包解压。

## Maven配置

修改 maven安装目录 -> conf -> settings.xml文件：

- 配置本地仓库（可选）

```xml
<localRepository>D:\soft\apache-maven-3.9.8-bin\apache-maven-3.9.8\repo</localRepository>
```

- 配置远程仓库：使用国内镜像（必需）

```xml
<mirror>
  <id>aliyunmaven</id>
  <mirrorOf>*</mirrorOf>
  <name>阿里云公共仓库</name>
  <url>https://maven.aliyun.com/repository/public</url>
</mirror>
```

## idea中配置maven

- 当前项目配置（必需）
- 所有新项目设置（可选）



https://mvnrepository.com/
