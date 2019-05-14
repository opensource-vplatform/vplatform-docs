
# 全终端变量

> 全终端变量会影响到所有窗体，全终端变量的前缀是 `v-`

### 基础色

变量名 | 语义 | 图例
---|---|---
@v-primary-color    | 主色，系统主品牌色                     | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-primary-color.png) #356bbc
@v-info-color       | 信息，                                | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-info-color.png) #356bbc
@v-success-color    | 成功，常用于正向操作，如成功、新增       | ![#19be6b](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-success-color.png) #19be6b
@v-warning-color    | 警告，常用于提醒、警告                  | ![#ff9900](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-warning-color.png) #ff9900
@v-error-color      | 错误 ，常用于负方操作，如失败、出错      | ![#ed3f14](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-error-color.png) #ed3f14



### 文字排版

变量名 | 语义 | 图例
---|---|---
@v-text-title-color         | 文本标题色，常用于信息标题，栏目标题等          | ![#2e3740](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-text-title-color.png) #2e3740
@v-text-base-color          | 基础文本色，项目大面积展示的文本色              | ![#556373](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-text-base-color.png) #556373
@v-text-secondary-color     | 二级文本色，常用于辅助文本信息                 | ![#919191](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-text-base-color.png) #919191
@v-link-color               | 超链接文字色 - 默认                           | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-link-color.png) #356bbc
@v-link-hover-color         | 超链接文字色 - 鼠标悬停                       | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-link-hover-color.png) tint(@v-link-color, 20%)
@v-link-active-color        | 超链接文字色 - 鼠标按下                       | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-link-active-color.png) shade(@v-link-color, 5%)
@v-link-text-decoration     | 链接文本默认下划线                            | none



### 边框

变量名 | 语义 | 图例
---|---|---
@v-border-base-color         | 控件外围边框色                            | ![#dadde0](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-base-color.png) #dadde0
@v-border-split-color        | 控件内部分割线                            | ![#e1e4e8](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-split-color.png) #e1e4e8
@v-border-radius-base        | 系统默认圆角半径                          | ![4px圆角](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-radius-base.png) 4px
@v-border-radius-small       | 较小的圆角半径，常用于较小的按钮等          | ![2px圆角](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-radius-small.png) 2px



### 背景

变量名 | 语义 | 图例
---|---|---
@v-background-base-color         | 基础灰色：                            | ![#f5f7fa](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-background-base-color.png) #f5f7fa
@v-background-stripe-color       | 表格斑马线颜色                        | ![#f5f7fa](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-background-stripe-color.png) #f5f7fa
@v-background-active-color       | table默认鼠标经过行，选中行背景色      | ![#dadde0](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-background-active-color.png) tint(@v-primary-color, 92%)



### 禁用

变量名 | 语义 | 图例
---|---|---
@v-disabled-color   | 禁用文本色，如连接禁用，按钮禁用时的文本色      | ![#b1b5ba](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-disabled-color.png) #b1b5ba
@v-disabled-bg      | 禁用背景色。如按钮的禁用背景色，表单禁用        | ![#f5f7fa](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-disabled-bg.png) @v-background-base-color


### 阴影
> 投影是UI界面设计很重要的一个元素，它能助于我们大脑区分我们看见的UI元素，让用户对于信息的理解更加简单，提高界面品质感

变量名 | 语义 | 图例
---|---|---
@v-shadow-color           | 投影默认颜色                     | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-color.png) rgba(0, 0, 0, .2)
@v-shadow-base            | 默认投影：即阴影-下               | ![base](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-down.png) @v-shadow-down
@v-shadow-up              | 阴影-上                          | ![up](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-up.png) 0 -1px 6px @v-shadow-color
@v-shadow-down            | 阴影-下                          | ![down](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-down.png) 0 1px 6px @v-shadow-color
@v-shadow-left            | 阴影-左                          | ![left](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-left.png) -1px 0 6px @v-shadow-color
@v-shadow-right           | 阴影-右                          | ![right](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-right.png) 1px 0 6px @v-shadow-color


### 动画缓动曲线
> 缓动曲线是动效执行时的速度曲线，是的动效看起来更加的真实，符合自然规律。
[缓动函数动画示意demo](http://www.xuanfengge.com/easeing/easeing/#)

变量名 | 语义 | 图例
---|---|---
@v-ease-out            | 减速到0的缓动（衰减）                               | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out.png) cubic-bezier(0.215, 0.61, 0.355, 1)
@v-ease-in             | 从0开始加速的缓动（加速）                           | ![easeIn](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in.png) cubic-bezier(0.55, 0.055, 0.675, 0.19)
@v-ease-in-out         | 前半段从0开始加速，后半段减速到0的缓动（先加速后减速） | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out.png) cubic-bezier(0.645, 0.045, 0.355, 1)
@v-ease-out-back       | 先超出返回再减速到0（衰减）                         | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out-back.png) cubic-bezier(0.12, 0.4, 0.29, 1.46)
@v-ease-in-back        | 先加速超出终点回弹减速到终点（加速）                 | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-back.png) cubic-bezier(0.71, -0.46, 0.88, 0.6)
@v-ease-in-out-back    | 先超出返回再回弹（先加速后减速）                    | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out-back.png) cubic-bezier(0.71, -0.46, 0.29, 1.46)
@v-ease-out-circ       | 圆形曲线的缓动（衰减）                             | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out-circ.png) cubic-bezier(0.08, 0.82, 0.17, 1)
@v-ease-in-circ        | 圆形曲线的缓动（加速）                             | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-circ.png) cubic-bezier(0.6, 0.04, 0.98, 0.34)
@v-ease-in-out-circ    | 圆形曲线的缓动（先加速后减速）                      | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out-circ.png) cubic-bezier(0.78, 0.14, 0.15, 0.86)
@v-ease-out-quint      | 速度先（衰减）                                     | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out-quint.png) cubic-bezier(0.23, 1, 0.32, 1)
@v-ease-in-quint       | 五次方的缓动（加速）                               | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-quint.png) cubic-bezier(0.755, 0.05, 0.855, 0.06)
@v-ease-in-out-quint   | 五次方的缓动（先加速后减速）                        | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out-quint.png) cubic-bezier(0.86, 0, 0.07, 1)




<br/>
<br/>
<br/>

# 网页窗体变量

网页窗体变量与全终端窗体变量命名基本一致，没有了前面的`v-`前缀。


### 基础色

变量名 | 语义 | 图例
---|---|---
@primary-color    | 主色，系统主品牌色                     | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-primary-color.png) @v-primary-color
@info-color       | 信息，                                | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-info-color.png) @v-info-color
@success-color    | 成功，常用于正向操作，如成功、新增       | ![#19be6b](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-success-color.png) @v-success-color
@warning-color    | 警告，常用于提醒、警告                  | ![#ff9900](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-warning-color.png) @v-warning-color
@error-color      | 错误 ，常用于负向操作，如失败、出错      | ![#ed3f14](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-error-color.png) @v-error-color



### 文字排版

变量名 | 语义 | 图例
---|---|---
@text-title-color         | 文本标题色，常用于信息标题，栏目标题等       | ![#2e3740](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-text-title-color.png) @v-text-title-color
@text-base-color          | 基础文本色，项目大面积展示的文本色           | ![#556373](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-text-base-color.png) @v-text-base-color
@text-secondary-color     | 二级文本色，常用于辅助文本信息              | ![#919191](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-text-base-color.png) @v-text-secondary-color
@font-size-large	      | 较大文字                                  | 14px  
@font-size-base	          | 系统默认文字                              | 12px 
@link-color               | 超链接文字色 - 默认                        | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-link-color.png) @v-link-color
@link-hover-color         | 超链接文字色 - 鼠标悬停                    | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-link-hover-color.png) @v-link-hover-color
@link-active-color        | 超链接文字色 - 鼠标按下                    | ![#356bbc](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-link-active-color.png)  @v-link-active-color
@link-text-decoration     | 链接文本下划线                            | @v-link-text-decoration



### 边框

变量名 | 语义 | 图例
---|---|---
@border-base-color         | 控件外围边框色                            | ![#dadde0](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-base-color.png) @v-border-base-color
@border-split-color        | 控件内部分割线                            | ![#e1e4e8](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-split-color.png) @v-border-split-color
@border-radius-base        | 系统默认圆角半径                          | ![4px圆角](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-radius-base.png)  @v-border-radius-base
@border-radius-small       | 较小的圆角半径，常用于较小的按钮等          | ![2px圆角](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-border-radius-small.png) @v-border-radius-small




### 背景

变量名 | 语义 | 图例
---|---|---
@background-base-color         | 基础灰色：                            | ![#f5f7fa](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-background-base-color.png) @v-background-base-color
@background-stripe-color       | 表格斑马线颜色                        | ![#f5f7fa](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-background-stripe-color.png) @v-background-stripe-color
@background-active-color       | table默认鼠标经过行，选中行背景色      | ![#dadde0](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-background-active-color.png) @v-background-active-color



### 禁用

变量名 | 语义 | 图例
---|---|---
@disabled-color   | 禁用文本色，如连接禁用，按钮禁用时的文本色      | ![#b1b5ba](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-disabled-color.png) @v-disabled-color
@disabled-bg      | 禁用背景色。如按钮的禁用背景色，表单禁用        | ![#f5f7fa](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-disabled-bg.png) @v-disabled-bg



### 阴影
> 投影是UI界面设计很重要的一个元素，它能助于我们大脑区分我们看见的UI元素，让用户对于信息的理解更加简单，提高界面品质感

变量名 | 语义 | 图例
---|---|---
@shadow-color           | 投影默认颜色                     | ![#000](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-color.png) @v-shadow-color
@shadow-base            | 默认投影：即阴影-下               | ![base](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-down.png) @v-shadow-base
@shadow-up              | 阴影-上                          | ![up](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-up.png) @v-shadow-up
@shadow-down            | 阴影-下                          | ![down](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-down.png) @v-shadow-down
@shadow-left            | 阴影-左                          | ![left](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-left.png)  @v-shadow-left
@shadow-right           | 阴影-右                          | ![right](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-shadow-right.png) @v-shadow-right



### 动画缓动曲线
> 缓动曲线是动效执行时的速度曲线，是的动效看起来更加的真实，符合自然规律。
[缓动函数动画示意demo](http://www.xuanfengge.com/easeing/easeing/#)

变量名 | 语义 | 图例
---|---|---
@ease-out            | 减速到0的缓动（衰减）                               | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out.png) @v-ease-out
@ease-in             | 从0开始加速的缓动（加速）                           | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in.png) @v-ease-in
@ease-in-out         | 前半段从0开始加速，后半段减速到0的缓动（先加速后减速） | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out.png) @v-ease-in-out
@ease-out-back       | 先超出返回再减速到0（衰减）                         | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out-back.png) @v-ease-out-back
@ease-in-back        | 先加速超出终点回弹减速到终点（加速）                 | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-back.png) @v-ease-in-back
@ease-in-out-back    | 先超出返回再回弹（先加速后减速）                    | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out-back.png)  @v-ease-in-out-back
@ease-out-circ       | 圆形曲线的缓动（衰减）                             | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out-circ.png) @v-ease-out-circ
@ease-in-circ        | 圆形曲线的缓动（加速）                             | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-circ.png) @v-ease-in-circ
@ease-in-out-circ    | 圆形曲线的缓动（先加速后减速）                      | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out-circ.png) @v-ease-in-out-circ
@ease-out-quint      | 速度先（衰减）                                    | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-out-quint.png) @v-ease-out-quint
@ease-in-quint       | 五次方的缓动（加速）                               | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-quint.png) @v-ease-in-quint
@ease-in-out-quint   | 五次方的缓动（先加速后减速）                        | ![easeOut](https://github.com/opensource-vplatform/vplatform-docs/blob/master/mdImages/skinVariable/v-ease-in-out-quint.png) @v-ease-in-out-quint


```