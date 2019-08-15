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
## schema 的高级属性
### script