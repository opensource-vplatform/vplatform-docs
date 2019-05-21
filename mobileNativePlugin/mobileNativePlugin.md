# 移动端原生插件使用

## 一、使用背景

* 平台提供现有插件无法满足项目需求

* 灵活引用第三方现成插件

* 根据需求定制开发插件


## 二、打包APP应用

### 1、打开移动应用打包界面

登录服务控制台，点击“移动端管理->移动应用打包”，进行APP初始设置和打包。

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584204964294.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584205748338.png)



（1）控制台地址的一般格式：服务地址:`端口号/system/console`

（2）如果一体化环境，使用登录V开发平台的账号和密码登录

（3）如果服务器版，使用登录服务器的账号和密码登录

### 2、查看APP应用列表

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584225947644.png)

*  **APP名称**：插件测试 

*  **应用ID**：cn.com.vapp.toone.chenftest 

*  **创建时间**：2019-04-26 13:57:54 

*  **添加版本**：创建新版本

*  **最新版本**：当前最高版本1.0.9

*  **历史版本**：查看所有历史版本

*  **下载**：下载安装APP

### 3、创建一个新的APP应用

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/1556247507249.png)

*  **应用ID的格式要求**：公司小写英文+"."+自定义小写英文，例如：baidu.abc (创建之后不得修改)

*  **布局类型**：竖屏、横屏

*  **支持兼容设备**：手机、平板和手机平板

*  **打包模式**：

 &emsp;&emsp;①生产模式（一般用于正式环境）   
&emsp;&emsp;②开发模式（一般用于测试环境）

### 4、资源配置

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/1558422759614.png)

*  **服务器地址**（可检测连接）

*  **应用首页配置：**

 &emsp;&emsp;①首页对应构件   
 &emsp;&emsp;②首页对应窗体

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584227928402.png)


*  **广告图片配置**

* APP启动顺序依次为：
&emsp;&emsp;启动图片 
&emsp;&emsp;广告图片 
&emsp;&emsp;首页窗体

### 5、添加版本

*  **应用配置**

&emsp;&emsp;①应用图标
&emsp;&emsp;②启动图片
&emsp;&emsp;③版本号（默认+1）

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584215275584.png)

*  **平台提供插件**

&emsp;&emsp;①百度鹰眼轨迹服务

&emsp;&emsp;②友盟分享（支持微信、QQ、新浪微博）

&emsp;&emsp;③TalkingData第三方移动数据服务平台  

&emsp;&emsp;④Ping++支付（支持微信、支付宝）

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584215826214.png)

## 三、添加自定义插件

### 1、上传自定义插件

如果所示，点击"+"
选择已经准备好的自定义插件zip包

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584216193728.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584217128960.png)

插件上传流程：

上传—》 校验—》 安装  —》 编译

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584217569095.png)


![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584219517943.png)

### 2、插件相关属性

点击插件【编辑】按钮，可以查看该插件相对应的属性配置

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/1558421989551.png)

### 3、插件适用终端

插件上传之后会显示该插件适用的终端平台，苹果/安卓

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584220284050.png)

如果插件校验失败，可以点击按钮查看具体日志

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584241865016.png)



### 4、开启插件

点击插件【开启】按钮，开启插件适用

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584220905249.png)

部分插件开启需要配置指定参数

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584221233260.png)


## 四、打包APP

如图所示，点击"开始打包"

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584221574569.png)

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584222021457.png)

具体的平台APP打包操作步骤详解可以参考  [V平台移动APP简介](http://www.toone.com.cn:9999/document/yidongkaifa/APP-001%E7%A7%BB%E5%8A%A8%E5%BA%94%E7%94%A8%E7%AE%80%E4%BB%8B.pdf)


## 五、调用插件实例

本文档以调用移动端日历为例子，演示移动端如何使用自定义插件

### Step1

上传一个已经准备好的日历插件Calendar-PhoneGap-Plugin-master.zip，上传成功后点击【开启】按钮启用该插件

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/1556414916264.png)

### step2

配置APP页面内容

页面放置两个button

button1--打开移动端原生日历

button2--添加一个自定义日历行程

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584222797696.png)


### step3

开发一个前端函数，用于调用该日历插件接口。通过按钮绑定点击事件，触发调用该函数。 

函数名【moblieCalendar】

插件打包成功之后会注册为window全局，调用之前可先判断window是否已经注册成功

```
//判断插件是否已注册
if(window.plugins.calendar){
   var startDate = new Date(2018,3,15,18,30,0,0,0); // beware: month 0 = january, 11 = december
      var endDate = new Date(2018,3,18,19,30,0,0,0);
      var title = "V3平台技术分享";
      var eventLocation = "公司";
      var notes = "分享V3平台最新技术，分享最前沿研发方案！";
      var success = function(message) { alert("Success: " + JSON.stringify(message)); };
      var error = function(message) { alert("Error: " + message); };

      // create an event silently (on Android < 4 an interactive dialog is shown which doesn't use this options) with options:
      var calOptions = window.plugins.calendar.getCalendarOptions(); // grab the defaults
      calOptions.firstReminderMinutes = 120; // default is 60, pass in null for no reminder (alarm)
      calOptions.secondReminderMinutes = 5;

      // Added these options in version 4.2.4:
      calOptions.recurrence = "monthly"; // supported are: daily, weekly, monthly, yearly
      calOptions.recurrenceEndDate = new Date(2016,10,1,0,0,0,0,0); // leave null to add events into infinity and beyond
      calOptions.calendarName = "Birthdays"; // iOS only
      calOptions.calendarId = 1; // Android only, use id obtained from listCalendars() call which is described below. This will be ignored on iOS in favor of calendarName and vice versa. Default: 1.

      // This is new since 4.2.7:
      calOptions.recurrenceInterval = 2; // once every 2 months in this case, default: 1

      // And the URL can be passed since 4.3.2 (will be appended to the notes on Android as there doesn't seem to be a sep field)
      calOptions.url = "https://www.google.com";

     
      if(value=="createEvent"){
   	 //调用原生端行程设置行程
 	    	  window.plugins.calendar.createEventInteractivelyWithOptions(title,eventLocation,notes,startDate,endDate,calOptions,success,error);
      }else{
   	 //调用原生端日历
	   	  window.plugins.calendar.openCalendar();
      }
}else{
	return;
}
```

### step4

两个按钮绑定对应的事件，
通过【执行函数/表达式】规则调用函数

```
moblieCalendar("createEvent")
moblieCalendar( )
```

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584223468318.png)

### step5

演示效果

![Alt text](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/mobileNativePlugin/15584234325413.png)



## 五、总结

开发者可以根据需求自定义开发插件，开发规范遵循当前业界通用的Cordova开发规范，可以通过学习【Cordova插件开发】快速入门

IOS平台
http://open.yindangu.com/package/itop/mobile/plugindev/markdown/iOS/html/README.html

Android平台
http://open.yindangu.com/package/itop/mobile/plugindev/markdown/android/README.html