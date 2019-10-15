# schema 
## schema 样例

```json
[{
	"name": "Los",
    "component": "vc-textbox",
    "model": "Los",
    "type": "text",
    "label": "Los"
}]
```



## schema 的基础属性
### name  

- **必须属性**
- 类型： String

初始化必须具有的属性，对应控件名字



### component
- **必须属性**
- 类型： String

初始化必须具有的属性，对应控件

### model

- 可选属性
- 类型： String

读取数据时需要的属性，对应数据中的字段名。对于某些控件，如cardlist , 该属性由另一个属性取代



### queryid

- 可选属性
- 类型： String

读取数据时需要的属性，对应一个数据接口的关键字。



### schemas

- 可选属性
- 类型： Array

如果schema 中存在嵌套结构，则子集以schema 形式存在于这个字段中。



## schema 基于控件的扩展属性
### required

- 可选属性
- 类型： Boolean

输入型控件，可以配置是否必填

### classes

- 可选属性
- 类型： String

像layout 这样的控件，是支持可以自定义class 的，可以由这个属性传入

### layout

- 可选属性
- 类型： String

像layout 这样的控件，能够支持控件横向布局和纵向布局

### 

