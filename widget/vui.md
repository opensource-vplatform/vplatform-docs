# 自定义控件开发

## 一、基础知识

高效的开发，离不开基础工程的搭建。在开始自定义窗体开发之前，有必要先了解以下基础知识：

[Vue 教程](https://cn.vuejs.org/v2/guide/)

[Vue API](https://cn.vuejs.org/v2/api/) 

[Vue 组件](https://cn.vuejs.org/v2/guide/components.html) 

[Vue 风格指南](https://cn.vuejs.org/v2/style-guide/)

[Vue 单页面开发](https://segmentfault.com/a/1190000005667546) 

[Vui 控件标签使用指南](http://service.yindangu.com:8018/module-operation!executeOperation?componentCode=divusermanual&windowCode=div_userguide#top_nav_menu) 

## 二、环境准备

* 窗体自定义开发基于nodejs环境，如果本机没有安装nodejs，请到官网（https://nodejs.org/en/）下载nodejs，并安装。
* 本地开发推荐编辑器VSCode（https://code.visualstudio.com/）


![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15578013269429.png)

## 三、使用指令
*  **v3:package**   使用webpack打包    `npm run v3:package`
*  **v3:test/v3:start**   启动本地测试服务     ` npm run v3:start    `
*  **v3:pack**   将控件打包成vstore构件      `npm run v3:pack  `
*  **v3:publish**   将控件部署到vstore仓库     `npm run v3:publish `
*  **v3:apply**   将控件安装至指定的执行系统      `npm run v3:apply  `
*  **v3:init**       更新控件的webpack配置文件      `npm run v3:init `
*  **v3:install**   给控件安装平台的资源构件        `npm run v3:install XXX`
*  **v3:uninstall**  将控件中安装的资源构件选择性卸载    `npm run v3:uninstall XXX`

## 四、初始化环境

1. 新建一个目录，如：example
2. 在cmd命令行中    `cd example`
3. 执行命令   

```
npm install v3-cli –save-dev
```

4. 根据指引设置控件信息，设置完成后，v3-cli脚手架会自动生成模板工程

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577996071226.png)

* **Vstore仓库**：发布至Vstore的指定仓库
* **插件类型**：生成的自定义控件的类型，widget为二次开发控件，resource为资源构件
* **项目（构件）名称**：自定义
* **组织id**：默认平台id，可自拟
* **匹配版本号**：默认1
* **应用范围**：V平台适用窗体类型（all全部、web网页版、mobile移动版）

## 五、工程目录结构

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577982521214.png)

*  **build文件夹：**存放webpack配置文件信息

	A、**webpack.config.js**： webpack打包配置主入口 **（请不要更改）**

	B、**webpack.ext.config.js**：控件额外配置文件，如果控件需要额外定制打包配置，请调整此文件。

	C、**v3文件夹**：存放v3平台webpack打包配置文件**（请不要更改）**

*  **dist文件夹**：存放输出文件
*  **examples文件夹**：存放样例文件
*  **node_modules**：生成的相关依赖
*  **.babelrc** ：Babel转译配置项
*  **.v3devrc**：v3平台二次开发配置信息
*  **package.json**：配置说明
*  **package-lock.json**：当前安装的包相关的依赖


   ![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/1556085112188.png)

* **src文件夹**:存放源码文件

	A、**static文件夹**：存放静态文件

	B、**widgets文件夹**：存放控件定义信息

* **index.js文件**：控件注册信息 **（请不要更改）**

* **index.vue文件**：控件定义

* **theme.less文件**：控件样式class定义

* **var.less文件**：控件样式变量定义


## 六、控件开发规范详解

### 1、控件实现 

#### 属性定义

为了二次开发控件与平台实体数据实现无缝衔接，建议在二次开发控件中，涉及到数据绑定的属性使用平台实体数据格式。

平台实体是一个数组，数组的每一项都是对象，对象中key值为字段编号，value值为字段值。

二次开发标签与实体数据绑定一般有三种类型：

1. 单行单值类型：绑定单个字段，如输入框等。

```
//例：单值类型
props : {
    value : {
        type : String
    }
}

```

2. 单行多值类型：绑定多个字段，如下拉选择：同时绑定标识值与显示值。

```
//例：多值类型
props : {
    //多值类型的itemSource为实体数组中的当前行对象，一般为第一行
    itemSource: {
        type: Object,
        default: function() {
            return {};
        }
    },
    itemValue: {
        type: String,
        default: "id"
    },
    itemText: {
        type: String,
        default: "text"
    },
},
```

3. 多行类型：绑定整个实体，如列表等

```
//例：绑定多行类型
props : {
    itemSource: {
        type: Array,
        default: function() {
            return [];
        }
    },
    itemValue: {
        type: String,
        default: "id"
    },
    itemText: {
        type: String,
        default: "text"
    },
},
```

实体字段类型包括：文本、整数、小数、布尔。
> 如果需要绑定别的数据类型，建议在二次开发控件内部将数据先转换为实体字段类型之一，再去绑定平台实体。

#### 控件代码
widgets文件夹 `index.vue`，编写控件代码

```
<template>
    <div>
        <button @mouseover = "isHidden = false" @mouseout = "isHidden = true">
            {{title}}
            <span class = "downBtn"></span>
            <div class = "dropdown-box" :class = "{hidden:isHidden}">
                <ul>
                    <li v-for = "item in items" @click = "onclick(item.text)">{{item.text}}</li>
                </ul>
            </div>
        </button>
    </div>
</template>
<script>
export default {
	name : "v3dropdown",
	props : {
        itemSource: {
            type: Array,
            default: function() {
                return [];
            }
        },
        itemValue: {
            type: String,
            default: "id"
        },
        itemText: {
            type: String,
            default: "text"
        },
        onClick : Function,
        title : String
	},
	data : function(){
		return {
			isHidden:true,
			items: []
		};
	},
	watch : {
        itemSource: {
			handler: function(nVal, oVal) {
				this.updateItems();
			},
			deep: true
        }
    },
    created : function(){
        this.updateItems();
    },
	methods : {
		onclick : function(item){
			this.$emit('on-click',item);
		},
		updateItems: function() {
            var items = [];
            for (var i = 0, l = this.itemSource.length; i < l; i++) {
                var val = this.itemSource[i];
                var _value = val[this.itemValue];
                var _text = val[this.itemText];
                var _checked = val[this.itemChecked]
                items.push({
                    value: _value,
                    text: _text
                });
            }
            this.items = items;
        }
	}
}
</script>
```


### 2、编写本地样例

examples文件夹 `index.html`本地写测试代码页面

```
new Vue({
	el : "#app",
	template : '<v3dropdown :title = "title" :dropSource = "dropSource" @on-click="click1"></v3dropdown>',
	data : {
		dropSource : ['test1','test2','test3','test4'],
		title : '下拉菜单'
	},
	methods:{
		click1:function(index){
			alert(index);
		}
	}
});
```

### 3、控件样式引入皮肤变量

在 `var.less`文件中引入皮肤变量： `@vPlatformMobileSkinVar` 或   `@vPlatformWebSkinVar`，在 `theme.less`中使用 

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/1556090378630.png)

```
import '~@vPlatformBaseSkinVar';
//网页版皮肤变量
import '~@vPlatformWebSkinVar';
//移动版皮肤变量
import '~@vPlatformMobileSkinVar';

.test1{
	width:100px;
	height:100px;
	background:@primaty-color;
}
.test2{
	width:100px;
	height:100px;
	background:@m-success-color;
}
```

[皮肤变量查询](https://github.com/opensource-vplatform/vplatform-docs/blob/master/skinVariable/skinVariable.md)


### 4、控件安装资源构件

执行  ` npm run v3:install XXX`，有本地安装和从Vstore仓库安装两种方式

**方式1**：本地安装

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15571919888752.png)

红框为资源构件生成的jar包所在的绝对路径

**方式2**：Vstore仓库安装

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15571923571910.png)

第一个红框为资源构件的构件名

第一个红框为选择资源构件所在的Vstore仓库，二次开发构件要与资源构件在同一个仓库中

### 5、控件卸载资源构件
执行   `npm run v3:uninstall XXX`

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577997713024.png)

红框为需要卸载的资源构件的构件名称


### 6、本地编译预览

**方式1**：执行` npm run v3:start `，可以启动本地测试服务实时预览效果

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577990545510.png)

执行npm run v3:start，会自动选择可用端口，自动打开浏览器

本地修改代码之后，无需重新执行npm run v3:start，保存代码之后刷新浏览器即可更新预览界面

**方式2**：执行 `npm run v3:package`，dist文件夹下输出的index.html可以直接预览效果

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577983665154.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577984141142.png)


### 7、打包生成Vstore构件
执行  `npm run v3:pack`

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577984639263.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15577985413985.png)


### 8、部署到Vstore仓库
执行 `npm run v3:publish`

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/1557798650553.png)

红框为第一次部署到Vstore仓库时，会要求输入Vstore账号和密码。


### 9、安装到指定V3服务

执行  `npm run v3:apply`

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/1557798736930.png)

红框为第一次安装到服务时，会要求输入Vstore账号密码，以及安装到指定的执行系统地址。

### 10、V3中使用

以v3dropdown为列子，先在指定执行系统中安装v3dropdown控件，开发系统中创建一个自定义窗体，打开div编辑器

```
<div>
	<v3dropdown :title="btnTitle" :item-source="dataSource" item-value="value" item-text="title" @on-click="onClick">
</div>
```

部署窗体预览效果

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/widget/vui/15578011604345.png)
