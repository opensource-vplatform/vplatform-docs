# 自定义窗体开发
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


![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555919091559.png)

## 三、使用指令
*  **v3:package**   使用webpack打包  npm run v3:package

*  **v3:start**   启动本地测试服务    npm run v3:start    

## 四、创建生成代码工程

### 1、创建自定义模板窗体
> 当前支持网页窗体、移动窗体

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555919266183.png)

### 2 、创建实体并设置测试数据

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555919593370.png)

### 3 、导出构件工程

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555919642038.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555919644715.png)

## 五、工程目录结构

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555921020794.png)

*  **node_modules：**生成的相关依赖模块（无需关注）

*  **src：**源代码

*  **export_test1：**构件名称

*  **share：**构件内共享资源文件 js、css、图片

*  **views：**窗体集合

*  **form1、form2：**窗体名称

*  **package.json：**配置说明

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555921348239.png)

*  **entities.js：**数据实体定义（无需关注）

*  **index.vue：**窗体页面（HTML、CSS、JS）

*  **metadata.json：**工程元信息（无需关注）

*  **theme.less：**窗体样式定义

*  **var.less：**窗体样式变量定义

*  **form1、form2：**窗体名称

*  **entities.json：**测试数据

## 六、本地开发规范详解

### 1、已生成的测试数据及应用

导出的代码工程会带上已生成的测试数据

```
  "infolist": [
    {
      "item": "基本配置",
      "content": "海纳百川精选全球的高品质软件与服务，大咖云集，知识分享的开发者技术社区",
      "price": "99"
    },
    {
      "item": "标准配置",
      "content": "海纳百川精选全球的高品质软件与服务，大咖云集，知识分享的开发者技术社区",
      "price": "199"
    },
    {
      "item": "高端配置",
      "content": "海纳百川精选全球的高品质软件与服务，大咖云集，知识分享的开发者技术社区",
      "price": "299"
    }
  ]

```

```
<div class="box">
	<Row>
		<i-col :xs="24" :sm="12" :md="8" v-for="infolist in infolist" :key="infolist.id" style="padding-left: 10px;padding-right: 10px;">
			<div class="itemBox">
				<div class="content">
					<h3>{{infolist.item}}</h3>
					<p>{{infolist.content}}</p>
				</div>
				<div class="price">
					<p>￥{{infolist.price}}</p>
				</div>
				<div class="buybtn">
					<a>立即购买</a>
				</div>
			</div>
		</i-col>
	</Row>
</div>
```

### 2、样式规范

页面样式部分推荐使用平台本身提供的默认样式变量，
如果在share下面的Vue组件使用样式变量，可在Vue组件的页面里面引入：

```
import '~@vPlatformBaseSkinVar';
import '~@vPlatformWebSkinVar';
import '~@vPlatformMobileSkinVar';

.box{
	background:@v-primary-color;
	height:100%;
	width:100%;
	color:@v-text-title-color;
}
```

### 3、引入插件、第三方JS

**方式1**:通过npm安装相关依赖

例：安装 Element UI
>npm i element-ui -S

```
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';
```

**方式2**:手动引入，将相关文件放入share文件夹下面，import直接引入相对路径下的文件
例：“@share/xx/xx”

```
import Swiper from '@share/swiper.min.js';
import '@share/swiper.min.css';
```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555922717541.png)

**方式3**:引入Vue组件

vue组件放置于share文件夹

* import引入vue文件

* components定义

```
<template>
	<div class="app bg">
    	<img width="128px" height="128px" src="@share/logo.png">
		<HelloWorld :blankurl="blankurl" />
	</div>
</template>
<script>
  	import vdk from 'v3-vdk';
	import entities from './entities.js';
	import HelloWorld from "@share/HelloWorld.vue";
	export default {
		components: {
			HelloWorld
		},
		props: entities,
		data: function(){
			return {
				msg: "欢迎学习V3开发技术"
			};
		}
	};
</script>
```

### 4、事件关联

关联事件的标识为$emit

如：this.$emit("XXX");

v-on:click=''$emit('XXX')''

```
<i-button typr="primary" @click="onClik">Primary</i-button>
<i-button typr="success" v-on:click="$emit('onClik')">Success</i-button>
```

```
onClick:function(){
	alert("This is click");
	this.$emit("clickEvent','a','b','c')
}
```

### 5、指令使用

* npm run v3:package

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555932493243.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555932543181.png)

* npm run v3:start

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555932570038.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555932579288.png)

### 6、约束规范

针对网页窗体开发目前有以下约束和建议：

**1、不可引用【Bootstrap】UI库及其相关组件**

**2、V平台已内置第三方Vue UI库 【iView 2.0】，可直接使用iView标签**

**3、V平台有提供内置官方UI库【VUI】，建议在面向企业应用类场景使用**

## 七、导入V3开发系统

### 1、导入构件代码工程

如下图，两个地方皆可导入构件代码工程

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933211142.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933215810.png)


### 2、在开发系统编辑器打开

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933432305.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933440265.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933443733.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933446612.png)

### 3、部署构件

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933468671.png)

### 4、预览效果

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/customWindow/1555933472474.png)
