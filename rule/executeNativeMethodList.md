# 执行开发系统方法

## 获取当前构件编码
`GetCurrentComponentCode`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|ComponentCode|构件编码|
|ComponentName|构件名称|
|ComponentCodeName|构件编码（构件名称）|
|ComponentType|构件类型|

## 获取当前方法文件路径
`GetCurrentMethodsFilePath`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|MethodsFilePath|方法文件路径|

## 获取当前方法编码
`GetCurrentMethodCode`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|MethodCode|方法编码|

## 获取当前规则实例编码
`GetCurrentRuleInstanceCode`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|RuleInstanceCode|规则实例编码|

## 获取当前窗体路径
`GetCurrentWindowPath`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|WindowPath|窗体路径|

## 获取当前窗体编码
`GetCurrentWindowCode`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|WindowCode|窗体编码|

## 获取构件集合
`GetComponents`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|

## 获取构件变量
`GetSystemVariables`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|

## 获取构件常量
`GetSystemConstants`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|

## 获取构件服务端方法集合
`GetComponentServerMethods`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InterfaceType|接口类型|
|ComponentCode|构件编码|

## 获取构件客户端方法集合
`GetComponentClientMethods`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InterfaceType|接口类型|
|ComponentCode|构件编码|

## 获取方法输入
`GetMethodInputs`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|InitValue|初始值|
|Desc|描述|
|EnumValue|枚举值|

## 获取方法输入实体字段
`GetMethodInputFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|Length|长度|
|Precision|精度|
|Description|描述|

## 获取方法输出
`GetMethodOutputs`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|InitValue|初始值|
|Desc|描述|

## 获取输出实体字段
`GetMethodOutputFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|Length|长度|
|Precision|精度|
|Description|描述|

## 获取方法变量
`GetMethodVariants`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|InitValue|初始值|
|Desc|描述|

## 获取方法变量实体字段
`GetMethodVariantFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|Length|长度|
|Precision|精度|
|Description|描述|

## 获取窗体集合
`GetWindows`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|DataType|数据类型|

## 获取窗体输入
`GetWindowInputs`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|

## 获取窗体输入实体字段
`GetWindowInputFields`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取窗体输出
`GetWindowOutputs`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|

## 获取窗体输出实体字段
`GetWindowOutputFields`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取控件
`GetControls`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|PCode|上级编码|
|MetaCode|元数据编码|
|IsValueMode|是否为值模式|

## 获取控件属性
`GetControlProperties`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
|controlCode|控件编码|
|controlMetaCode|控件元数据|
|controlPropertyGetType|属性获取类型(`IsAllowGetValue`,`IsAllowSetValue`,`IsAllowGetSetValue`)|
### 返回值
|编码|名称|
|----|----|
|ControlCode|控件编码|
|ControlMetaCode|控件元数据编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Category|控件属性分类|
|PropertyValueType|属性值类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|DataType|数据类型|
|Remark|备注|

## 获取控件-根据Code
`GetControlsByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|PCode|上级编码|
|MetaCode|元数据编码|
|IsValueMode|是否为值模式|

## 获取控件属性-根据Code
`GetControlPropertiesByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|controlCode|控件编码|
|controlMetaCode|控件元数据编码|
### 返回值
|编码|名称|
|----|----|
|ControlCode|控件编码|
|ControlMetaCode|控件元数据编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Category|控件属性分类|
|PropertyValueType|属性值类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|DataType|数据类型|
|Remark|备注|

## 获取实体
`GetEntities`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|

## 获取实体字段
`GetEntityFields`
### 参数
|编码|名称|
|----|----|
|windowPath|窗体路径|
|entityCode|实体编码|
### 返回值
|编码|名称|
|----|----|
|EntityCode|实体编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取表
`GetTables`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|

## 获取表字段
`GetTableFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|tableCode|表编码|
### 返回值
|编码|名称|
|----|----|
|TableCode|表编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取查询
`GetQueries`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|

## 获取查询字段
`GetQueryFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|queryCode|查询编码|
### 返回值
|编码|名称|
|----|----|
|QueryCode|查询编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取查询参数
`GetQueryParams`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|queryCode|查询编码|
### 返回值
|编码|名称|
|----|----|
|QueryCode|查询编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取引用构件
`GetRefComponents`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|ComponentFilePath|构件文件路径|

## 获取引用构件方法
`GetRefComponentMethods`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InterfaceType|接口类型|
|WindowCode|窗体编码|

## 获取引用构件方法输入
`GetRefComponentMethodInputs`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InitValue|初始值|
|Desc|描述|

## 获取引用构件方法输入实体字段
`GetRefComponentMethodInputFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|DataType|数据类型|
|Length|长度|
|Precision|精度|
|Description|描述|

## 获取引用构件方法输出
`GetRefComponentMethodOutputs`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InitValue|初始值|
|Desc|描述|

## 获取引用构件方法输出实体字段
`GetRefComponentMethodOutputFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|DataType|数据类型|
|Length|长度|
|Precision|精度|
|Description|描述|

## 获取引用构件窗体
`GetRefComponentWindows`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|ComponentCode|构件编码|
|FullPath|完整路径|

## 获取引用构件窗体输入
`GetRefComponentWindowInputs`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InitValue|初始值|

## 获取引用构件窗体输入实体字段
`GetRefComponentWindowInputFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InitValue|初始值|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取引用构件窗体输出
`GetRefComponentWindowOutputs`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InitValue|初始值|

## 获取引用构件窗体输出实体字段
`GetRefComponentWindowOutputFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|InitValue|初始值|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取引用构件窗体控件
`GetRefComponentWindowControls`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|PCode|上级编码|
|MetaCode|元数据编码|
|IsValueMode|是否为值模式|

## 获取引用构件窗体控件属性
`GetRefComponentWindowControlProperties`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|windowCode|窗体编码|
|controlCode|控件编码|
|controlMetaCode|控件元数据编码|
|controlPropertyGetType|属性获取类型(`IsAllowGetValue`,`IsAllowSetValue`,`IsAllowGetSetValue`)|
### 返回值
|编码|名称|
|----|----|
|ControlCode|控件编码|
|ControlMetaCode|控件元数据编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Category|控件属性分类|
|PropertyValueType|属性值类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|
|DataType|数据类型|
|Remark|备注|

## 获取引用构件表
`GetRefComponentTables`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
### 返回值
|编码|名称|
|----|----|
|ID|表标识|
|Code|编码|
|Name|名称|
|CodeName|编码名称|

## 获取引用构件表字段
`GetRefComponentTableFields`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|refComponentCode|引用构件编码|
|tableCode|表编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|Type|类型|
|DefaultValue|默认值|
|Length|长度|
|Precision|精度|
|IsMandratory|是否必填|
|Remark|备注|

## 获取窗体输入-根据Code
`GetWindowInputsByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|

## 获取窗体输入实体字段-根据Code
`GetWindowInputFieldsByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取窗体输出-根据Code
`GetWindowOutputsByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|

## 获取窗体输出实体字段-根据Code
`GetWindowOutputFieldsByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|paramCode|参数编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取窗体实体-根据Code
`GetEntitiesByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|

## 获取窗体实体字段-根据Code
`GetEntityFieldsByCode`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|entityCode|实体编码|
### 返回值
|编码|名称|
|----|----|
|EntityCode|实体编码|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|FullCode|完整的编码（带前缀）|
|FullCodeName|完整的编码和名称|

## 获取打印模板列表
`GetPrintviewTreeList`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Id|id|
|PID|上级id|
|Code|编码|
|Name|名称|
|Path|路径|
|IsLeaf|是否为叶子节点|

## 获取打印模板实体列表
`GetPrintviewEntityList`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|printviewCode|打印模板编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|

## 获取打印模板映射列表
`GetPrintviewMappingList`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|printviewCode|打印模板编码|
### 返回值
|编码|名称|
|----|----|
|EntityCode|实体编码|
|EntityFieldCode|实体字段编码|

## 获取表达式函数列表
`GetExpressionFunctions`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|Example|示例|
|Remark|备注|

## 获取表达式规则
`GetExpressionLogic`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|instanceCode|规则实例编码|
### 返回值
|编码|名称|
|----|----|
|ruleCode|规则编码（元数据编码）|
|ruleName|规则名称（元数据名称）|
|instanceCode|规则实例编码|
|instanceName|规则实例名称|
|instanceCodeName|规则实例编码名称|
|isNeedLog|是否需要日志|
|isEnabled|是否可用|
|isDebug|是否调试|

## 获取表达式规则返回值列表
`GetExpressionReturnValueOfLogic`
### 参数
|编码|名称|
|----|----|
|ruleCode|规则编码|
### 返回值
|编码|名称|
|----|----|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|
|Remark|备注|
|RuleCode|规则编码|

## 获取表达式Foreach列表实体
`GetExpressionForeachEntity`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|instanceCode|规则实例编码|
### 返回值
|编码|名称|
|----|----|
|LoopVariant|循环变量|
|EntityType|实体类型|
|IterationEntity|迭代实体|

## 获取表达式Foreach列表循环变量
`GetExpressionForeachVariable`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|windowCode|窗体编码|
|methodCode|方法编码|
|instanceCode|规则实例编码|
|loopEntity|循环变量|
### 返回值
|编码|名称|
|----|----|
|LoopVariant|循环变量|
|EntityType|实体类型|
|IterationEntity|迭代实体|
|Code|编码|
|Name|名称|
|CodeName|编码名称|
|DataType|数据类型|

## 获取WebService的方法列表
`GetWebServiceMethod`
### 参数
|编码|名称|
|----|----|
|webServiceUrl|webServiceUrl地址|
### 返回值
|编码|名称|
|----|----|
|MethodCode|方法编码|

## 获取WebService方法的输入/输出列表
`GetWebServiceMethodInputOutput`
### 参数
|编码|名称|
|----|----|
|webServiceUrl|webServiceUrl地址|
|methodCode|方法编码|
### 返回值
|编码|名称|
|----|----|
|ParamCode|参数编码|
|ParamType|参数类型|
|Flag|标识，方法输入或输出|

## 获取功能构件页面数据
`GetWindowDesignPageData`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|installedComponentCode|已安装的构件编码|
|windowCode|窗体编码|
### 返回值
|编码|名称|
|----|----|
|ViewData|页面数据|
|DeployData|部署数据|

## 调用表达式
`DevExcuteExpression`
### 参数
|编码|名称|
|----|----|
|dataStructureJson|实体结构|
|associationStructureJson|实体字段结构|
|expressResult|表达式返回结果|
|dataType|数据类型|
|ruleSetInputAlias|方法输入别名|
|ruleSetOutputAlias|方法输出别名|
|ruleSetVarAlias|方法变量别名|
### 返回值
|编码|名称|
|----|----|
|result|返回结果|
|dialogResult|对话框操作结果(`confirm`或`cancel`)|

## 调用规则链
`CallRuleChain`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|viewData|页面数据|
|dataStructureJson|实体结构|
|associationStructureJson|实体字段结构|
|showRuleList|是否显示规则链|
|showRuleSetInput|是否显示方法输入|
|showRuleSetOutput|是否显示方法输出|
|showRuleSetVar|是否显示方法变量|
|ruleSetInputAlias|方法输入别名|
|ruleSetOutputAlias|方法输出别名|
|ruleSetVarAlias|方法输出变量|
|isMethodExpandImp|是否方法实现|
### 返回值
|编码|名称|
|----|----|
|viewData|页面数据|
|deployData|部署数据|
|dialogResult|对话框操作结果(`confirm`或`cancel`)|

## 获取当前登录人信息
`GetCurrentLoginUser`
### 参数
无
### 返回值
|编码|名称|
|----|----|
|LoginUserName|用户登录账号|
|UserName|用户账号|
|UserAlias|登录用户别名|

## 系统全局变量赋值
`EvaluateSystemVariable`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|key|变量编码|
|value|变量名称|
### 返回值
|编码|名称|
|----|----|
|result|操作结果|
|EvaluateState|状态(`Add`或`Update`)|

## 系统全局变量取值
`GetSystemVariable`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|key|关键字|
### 返回值
|编码|名称|
|----|----|
|result|结果(`Fail`或`Success`)|
|value|变量值|

## 获取构件资源目录
`GetResourceFolders`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
### 返回值
|编码|名称|
|----|----|
|id|id|
|pid|上级id|
|folderName|目录名称|
|path|路径|

## 获取构件资源
`GetResourceFiles`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|path|路径|
|isRecurse|是否递归|
|filter|过滤条件|
### 返回值
|编码|名称|
|----|----|
|code|编码|
|name|名称|
|extension|文件后缀|
|size|文件大小|
|dimension|尺寸|
|updator|上传用户|
|updateTime|上传时间|
|desc|描述|
|fullPath|完整路径|

## 通过构件编码和文件编码列表获取资源文件列表
`GetResourceFilesByCodes`
### 参数
|编码|名称|
|----|----|
|componentCode|构件编码|
|fileCodes|编码列表|
### 返回值
|编码|名称|
|----|----|
|code|编码|
|name|名称|
|extension|文件后缀|
|size|文件大小|
|dimension|尺寸|
|updator|上传用户|
|updateTime|上传时间|
|desc|描述|
|fullPath|完整路径|

