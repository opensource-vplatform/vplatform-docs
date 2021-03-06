# 函数开发

# 1. 简介

开发基于V3平台的二次开发函数。

## 2. 开发系统

## 2.1. 功能构件

### 2.1.1. 新建功能构件

![新建功能构件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/2.1_createFunctionComponent.png)

- 构件导航栏右键菜单-新建功能构件；
- 构件信息-分类，选择**函数**；
- 点击”确定“按钮后创建函数-功能构件；

### 2.1.2. 元数据管理

功能构件-元数据管理，主要是用于描述函数的基本信息和在安装时生成元数据文件。

![元数据管理](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/2.2_metadata_1.png)

![元数据管理](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/2.2_metadata_2.png)

- 编码，函数编码；

- 名称，函数名称；

- 版本号，函数版本号；

- 返回类型，函数返回值的数据类型；

- 函数类型，定义函数在哪种方法内使用，客户端，服务端；

- 函数支持，定义函数在哪种平台下可用，普通窗体、网页窗体、移动窗体、构件方法；

- 分类，在表达式编辑器中，选择函数时的分类；

  ![函数分类](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/2.2_metadata_3.png)

- 是否显示，定义函数是否可见。

- 是否可用于功能构件，定义函数是否在功能构件中使用；

- 备注，函数的描述信息；

- 示例，函数的使用例子；

- 一致性校验，标识该函数在部署时是否需要校验与执行系统的一致性；

- 一致性编码，开发系统与执行系统的一致性编码，通过这个编码来关联开发系统与执行系统的对应关系；

- 一致性版本，对应执行系统的一致性版本，执行系统还有会“最低一致性版本”的设置。即开发系统的一致性版本在对应系统系统的一致性版本和“最低一致性版本”之间，则可以通过一致性检查；

- 函数参数-不定参数，定义函数参数的个数是否固定；

- 函数参数-数据类型，定义函数参数的数据类型；

- 函数参数-是否必填，定义函数参数是否为必填项；

- 函数参数-备注，函数参数的描述；

# 3. 执行系统

## 3.1. 客户端函数

### 3.1.1. 创建工程

- 选择**V3 Webfunc Project**类型，创建工程；

  ![新建工程](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.1_eclipseCreateWebfuncProject.png)

- 编辑工程信息

  ![工程信息](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.1_webfuncProjectInfo.png)

  - Artifact Id，构件id
  - Version，版本号
  - FuncName，函数编码

### 3.1.2. 函数实现

- 工程目录

  ![工程目录](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.1_webfuncDir.png)

  - DemoFunc.js，存放函数功能实现的逻辑；
  - pom.xml，保存函数的版本信息，以及需要引用的其他服务信息；

- js文件实现

  ![js文件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.1_jsFile_2.png)

  - main方法，函数实现部分；
  - param变量，通过param来获取函数参数；
  - 处理步骤
    1.  获取函数参数；
    2. 对传入参数判断；
    3. 实现函数处理逻辑；
    4. 设置函数返回值；
- pom.xml

  ![pom.xml](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.1_pomFile.png)

  - 增加函数依赖的vjs定义；
  - 增加函数一致性检查相关配置；

## 3.2. 服务端函数

### 3.2.1. 创建工程

- 选择**V3 Webfunc Project**类型，创建工程；

  ![新建工程](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.2_eclipseCreateServerfuncProject.png)

- 编辑工程信息

  ![工程信息](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.2_serverfuncProjectInfo.png)

  - Artifact Id，构件id
  - Version，版本号
  - FuncName，函数编码

### 3.2.2. 函数实现

- 工程目录

  ![工程目录](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.2_serverfuncProjectDir.png)

  - DemoFunc.java，函数实现部分的java代码；
  - pom.xml，保存函数的版本信息，以及需要引用的其他服务信息；

- java文件实现

  ![java文件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.2_javaSourceCode.png)

  - evaluate方法，函数执行时的入口方法；
  - List args变量，通过args来获取函数参数；
  - return，函数的返回值
- pom.xml

  ![pom.xml](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/3.2_pomFile.png)

  - 增加依赖的定义；
  - 增加函数一致性检查相关配置；

# 4. 部署与安装

## 4.1. 开发系统

### 4.1.1. 部署功能构件

![构件部署](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/4.1_deployComponent.png)

- 部署到本地，生成构件包到本地，通过分发构件包文件。其他用户在安装构件时，选择“从本地安装”来安装对应的构件包文件；

### 4.1.2. 安装构件

- 从本地安装，选择本地构件包文件，直接安装该构件包；

  ![构件安装](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/4.1_componentInstall_fromLocal.png)

- 针对函数-功能构件，可以在构件导航栏选中功能构件节点，右键菜单**安装本地功能构件**，把功能构件直接安装到当前的开发系统中。

![安装本地功能构件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/4.1_installComponentToLocal.png)

- 如何判断函数-功能构件安装成功？

  函数-功能构件安装到本地开发系统后，会在`\Plugins\Toone.V3.DevSystem.Function\Resources\CommonFunction`目录下，在根据函数的类型为客户端或服务端，分别对应在`Client`和`Server`目录下。若函数安装成功，会创建以函数编码命名的元数据（xml）文件。

## 4.2. 执行系统

### 4.2.1. 构件打包

![构件打包](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/4.2_exeMavenInstall.png)

- 在Eclipse中选中工程节点右键菜单**Run As**，选择**Maven install**

![构件包项目位置](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/4.2_exePackageFile.png)

- 执行成功后会在项目的``target``文件夹中生成对应的``jar``文件；

### 4.2.2. 安装执行系统构件

![安装构件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/function/4.2_exeInstallFromLocal.png)

1. 进入控制台
    - 开发系统- 开始菜单-> 管理控制台
    - 执行系统- 输入服务地址 + system/console（如：127.0.0.1:8080/system/console）
2. 构件管理
3. 本地构件管理
4. 安装/更新
5. 选择jar包
6. 安装或更新

# 5. 注意事项/常见问题

## 5.1. 开发系统

- 函数编码冲突

  函数-功能构件安装到开发系统时，会以函数编码作为文件名创建对应的元数据文件。对于同一类型（客户端/服务端）但不同的函数，使用了相同的函数编码，则会导致在安装时覆盖了原来的函数元数据文件。