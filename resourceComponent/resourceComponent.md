# 资源构件开发
## 一、功能需求背景
1.需要抽提公用的资源构件

2.需要引入第三方资源（js库、样式库等）


## 二、创建资源构件脚手架
使用npm方式安装 v3-cli ，执行`npm install v3-cli --save-dev`

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image1.png)


安装完v3-cli插件后，会出现安装向导，根据安装向导完成创建构件模版。


## 三、命令说明

*  **v3:package**   使用webpack打包    npm run v3:package
*  **v3:test/v3:start**   启动本地测试服务     npm run v3:start
*  **v3:pack**   将控件打包成vstore构件    npm run v3:pack
*  **v3:publish**   将控件部署到vstore仓库   npm run v3:publish
*  **v3:apply**   将控件安装至指定的执行系统   npm run v3:apply
*  **v3:init**       更新控件的webpack配置文件     npm run v3:init
*  **v3:install**   给控件安装平台的资源构件       npm run v3:install XXX
*  **v3:uninstall**  将控件中安装的资源构件选择性卸载   npm run v3:uninstall XXX

## 四、样例

### (一)引入第三方ui（element-ui）

#### Step1：创建element-ui-lib构件资源

1.创建element-ui-lib文件夹，在该文件夹下执行命令：`npm install v3-cli --save-dev`

2.安装完成后，会出现向导，按照需求填入相关信息。
**插件类型选择  `resource`**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image2.png)


3.在element-ui-lib文件夹中安装element-ui插件，执行:`npm install element-ui --save`

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image3.png)


4.插件安装完成后，在element-ui-lib/index.js中添加对element-ui的使用，此处使用方式参考[element ui官网](http://element-cn.eleme.io/#zh-CN)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image4.png)

```
import element from 'element-ui';
import 'elemet-ui/lib/theme-chalk/index.css';
import vue from 'vue';
vue.use(element);
```

#### Step2：部署到vstore仓库，执行`npm run v3:publish`

第一次部署到vstore仓库时，会要求输入vstore账号和密码。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image5.png)


部署到vstore仓库完成后，进入**开发系统控制台 => 构件管理 => 动力平台构件仓库 => 选择部署的vstore仓库 **，可找到该资源构件。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image6.png)


#### Step3：使用资源构件

##### 自定义窗体中使用element-ui-lib构件资源

##### A.执行系统处理

在执行系统中安装element-ui-lib资源构件（将来此步可以省略，目前正在处理）。控制台选择**构件管理 =》 构件动态安装（动态升级） =》 选择对应的库 =》 选择批量安装列表 =》 安装该资源构件**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image7.png)


##### B.开发系统处理
##### 1.在开发系统中安装element-ui-lib资源构件

开发系统中选择**开始 =》 安装构件 =》 选择对应的构件库 =》 输入关键字搜索 =》 安装构件**。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image8.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image9.png)


##### 2.在自定义窗体中使用element-ui-lib资源构件

在自定义窗体中使用资源构件，保存部署预览即可。
自定义窗体的template页面代码：

```
<el-row>
    <el-button>默认按钮</el-button>
    <el-button type = "primary">主要按钮</el-button>
    <el-button type = "success">成功按钮</el-button>
    <el-button type = "info">信息按钮</el-button>
    <el-button type = "warning">警告按钮</el-button>
    <el-button type = "danger">危险按钮</el-button>
</el-row>
```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image48.png)


自定义窗体的script页面代码：

```
import vdk from 'v3-vdk';
import entities from './entities.js';
import 'element-ui-lib';
export default{
	props : entities,
    data : function(){
    	return {};
    },
    methods:{

    }
}

```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image49.png)


保存部署后预览页面：

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image10.png)


##### 3.二次开发控件中使用element-ui-lib构件资源

以开发element-ui-button控件为例，使用`npm install v3-cli --save-dev`创建二次开发控件模板。在二次开发控件的文件夹中，安装element-ui-lib资源构件，执行`npm run v3:install element-ui-lib`。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image37.png)


在element-ui-button控件的widget文件夹下的index.vue文件中，引入element-ui-lib资源构件。

```
<template>
	<el-button type = "primary">主要按钮</el-button>
</template>
<script>
import 'element-ui-lib';
export default{
	name : 'element-ui-button',
    props : {
    },
    data : function(){
    	return {};
    },
    methods:{
    }
}
</script>
<style scope lang = "less" src = "./theme.less"></style>
```

在二次开发控件中执行`npm run v3:test`，开启本地测试预览。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image39.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image11.png)



### (二)引入第三方工具方法（lodash）

#### Step1：创建lodash-lib构件资源

1.创建lodash-lib文件夹，在该文件夹下执行命令：`npm install v3-cli --save-dev`

2.安装完成后，会出现向导，按照需求填入相关信息。

**插件类型选择 `resource `**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image13.png)


3.在lodash-lib文件夹中安装lodash插件，执行:`npm install lodash --save`

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image15.png)


4.插件安装完成后，在`lodash-lib/index.js`中添加对lodash的使用。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image14.png)


```
import _ from 'lodash';
export default _;
```

#### Step2：部署到vstore仓库，执行`npm run v3:publish`

第一次部署到vstore仓库时，会要求输入vstore账号和密码。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image16.png)


部署到vstore仓库完成后，进入**开发系统控制台 => 构件管理 => 动力平台构件仓库 => 选择部署的vstore仓库**，可找到该资源构件。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image17.png)


#### Step3：使用资源构件
##### 自定义窗体中使用lodash-lib构件资源
##### A.执行系统处理

在执行系统中安装lodash-lib资源构件（>将来此步可以省略，目前正在处理）。控制台选择**构件管理 =》 构件动态安装（动态升级） =》 选择对应的库 =》 选择批量安装列表 =》 安装该资源构件**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image18.png)


##### B.开发系统处理

##### 1.在开发系统中安装lodash-lib资源构件

开发系统中选择**开始 =》 安装构件 =》 选择对应的构件库 =》 输入关键字搜索 =》 安装构件**。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image8.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image19.png)


##### 2.在自定义窗体中使用lodash-lib资源构件

在自定义窗体中使用资源构件，保存部署预览即可。
自定义窗体的template页面代码：

```
<el-row>
    <el-button type = "primary" @click = "onClick">测试lodash</el-button>
</el-row>
```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image40.png)


自定义窗体的script页面代码：

```
import vdk from 'v3-vdk';
import entities from './entities.js';
import 'element-ui-lib';
import lodash from 'lodash-lib';
export default{
	props : entities,
    data : function(){
    	return {};
    },
    methods:{
		onClick : function(){
        	alert(JSON.stringify(lodash.defaults({'a':1},{'a':3,'b':2})));
        }
    }
}

```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image41.png)


保存部署后预览页面：

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image20.png)


##### 3.二次开发控件中使用lodash-lib构件资源

以开发element-ui-button控件为例，使用`npm install v3-cli --save-dev`创建二次开发控件模板。在二次开发控件的文件夹中，安装lodash-lib资源构件，执行`npm run v3:install lodash-lib`。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image42.png)


在element-ui-button控件的widget文件夹下的index.vue文件中，引入element-ui-lib资源构件。

```
<template>
	<el-button type = "primary" @click = "onClick">测试lodash</el-button>
</template>
<script>
import 'element-ui-lib';
import lodash from 'lodash-lib';
export default{
	name : 'element-ui-button',
    props : {
    },
    data : function(){
    	return {};
    },
    methods:{
    	onClick : function(){
        	alert(JSON.stringify(lodash.defaults({'a':1},{'a':3,'b':2})));
        }
    }
}
</script>
<style scope lang = "less" src = "./theme.less"></style>
```

在二次开发控件中执行`npm run v3:test`，开启本地测试预览。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image43.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image21.png)


### (三)本地引入第三方js库(swiper)

#### Step1：创建swiper-lib构件资源

1.创建swiper-lib文件夹，在该文件夹下执行命令：`npm install v3-cli --save-dev`

2.安装完成后，会出现向导，按照需求填入相关信息。

**插件类型选择 `resource `**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image22.png)


3.前往[swiper官网](https://www.swiper.com.cn/)下载，目前使用swiper2作为例子，下载网址：https://www.swiper.com.cn/download/index.html#file1 ,得到两个资源文件：**swiper.min.css、swiper.min.js**，将资源文件拷贝到swiper-lib文件夹下lib文件夹中。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image23.png)


4.在**.v3devrc**中调整**extraSources**节点配置。

```
{
	"libType": "dev",
	"type": "resource",
	"pluginCode": "swiper-lib",
	"groupId": "com.toone.v3.platform",
	"matchVersion": 1,
	"symbolicName": "com.toone.v3.platform-vjs.framework.extension.platform.custom.resource.swiper-lib",
	"version": "1.0.0",
	"minMatchVersion": 1,
	"resourceCode": "vPlatform-resource-27516c460c57d85cf14c69edcb7326c4",
	"skin": {},
	"out": "target",
	"sources": "dist",
	"webpackCfgVersion": "1.0.4",
	"extraSources": [
		"lib/swiper.min.css",
		"lib/swiper.min.js"
	],
	"urlSources": [],
	"dependencies": [],
	"VjsList": [
		{
			"name": "vjs.framework.extension.platform.custom.resource.swiper-lib",
			"version": "1.0.0.SNAPSHOT"
		}
	],
	"depVjsList": [],
	"require": [],
	"account": "zhaoyf",
	"pwd": "zhaoyf"
}
```

*注意：如果文件有加载顺序要求，则extraSources中的文件按照顺序配置。*

#### Step2：部署到vstore仓库，执行`npm run v3:publish`

第一次部署到vstore仓库时，会要求输入vstore账号和密码。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image24.png)


部署到vstore仓库完成后，进入**开发系统控制台 => 构件管理 => 动力平台构件仓库 => 选择部署的vstore仓库**，可找到该资源构件。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image25.png)


#### Step3：使用资源构件

##### 自定义窗体中使用swiper-lib构件资源

##### A.执行系统处理

在执行系统中安装swiper-lib资源构件（将来此步可以省略，目前正在处理）。控制台选择**构件管理 =》 构件动态安装（动态升级） =》 选择对应的库 =》 选择批量安装列表 =》 安装该资源构件**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image26.png)


##### B.开发系统处理

##### 1.在开发系统中安装swiper-lib资源构件

开发系统中选择**开始 =》 安装构件 =》 选择对应的构件库 =》 输入关键字搜索 =》 安装构件**。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image8.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image27.png)


##### 2.在自定义窗体中使用swiper-lib资源构件,参考https://www.swiper.com.cn/usage/index.html

在自定义窗体中使用资源构件，保存部署预览即可。

自定义窗体的template页面代码：

```
<div class = "swiper-container">
	<div class = "swiper-wrapper">
    	<div class = "swiper-slide">slider 1</div>
        <div class = "swiper-slide">slider 2</div>
        <div class = "swiper-slide">slider 3</div>
    </div>
    <-- 如果需要分页器 -->
    <div class = "swiper-pagination"></div>
</div>
```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image44.png)


自定义窗体的script页面代码：

```
import vdk from 'v3-vdk';
import entities from './entities.js';
import swiper from 'swiper-lib';
export default{
	props : entities,
    data : function(){
    	return {};
    },
    methods:{
		initSwiper : function(){
        	new Swiper('.swiper-container',{
            	direction : 'vertical',
                loop : true,
                //如果需要分页器
                pagination : {
                	el : '.swiper-pagination'
                }
            })
        }
    },
    mounted : function(){
    	this.initSwiper();
    }
}

```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image45.png)


保存部署后预览页面：

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image28.png)



### (四)在线请求第三方js(map)

#### Step1：创建map-source构件资源

1.创建map-source文件夹，在该文件夹下执行命令：`npm install v3-cli --save-dev`

2.安装完成后，会出现向导，按照需求填入相关信息。

**插件类型选择> `resource`**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image29.png)


3.前往[百度地图官网](http://lbsyun.baidu.com/),先注册百度账号，登录API控制台，申请到密钥；使用百度地图API。得到百度地图API的js文件路径。在**.v3devrc**中调整**urlSources**节点配置。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image30.png)


```
{
	"libType": "dev",
	"type": "resource",
	"pluginCode": "map-source",
	"groupId": "com.toone.v3.platform",
	"matchVersion": 1,
	"symbolicName": "com.toone.v3.platform-vjs.framework.extension.platform.custom.resource.map-source",
	"version": "1.0.0",
	"minMatchVersion": 1,
	"resourceCode": "vPlatform-resource-27516c460c57d85cf14c69edcb7326eb",
	"skin": {},
	"out": "target",
	"sources": "dist",
	"webpackCfgVersion": "1.0.4",
	"extraSources": [],
	"urlSources": [
    	{
        	"url" : "http://api.map.baidu.com/api?v=2.0&ak=7EymnL4e9YpS22Ln4AWGbXGklCR7TEMl&callback=init",
            "type" : "js"
        }
    ],
	"dependencies": [],
	"VjsList": [
		{
			"name": "vjs.framework.extension.platform.custom.resource.map-source",
			"version": "1.0.0.SNAPSHOT"
		}
	],
	"depVjsList": [],
	"require": [],
	"account": "zhaoyf",
	"pwd": "zhaoyf"
}
```

#### Step2：部署到vstore仓库，执行`npm run v3:publish`

第一次部署到vstore仓库时，会要求输入vstore账号和密码。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image31.png)


部署到vstore仓库完成后，进入**开发系统控制台 => 构件管理 => 动力平台构件仓库 => 选择部署的vstore仓库 **，可找到该资源构件。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image32.png)


#### Step3：使用资源构件

##### 自定义窗体中使用map-source构件资源

##### A.执行系统处理

在执行系统中安装map-source资源构件（将来此步可以省略，目前正在处理）。控制台选择**构件管理 =》 构件动态安装（动态升级） =》 选择对应的库 =》 选择批量安装列表 =》 安装该资源构件**

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image33.png)


##### B.开发系统处理

##### 1.在开发系统中安装map-source资源构件

开发系统中选择**开始 =》 安装构件 =》 选择对应的构件库 =》 输入关键字搜索 =》 安装构件**。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image8.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image34.png)


##### 2.在自定义窗体中使用map-source资源构件

在自定义窗体中使用资源构件，保存部署预览即可。

自定义窗体的template页面代码：

```
<div>
	<div id = "allmap"></div>
</div>
```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image46.png)


自定义窗体的script页面代码：

```
import vdk from 'v3-vdk';
import entities from './entities.js';
import map from 'map-source';
export default{
	props : entities,
    data : function(){
    	return {};
    },
    methods:{
		initMap : function(){
        	var map = new BMap.Map("allmap"); //创建Map实例
            map.centerAndZoom(new BMap.Point(116.404,39.915),11); //初始化地图，设置中心点坐标
            //添加地图类型控件
            map.addControl(new BMap.MapTypeControl({
            	mapTypes : [
                	BMAP_NORMAL_MAP,
                    BMAP_HYBRID_MAP
                ]
            }));
            map.setCurrentCity("北京"); //设置地图显示的城市，此项是必须设置的
            map.enableScrollWheelZoom(true);  //开启鼠标滚轮缩放
        }
    },
    mounted : function(){
    	this.initMap();
    }
}

```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image47.png)


保存部署后预览页面：

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image35.png)



##### 3.二次开发控件中使用map-source构件资源

以开发vui-m-map控件为例，使用`npm install v3-cli --save-dev`创建二次开发控件模板。

在二次开发控件的文件夹中，安装map-source资源构件，执行`npm run v3:install map-source`.或者执行npm run v3:install XXXX.jar(本地路径，jar指资源构件工程target生成的jar包)，就可以进行百度地图相关的构件二次开发。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/resourceComponent/image36.png)


