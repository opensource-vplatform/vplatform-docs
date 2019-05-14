# 控件二次开发

## 1. 简介

开发基于V3平台的二次开发控件

### 1.1. 概述

### 1.2. 名词解释

1. **构件编码ComponentCode**
	- 业务构件的全局唯一标识。

2. **控件系列Series**
	- 控件类型标识，同一类控件，通常使用同一套前端UI实现。
    
3. **窗体编码WindowCode**
	- 当前构件下窗体唯一标识

4. **控件编码WidgetCode**
	- 当前窗体下控件唯一标识

### 1.3. 控件开发准备

1. **控件系列、控件编码**
    -  控件唯一标识，需要在开发前就确定下来

2. **外观、交互效果**
    - 首先控件开发之前，需要了解控件的外观、交互效果部分，这是控件最重要的部分。接下来的一些设计实现，
都需要从这里入手，这个也直接决定了这个控件适合使用什么UI进行实现。

3. **控件数据存储**
    - 确定控件关联的数据规模，常见的有：
      - 关联某个实体的一列 	例如：文本，长文本等。
      - 关联某个实体多列		例如：下拉选择，多选组等
      - 关联某个实体		例如：列表、树表等
      - 完全不关联实体		例如：按钮、标签等

4. **控件支持的事件**
    - 控件支持哪些事件类型。当触发了事件之后，必须执行预先配置好的规则。

5. **需要支持哪些规则**
    - 某些规则会直接操作到控件上，如显示隐藏、控件属性调整等。那么这个时候就需要控件对外提供特定的接口予以支持。

### 1.4. 控件介绍-控件分类

- 控件有很多中，无论是在普通窗体还是网页窗体，
按照功能以及作用我们大致可以分为如下几类：

1. **布局控件**
    - 如面板，容器等，本身并不带任何内容，但是可以装载其他的控件，或者窗体。

2. **静态控件**
    - 标签，按钮等，控件的外观，以及内容在定义期就完全决定下来，不需要绑定实体数据

3. **字段控件**
    - 文本框等输入类的控件，和数据源绑定，用于数据录入，或者数据展示。控件开发重点在于数据同步。

4. **第三方插件控件**
    - 如图表、报表等控件，主要是把第三方的插件或者控件进行封装，开发控件的时候主要是解决兼容性问题以及了解第三方控件的api和事件。

### 1.5. 控件介绍-控件系列

- 目前控件主要有三个控件系列，也对应着有三个渲染引擎。

1. 普通窗体
	
2. 网页窗体
	
3. 移动窗体
	

> 注意：下面讲是 **普通窗体** 的开发，以文本输入框为例。

### 2. 开发系统

#### 2.1. 功能构件

##### 2.1.1. 新建功能构件

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557109447222.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557714257252.png)



1. 构件树顶部工具栏-新建功能构件

2. 构件树右键菜单-新建功能构件

3. 构件信息-分类，选择【**控件**】

4. 点击“确定”按钮后创建控件-功能构件

5. 新建完成，在构件中只需要关注【**资源管理**】和【**元数据管理**】

 ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557714299730.png)



#### 2.2.2. 元数据管理

1. 配置控件信息；

2. 配置控件属性信息

##### 2.2.2.1. 控件定义

 ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557714415013.png)


- **基本设置**

1. 编码：设置控件的元数据编码（**必填**）
    > 注意编码的唯一性

2. 名称：设置控件的名称（**必填**）

3. 版本号：设置控件的版本号（**必填**）
    > 这里不需要手动修改，默认同步功能构件的版本，只需修改功能构件版本号即可

4. 窗体类型：设置控件用到什么窗体上
    >可选 普通窗体、网页窗体、移动窗体

5. 控件分类：设置控件在工具箱中的分类
    >可选 通用控件、字段控件、业务控件

6. 是否显示：设置控件是否在工具箱中显示

7. 提供者：设置开发者

8. 描述：设置控件描述

- **平台一致性设置**

1. 一致性校验：设置控件在部署的时候是否需要进行一致性校验
    >建议启用，可以确保执行系统和开发系统版本一致

2. 一致性编码：设置一致性校验编码
    >注意编码唯一性，一般用默认生成的即可

3. 一致性版本：设置一致性校验的版本
    >默认从1开始，每次多控件属性的增删都应该给其加 1

- **样式设置**

  需要将图标文件放到【**构件资源**】中
    
1. 控件图标：设置控件在工具箱中显示的小图标
    >图标大小以 16 * 16 px 为佳

2. 样式缩略图：设置控件拖拽到窗体设计器中显示的样式缩略图

3. 样式模板：

    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126219780.png)


    - 模版是通过html形式编写,用于在将控件拖到开发系统画布之后的显示效果
··
    - 模版一般由html,js ,css ,图片这些组成
    
    > 配置了模版之后, 样式缩略图配置无效

    样式界面html模板,使用以下代码继续实现

    ```
    <!DOCTYPE HTML>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>basic-demo</title>

    <!-- 以下两项不可少，也不可修改， 原本复制过去 -->
    <script>#ScriptLib#</script>
    <style>#CssLib#</style>

    </head>

    <body>
    <script id="test" type="text/html">
        /* 标签写这里 */

        /* 示例 ：双大括号{{}} 包裹这就是对于的属性编码 */
        /*
        <div class="col-xs-{{DisplayScale}} row" style="padding-top:{{Top}}px;padding-right:{{Right}}px;padding-bottom:{{Bottom}}px;padding-left:{{Left}}px;">
            <button  type="button" class="btns btns-default"style="border-radius:{{Radius}};background-color:{{LabelBackColor}};color:{{LabelForeColor}};">{{LabelText}}</button>
        </div>
        */
    </script>
    <div id="content"></div>

    <!-- 这个script不能少 原本的复制过去 -->
    <script>
        var data = #Data#;
        var html = template('test', data);
        document.getElementById('content').innerHTML = html;
    </script>

    </body>
    </html>
    ```

- **扩展设置**

  ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126255001.png)

1. 控件扩展：配置控件的扩展点，让该控件可以扩展自己的子控件
    > 如果该控件支持扩展，在这里配置之后，其他控件可以在【扩展实现】中选择到这里配置的扩展点

2. 扩展实现：选择要实现的扩展
    > 选择一个扩展点，该控件将会成功扩展控件的子控件

    > 选择之后，【控件属性定义】会自动生成一个ExtPoint属性, 注意：这个属性**不可修改、删除**

    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557109994689.png)


##### 2.2.2.2. 控件属性定义

   ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557110085359.png)

   > 注意：第一次新建功能构件会自动生成平台不可缺少属性，这些属性**不要随意删、改**

   > 如果不小心删除，莫慌，点击【**引入必须的属性**】即可

- **属性定义**

1. 新增属性：新增一个属性
   > 属性编码和属性名称都是 必填；平台内置了一些常用的，点击【下拉选择】一个想要的，或者选中文本框，自行输入属性编码和名称
  
      ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557110282760.png)


2. 删除属性：删除一个属性

3. 引入必须的属性

- **属性的属性定义**

1. 属性值数据类型
    > 设置该属性的值的数据类型，如:高度的为 System.Int32

2. 属性值编辑器
  
    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126284731.png)

     > 设置该属性值使用的编辑器，可以使用 系统内置、二次开发的属性编辑器；默认为空，使用普通的文本编辑器

     > 二次开发的属性编辑器的开发 请查看 【**属性编辑器二次开发**】 流程

3. 自定义下拉选择项数据
    
    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126316733.png)

     > 自定义下拉选择项数据：在【**选项数据源设置**】窗体配置要显示值和保存值,安装后即可在属性编辑器选择
    
     > 注意： 必须将 **【属性值编辑器】** 设置为
     **自定义下拉选择项编辑器 【CustomDropDownListEditor】** 以上配置才生效

4. 初始值

     > 定义该属性的初始值(默认值)

5. 属性类型
    
     ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557716027093.png)

     > 在属性视图中的分类， 可选 数据、事件、格式、其他

6. 是否为复杂的属性

     ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126378377.png)

     > 标识该属性是否为复杂的属性，一般值比较多,可以设置为true ，如：JSON

     > true， 配置的属性值 显示为【已设置】； false， 直接显示值

7. 属性是否可用

    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126403016.png)

     > true 启用；false 禁用，属性列表中显示为灰色，不能进行编辑

8. 是否可以编辑
    > true 可编辑；false 只读

9. 显示
    > 设置是否在属性列表中显示； true 显示、false 隐藏

10. 常用属性

    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557727648982.png)
     > 设置是否可以显示在属性列表中常用分类中； true 显示

11. 是否样式属性

    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126427033.png)
     > 设置为true之后，在【**默认样式**】的编辑器中可以对其进行编辑，一般为字体，颜色等样式类型才这么弄

12. 是否为实体
    > 注意：如果该属性确实是实体，请务必设置为true

13. 是否为实体字段
    > 注意：如果该属性确实是实体字段，请务必设置为true

14. 属性是否可以生产代码Code
    > 设置为 false，在属性列表中配置的属性值将不会保存； 默认 true

15. 属性是否部署
    > 设置为 false，此属性将不会在部署包中生成； 默认 true

16. 允许赋值

    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557727506143.png)

    > 设置为 true，此属性可以在【**控件属性设置**】规则使用

    > 说明：真正的赋值操作还需要此控件的执行系统部分实现

17. 允许取值

    ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557727561476.png)

    > 设置为 true，此属性可以在【**表达式编辑器**】中使用

    > 说明：真正的取值操作还需要此控件的执行系统部分实现

18. 属性值验证表达式

     ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557112132815.png)

     > 设置一组正则表达式，用来验证属性值的合法性

19. 描述

     ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557727605278.png)

     > 对该属性的基本描述，一般用来说明 使用方法、值分类、注意事项等等

     > 此描述会出现在属性列表的 描述区域

## 3. 执行系统

### 3.1. 使用控件向导建立控件项目

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557112466055.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557112426443.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557711639497.png)

- **填写项目属性**

1. Group Id:(不需要修改)
    - com.toone.v3.platform
2. Artifact Id:
    - widget-smartclient-JGTextBoxExt
3. Version:
    - 3.3.1-SNAPSHOT          (初始版本号)
4. Series：
    - smartclient
5. WidgetCode:
    - JGTextBoxExt

- **完成项目创建**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557112636447.png)


### 3.2. 代码的文件结构

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557711797978.png)



1. JGTextBoxExtAction.js
    - 控件对外接口部分
2. JGTextBoxExtHandler.js
    - 控件数据同步实现
3. JGTextBoxExt.js
    - 控件渲染相关实现
4. JGTextBoxExt.less
    - 控件样式部分，less模版
5. property.xml
    - 控件属性元数据定义
6. pom.xml
	- 控件vjs服务依赖及版本定义

### 3.3. 增加第三方依赖类库或插件(property.xml)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557113823495.png)

```
<property name = "RequireJS" type = "string" required = "true" canEmpty = "true" defaultValue = "extra/thirdpart/textbox/js/jquery-3.2.1.js,extra/thirdpart/textbox/js/loader.js" />
```

- 依赖的资源，这里的资源可以是js或者css。可以使用这种方法，进行资源引入。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557712266420.png)


- 对应目录：前面的路径固定为： resource/page/itop/common/<控件系列>/ 

### 3.4. 增加控件属性(property.xml)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557113935980.png)


```
<!-- 静态属性 -->
<property name="IsAtomicType" defaultValue="true" type="string" required="false" canEmpty="true" desc="是否原子"/>
<!-- 静态属性 -->
<!-- UI属性 -->
<property name="ReadOnly" type="boolean" required="true" canEmpty="false" desc="只读"/>
<property name="TextLength" type="number" required="true" canEmpty="true" desc="文本长度"/>
<property name="LabelVisible" type="boolean" required="true" canEmpty="true" desc="显示标题"/>
<property name="DefaultValue" type="string" required="true" canEmpty="true" desc="默认值"/>
<property name="LabelWidth" type="number" required="true" canEmpty="true" desc="标题宽度(%)"/>
<!-- UI属性 -->

```

1. **必写**，defaultValue=“true”表示该控件内不可放入其他控件，false表示可放入其他控件，比如容器类控件；
2. name 属性值对应 **开发系统中配置的属性编码**
3. type 属性值支持 code, string, event, number, boolean

### 3.5. 增加事件属性(property.xml)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557114082214.png)


```
<!-- 事件 -->
<property name="OnEnter" type="event" required="true" canEmpty="true" desc="获取焦点"/>
<property name="OnLabelClick" type="event" required="true" canEmpty="true" desc="单击标题"/>
<property name="OnValueChanged" type="event" required="true" canEmpty="true" desc="值改变事件"/>
<property name="OnValueLoaded" type="event" required="true" canEmpty="true" desc="值加载事件"/>
<property name="OnKeyDown" type="event" required="true" canEmpty="true" desc="键盘按下"/>
<property name="OnLeave" type="event" required="true" canEmpty="true" desc="焦点移开"/>
<!-- 事件 -->

<events>
	<event name="OnEnter" desc="获取焦点"/>
	<event name="OnLabelClick" desc="单击标题"/>
	<event name="OnValueChanged" desc="值改变事件"/>
	<event name="OnValueLoaded" desc="值加载事件"/>
	<event name="OnKeyDown" desc="键盘按下"/>
	<event name="OnLeave" desc="失去焦点"/>
</events>
```

### 3.6. 指定控件数据源类型(property.xml)

需要绑定数据源的控件，可根据控件的实际情况指定数据源的类型（storeType）

1. singleRecord（单值类型）

     ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126478054.png)

   - 如：文本、小数、整数等，代表单行记录中的某个字段值的控件
单值类型的数据源只需指定一个字段

2. singleRecordMultiValue（多值类型）

     ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126503904.png)

   - 如：下拉选择，多选组、单选组等，需要同时存储控件的标识值和显示值的控件
多值控件一般需要绑定二个或以上的字段

3. set（多行类型）

     ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126525044.png)

    - 如：列表、树表、分页控件等，代表多行记录的控件
该类型一般不需要指定具体绑定哪个字段，如果有特殊需要也可指定绑定字段

本例（文本JGTextBoxExt）中需要绑定的数据源为单值类型。
![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557121192425.png)
```
<!-- 数据 -->
<property name="TableName" type="tableName" required="true" canEmpty="true" desc="实体"/>
<property name="ColumnName" type="columnName" required="true" canEmpty="true" desc="字段名称"/>
<!-- 数据 -->
```

```
<dataBindings>
	<dataBinding name="datasource" required="false">
		<storeType>singleRecord</storeType>
		<dataSource name="TableName" canEmpty="true" desc="实体"/>
		<dataMembers>
			<dataMember name="ColumnName" type="String" canEmpty="true" isRelation="false" desc="字段名称"/>
		</dataMembers>
	</dataBinding>
</dataBindings>
```


### 3.7. 控件渲染(render下的JGTextBoxExt.js)
控件向导初始化后，js文件中会生成模版。

**控件模块初始化：**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557712454345.png)

**控件UI定义：**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557712832343.png)


**控件UI初始化，产生UI实例：**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557123234085.png)



### 3.8 数据同步(data下的JGTextBoxExtHandler.js)

UI中的数据变化后，会自动同步到数据源，无需做处理。
只需要处理数据源的数据变化后，同步到UI中。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557713135325.png)



### 3.9 增加控件样式(JGTextBoxExt.less)
在JGTextBoxExt.less 文件中添加对应的样式

1.  @{WidgetStyle}表示控件名，如JGTextBoxExt

2. 可直接把第三方css直接复制入该文件

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557713236078.png)



### 3.10 事件绑定及提供控件对外接口(action下的JGTextBoxExtAction.js)

1. 获取必要的服务（下面使用）
2. 绑定事件，事件触发后执行对应的规则
3. 提供控件的对外接口

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557713314477.png)


![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557124028462.png)

### 3.11 控件版本修改(pom.xml)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557713457554.png)




## 4. 控件部署与安装

### 4.1.开发系统

#### 4.1.1. 部署构件

 部署到本地，生成构件包到本地，通过分发构件包文件。其他用户在安装构件时，选择“从本地安装”来安装对应的构件包文件
 
![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557124795935.png)


#### 4.1.2. 安装构件

1. 从本地安装，选择本地构件包文件，直接安装该构件包；

 ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557126571903.png)


2. 安装本地功能构件，在构件导航栏选中功能构件节点，右键菜单**安装本地功能构件**，把功能构件直接安装到当前的开发系统中。

 ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557124837829.png)

3. 如何判断控件-功能构件安装成功？

    > 查看在**工具箱**中是否有此控件节点
    
  ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557124929467.png)


### 4.2. 执行系统

> 注意：以下出现的所有构件名称、打包路径等都是例子；实际名称、路径要以开发的实际情况为准

#### 4.2.1 构件打包

1. 打包后自动生成构件包

2. 获取生成构件包的路径

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557129507930.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557714000396.png)


在target下生成的构件包，右键选择Properties，会自动生成构件包的路径

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557714038868.png)


![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557714101825.png)


```
D:\work\eclipse\eclipse-v3-allinone\workspace\widget-smartclient-JGTextBoxExt\target\com.toone.v3.platform-widget-smartclient-JGTextBoxExt-1.0.0-SNAPSHOT.jar
```


#### 4.2.2 安装执行系统构件

1. 进入控制台
   - 开发系统- 开始菜单-> 管理控制台

2. 执行系统- 输入服务地址 + system/console（如：127.0.0.1:8080/system/console）

3. 构件管理

4. 本地构件管理

5. 安装/更新

6. 选择jar包

7. 安装或更新

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557130880298.png)



## 5. 验证

#### 5.1. 部署业务构件demo	    
   开发系统新建一个业务构件，新建普通窗体，从工具箱中拖拽JGTextBoxExt控件到右侧窗体中，在最右侧配置文本控件的属性及事件，部署。
   
![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557125658515.png)

#### 5.2. 验证

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557125847815.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/smartclient/1557125888004.png)

## 6. 注意事项/常见问题

> 要注意 控件编码，属性编码的唯一性
