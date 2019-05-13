# 业务规则开发

# 1. 简介

开发基于V3平台的二次开发业务规则。

业务规则，是完成一个业务操作的最小粒度的复用模块，通过不同规则的组合可以完成一个复杂的业务操作。

业务规则的开发包含两部分，开发系统与执行系统。

- 开发系统，对应的是规则配置期的使用；
- 执行系统，对应的是规则运行期的实现；

# 2. 开发系统

## 2.1. 功能构件

### 2.1.1. 新建功能构件

![新建功能构件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.1_createFunctionComponent.png)

- 构件导航栏右键菜单-新建功能构件；
- 构件信息-分类，选择**业务规则**；
- 点击“确定”按钮后创建业务规则-功能构件；

### 2.2.2. 规则编辑器窗体

#### 2.2.2.1. 新建窗体

- 新建窗体作为规则的编辑器窗体；
- 根据实际业务需要添加各种控件，以窗体实体为数据载体；

![控件绑定实体字段](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.2_controlBindingEntity.png)

#### 2.2.2.2. 默认方法

规则编辑器窗体中**必须添加**3个默认方法用于与开发系统交互。

##### GetComponentSchemaData 

用于生成业务规则部署信息，即发送到执行系统的数据；

- 数据会通过方法输出返回给开发系统，因此需要添加方法输出（编码与结构需要与实体保持一致，可以通过**引入实体**操作来快速添加）；

![引入实体](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.2_GetComponentSchemaData_importEntity.png)

![GetComponentSchemaData方法输出](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.2_GetComponentSchemaData_methodOutput.png)

- 通过**给界面实体/控件/变量赋值**规则来把窗体实体的数据赋给方法输出；

![给方法输出赋值](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.2_GetComponentSchemaData_setMethodOutput.png)

- 上面的例子是直接把窗体实体赋值给方法输出。如果需要额外的处理/判断可以通过其他规则来实现；

##### GetViewSnapshotData 

- 该方法默认会输出窗体实体所有数据。**不需要额外配置方法输出**
- 如果输入自定义返回的数据，需要自行设置该方法的方法输出，并在规则链中对方法输出赋值。但是因为在`InitViewData`方法中会把数据解析为窗体实体，所以**方法输出的结构需要与窗体实体保持一致**。否则，会导致数据在`InitViewData`里解析失败。

##### InitViewData 

用于把上次保存的数据还原到窗体控件中，即`GetViewSnapshotData`方法所返回的数据。

- 数据会通过方法输入传递进来，因此需要**创建默认的窗体输入**。

  ![InitViewData方法输入](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.2_InitViewData_methodInput.png)

- 通过`VarToEntity`函数来解析方法输入到窗体实体；

  ```
  VarToEntity(BR_IN_PARENT.input)
  ```

  ![执行VarToEntity函数](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.2_InitViewData_execVarToEntity.png)

### 2.2.3. 执行开发系统方法

某些场景需要获取开发系统配置期的数据，如当前窗体的控件，控件属性等。需要通过**执行开发系统方法**规则来处理；
[执行开发系统方法列表](<https://github.com/opensource-vplatform/vplatform-docs/blob/master/rule/executeNativeMethodList.md>)

![执行开发系统方法](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.3_execDevNativeMethod.png)

- 参数传递

  部分开发系统方法需要设置参数，以获取指定上下文的数据；

- 返回值设置

  开发系统方法返回的数据需要，通过返回值设置赋值给指定的实体对象；

### 2.2.4. 元数据管理

功能构件-元数据管理，主要是用于描述业务规则的基本信息和在安装时生成元数据文件。

![元数据管理入口](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.4_metadata_1.png)

![元数据管理](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.4_metadata_2.png)

- 启动页面，规则编辑器对应的窗体；

- 编码，规则编码；

- 名称，规则名称；

- 版本号，业务规则版本号；

- 是否显示，标识业务规则在规则选择器中是否可见；

- 是否使用，标识业务规则是否可用；

- 构件分类，定义业务规则在哪种构件下可用；

- 规则类型，定义规则在哪种方法内使用，客户端，服务端；

- 事务，支持三种事务类型，有事务、无事务、不明确；

- 规则支持，定义规则在哪种平台下可用，普通窗体、网页窗体、移动窗体、构件方法；

- 规则分类，在规则选择器中的分类；

  ![规则分类](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.4_metadata_3.png)

- 一致性编码，开发系统与执行系统的一致性编码，通过这个编码来关联开发系统与执行系统的对应关系；

- 一致性版本，对应执行系统的一致性版本，执行系统还有会“最低一致性版本”的设置。即开发系统的一致性版本在对应系统系统的一致性版本和“最低一致性版本”之间，则可以通过一致性检查；

- 作者，业务规则作则；

- 描述，业务规则描述；

- 返回值定义，定义业务规则的返回值，在表达式编辑器中可以获取规则返回值；

  ![规则返回值](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/2.4_metadata_4.png)

# 3. 执行系统

## 3.1. 客户端规则

### 3.1.1. 创建工程

- 选择**V3 Webrule Project**类型，创建工程；

  ![新建工程](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.1_eclipseCreateWebRuleProject.png)

- 编辑工程信息

  ![工程信息](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.1_webRuleProjectInfo.png)

  - Artifact Id，构件id
  - Version，版本号
  - RuleName，规则编码

### 3.1.2. 规则实现

- 工程目录

  ![工程目录](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.1_webRuleProjectDir.png)

  - DemoRule20150509.js，规则启动后运行的js，规则的所有逻辑都在这个js内；
  - pom.xml，maven工程的配置文件，vjs的依赖也需要在这里进行配置；

- js文件实现

  ![js文件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.1_jsFile.png)

  - main方法，规则实现部分；
  - ruleContext，规则上下文；
  - jsonUtil，vjs工具类，通过获取服务的形式调用；

- pom.xml

  ![pom.xml](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.1_pomFile.png)

  - 配置规则依赖的vjs定义；
  - 规则一致性检查相关配置；

## 3.2. 服务端规则

### 3.2.1. 创建工程

- 选择**V3 Serverrule Project**类型，创建工程；

  ![新建工程](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.2_eclipseCreateServerRuleProject.png)

- 编辑工程信息

  ![工程信息](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.2_serverRuleProjectInfo.png)

  - Artifact Id，构件id
  - Version，版本号
  - RuleName，规则编码

### 3.2.2. 规则实现

- 工程目录

  ![工程目录](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.2_serverRuleProjectDir.png)

  - DemoRule20150512.java，规则启动后运行的java代码；

- java文件实现

  ![java文件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/3.2_javaFile.png)

  - evaluate方法，规则实现部分；

    上图示例简单地把入参打印出来，实际工作中，应该是针对入参进行解析，完成相应功能。

  - RuleContext，规则上下文；

# 4. 部署与安装

## 4.1.开发系统

### 4.1.1. 部署功能构件

![构件部署](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/4.1_deployComponent.png)

- 部署到本地，生成构件包到本地，通过分发构件包文件。其他用户在安装构件时，选择“从本地安装”来安装对应的构件包文件；

### 4.1.2. 安装构件

- 从本地安装，选择本地构件包文件，直接安装该构件包；

  ![构件安装](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/4.1_componentInstall_fromLocal.png)

- 针对业务规则-功能构件，可以在构件导航栏选中功能构件节点，右键菜单**安装本地功能构件**，把功能构件直接安装到当前的开发系统中。

  ![安装本地功能构件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/4.1_installComponentToLocal.png)

- 如何判断业务规则-功能构件安装成功？

  业务规则-功能构件安装到本地开发系统后，会在 `\Plugins\Toone.V3.DevSystem.MethodEditor\RuleEditor\` 目录下，再根据业务规则的类型为客户端或服务端，分别对应在`Client`或`Server`目录下。若规则安装成功，会创建以规则编码命名的文件夹，文件夹里有规则的元数据（xml）文件。如果是通过编码开发的规则，会有有规则编辑器对应的dll文件。

## 4.2. 执行系统

### 4.2.1. 构件打包

![安装打包](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/4.2_exeMavenInstall.png)

- 在Eclipse中选中工程节点右键菜单**Run As**，选择**Maven install**

  ![构件包项目位置](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/4.2_exePackageFile.png)

- 执行成功后会在项目的``target``文件夹中生成对应的``jar``文件；

### 4.2.2. 安装执行系统构件

![安装构件](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/rule/4.2_exeInstallFromLocal.png)

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

- 规则编码冲突

  规则构件安装到开发系统时，会以规则编码作为文件夹名称创建对应的目录。如果不同的规则使用了相同的规则编码，则会导致在安装的时候覆盖了原有的规则。
  
  
  
  
  
  

