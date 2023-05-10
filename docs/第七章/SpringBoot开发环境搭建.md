# SpringBoot开发环境搭建

Spring Boot是一个开源的、快速的、方便的、基于Java的Web开发框架。搭建Spring Boot开发环境需要以下步骤：

## 安装JDK

首先，需要在你的系统上安装JDK。建议安装JDK 8或更高版本，你可以从Oracle官网下载适合你操作系统的JDK。

## 安装开发工具

可以选择使用Eclipse、IntelliJ IDEA或者Visual Studio Code等开发工具。这里以IntelliJ IDEA为例，从JetBrains官网下载并安装IntelliJ IDEA。

## 创建Spring Boot项目

打开IntelliJ IDEA，选择File > New > Project，选择Spring Initializr模板，点击Next。

在下一个页面中，选择以下选项：

- Group: 组织名，如com.example
- Artifact: 项目名称，如spring-boot-demo
- Type: 选择Maven或Gradle
- Language: 选择Java
- Packaging: 选择Jar或War

然后点击Next。

在下一个页面中，选择需要添加的依赖库，如Spring Web、Spring Data JPA等，然后点击Next。

在下一个页面中，选择项目存储位置，然后点击Finish。

## 运行Spring Boot项目

在IntelliJ IDEA中，可以通过点击运行按钮（绿色三角形）或者使用快捷键Shift+F10运行Spring Boot项目。

默认情况下，Spring Boot会运行在8080端口。可以通过在application.properties或application.yml文件中配置server.port属性来更改端口号。

以上就是搭建Spring Boot开发环境的基本步骤，可以根据需要添加其他依赖库和配置。
