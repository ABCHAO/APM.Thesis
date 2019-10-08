# APM.Vue 简介

APM.Vue是一个基于Vue和Json Schema搭建的一站式网站生成平台。

## 什么是 Json ?

json 是 JavaScript Object Notation 的缩写，它是一种简化的数据交换格式，是目前互联网服务间进行数据交换最常见的一种交换格式，具有简洁、可读性好等特点。

在json中常见的数据类型主要包括:
- **object** 
```json
{ "key1": "value1", "key2": "value2" }
```
- **array** 
```json
[ "first", "second", "third" ]
```
- **number** 
```json
42
3.1415926
```
- **string** 
```json
"This is a string"
```
- **boolean** 
```json
true
false
```
- **null** 
```json
null
```

一个示例json格式比如:
```json
{
 "fruits": [ "apple", "orange", "pear" ],
 "vegetables": [
   {
     "veggieName": "potato",
     "veggieLike": true
   },
   {
     "veggieName": "broccoli",
     "veggieLike": false
   }
 ]
}
```

## 什么是 Json Schema ?

如前文所述，json是目前应用非常广泛的数据交换格式。既然是用于数据交换的格式，那么就存在数据交换的双方。如何约定或校验对方的数据格式是符合要求的，就成了服务交互需要解决的一个问题。所以Json Schema就是用来定义json数据约束的一个标准。根据这个约定模式，交换数据的双方可以理解json数据的要求和约束，也可以据此对数据进行验证，保证数据交换的正确性。

目前最新的Json-schema版本是draft 7，发布于2018-03-19。下面我们就以官网的一个实例来看看Json-schema是如何进行数据约束以及其应用
如下是一个schema实例：
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/product.schema.json",
  "title": "Product",
  "description": "A product from Acme's catalog",
  "type": "object",
  "properties": {
    "productId": {
      "description": "The unique identifier for a product",
      "type": "integer"
    },
    "productName": {
      "description": "Name of the product",
      "type": "string"
    },
    "price": {
      "description": "The price of the product",
      "type": "number",
      "exclusiveMinimum": 0
    },
    "tags": {
      "description": "Tags for the product",
      "type": "array",
      "items": {
        "type": "string"
      },
      "minItems": 1,
      "uniqueItems": true
    },
    "dimensions": {
      "type": "object",
      "properties": {
        "length": {
          "type": "number"
        },
        "width": {
          "type": "number"
        },
        "height": {
          "type": "number"
        }
      },
      "required": [ "length", "width", "height" ]
    }
  },
  "required": [ "productId", "productName", "price" ]
}
```
分析说明：

- **当前使用的schema版本，可以不包含** 
```json
"$schema": "http://json-schema.org/draft-07/schema#",
```
- **当前schema的唯一id标识，一般指向一个自主域名。方便后续引用，可以不包含** 
```json
"$id": "http://example.com/product.schema.json",
```
- **当前schema的标题，简要描述信息，可不包含** 
```json
"title": "Product",
```
- **详细描述信息，可不包含** 
```json
"description": "A product from Acme's catalog",
```
- **约束对象是object，也就是在 { } 中的数据** 
```json
"type": "object",
```
- **object中具体属性的约束，description是描述信息，不产生具体约束。type约束productid属性类型为整型** 
```json
"properties": {
    "productId": {
      "description": "The unique identifier for a product",
      "type": "integer"
    },
```
- **约束productName属性类型为字符型** 
```json
"productName": {
      "description": "Name of the product",
      "type": "string"
    }
```
- **约束price属性类型为数字型，可以是整型或浮点型。exclusiveMinimum约束该数字>0（不包含0）** 
```json
"price": {
      "description": "The price of the product",
      "type": "number",
      "exclusiveMinimum": 0
    },
```
- **约束tag属性是array数组。items是数组项约束，这里约束数组项均为字符型。minItems数组至少包含1项。uniqueItems约束数组中每项不得重复** 
```json
"tags": {
      "description": "Tags for the product",
      "type": "array",
      "items": {
        "type": "string"
      },
      "minItems": 1,
      "uniqueItems": true
    },
```
- **约束`dimensions`嵌套对象，其中length，width，height均为数字类型，且这三个字段在dimensions对象中必须包含** 
```json
"dimensions": {
      "type": "object",
      "properties": {
        "length": {
          "type": "number"
        },
        "width": {
          "type": "number"
        },
        "height": {
          "type": "number"
        }
      },
  "required": [ "length", "width", "height" ]
    }
  },
```
- **当前数据对象必须包含productId，productName，price三个字段** 
```json
 "required": [ "productId", "productName", "price" ]
}
```
以上是对Json-Schema的简要说明。

## View 定义

## 多语言定义

## 控件

### vc-layout


