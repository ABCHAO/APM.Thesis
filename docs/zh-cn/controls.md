# 系统组件
系统提供了基础的组件库
## vuetify

## AppMaker预定义组件

### 组件必备属性



### 组件共有属性列表

| 属性名    | 说明         | 是否必须 |      |      |      |
| --------- | ------------ | -------- | ---- | ---- | ---- |
| name      | 控件名字     | 是       |      |      |      |
| component | 控件类型标识 | 是       |      |      |      |
| model     | 控件数据     | 否       |      |      |      |
| label     |              | 否       |      |      |      |
| classes   |              | 否       |      |      |      |
| style     |              | 否       |      |      |      |



### 各组件详细说明

#### vc-layout

| 属性名  | 子属性名 | 必备  |  类型  | 默认值 | 是否支持脚本 | 样例 |
| :-----: | :------: | :---: | :----: | :----: | :----------: | :--: |
|  name   |          | true  | string |        |              |      |
| classes |          | false | string |        |              |      |
|  style  |          | false | object |  col   |              |      |
| layout  |          | false | string |        |              |      |

#### vc-alert

| 属性名  | 子属性名 | 必备  | 类型   | 默认值  | 是否支持脚本 | 样例 |
| ------- | -------- | ----- | ------ | :-----: | ------------ | ---- |
| name    |          | true  | string |         |              |      |
| type    |          | false | string | success |              |      |
| message |          | false | string |   " "   |              |      |
| show    |          | false | bool   |  false  |              |      |



#### vc-backtop

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 | 备注  80%                  |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- | -------------------------- |
| name   |          | true | string |        |              |      | 需要修改成公共的schema格式 |
|        |          |      |        |        |              |      |                            |
|        |          |      |        |        |              |      |                            |
|        |          |      |        |        |              |      |                            |

#### vc-breadcrumbs

| 属性名 | 子属性名 | 必备 | 类型         | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------------ | ------ | ------------ | ---- |
| name   |          | true | string       |        |              |      |
| items  |          | true | object array |        |              |      |
|        |          |      |              |        |              |      |
|        |          |      |              |        |              |      |

#### vc-button-group

| 属性名  | 子属性名 | 必备  | 类型        | 默认值 | 是否支持脚本 | 样例 |
| ------- | -------- | ----- | ----------- | ------ | ------------ | ---- |
| name    |          | true  | string      |        |              |      |
| classes |          | false | string      |        |              |      |
| schemas |          | false | json schema |        |              |      |
| model   |          | false |             |        |              |      |
| options |          | false |             |        |              |      |

#### 

#### vc-button

| 属性名              | 子属性名 | 必备  | 类型    | 默认值 | 是否支持脚本 | 样例 | 备注                    |
| ------------------- | -------- | ----- | ------- | ------ | ------------ | ---- | ----------------------- |
| name                |          | true  | string  |        |              |      |                         |
| color               |          | false | string  |        |              |      |                         |
| onclick             |          | true  | string  |        |              |      |                         |
| enableTransaction   |          |       |         |        |              |      | 是否支持c#代码          |
| transaction         |          |       |         |        |              |      | c#代码内容              |
| transactionCallback |          |       |         |        |              |      | 执行完c#之后回调        |
| disabled            |          | false | boolean | false  |              |      |                         |
| loading             |          | false | boolean | false  |              |      |                         |
| classes             |          | false | string  |        |              |      |                         |
| iconposition        |          | false | string  | left   |              |      |                         |
| type                |          | false | string  | button |              |      | type=submit时，留做提交 |
| style               |          | false | string  |        |              |      |                         |
| href                |          | false | string  |        |              |      |                         |
| to                  |          | false | string  |        |              |      |                         |
| target              |          | false | string  | _blank |              |      |                         |
| icon                |          | false | string  |        |              |      |                         |
| label               |          | false |         |        |              |      |                         |
| loadingtext         |          | false | string  |        |              |      |                         |
|                     |          |       |         |        |              |      |                         |

#### 

#### vc-card-list

| 属性名  | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name    |          | true  | string |        |              |      |
| classes |          | false | string |        |              |      |
|         |          |       |        |        |              |      |
|         |          |       |        |        |              |      |

#### vc-card

| 属性名   | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 说明 |
| -------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name     |          | true  | string |        |              |      |
| classes  |          | false | string |        |              |      |
| template |          | false | string |        |              |      |
| image    |          | false | string |        |              |      |
| static   |          | true  | bool   |        |              |      |
| title    |          | false | string |        |              |      |
| content  |          | false | string |        |              |      |
| href     |          | false | string |        |              |      |

#### vc-chart

| 属性名    | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 说明         |
| --------- | -------- | ----- | ------ | ------ | ------------ | ------------ |
| name      |          | true  | string |        |              |              |
| chartType |          | true  | string |        |              | 图标类型     |
| data      |          | false | json   |        |              |              |
| colors    |          | false | array  |        |              | 设置颜色主题 |

#### 

#### vc-checkbox

| 属性名   | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| -------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name     |          | true  | string |        |              |      |
| classes  |          | false | string |        |              |      |
| label    |          | false | string |        |              |      |
| rules    |          | false | string |        |              |      |
| color    |          | false | string |        |              |      |
| disabled |          | false | bool   |        |              |      |
| required |          | false | bool   |        |              |      |

#### 

#### vc-comment

| 属性名   | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| -------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name     |          | true  | string |        |              |      |
| required |          | false | string |        |              |      |
|          |          |       |        |        |              |      |
|          |          |       |        |        |              |      |

#### 

#### vc-data-table-group-tr

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-data-table

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-datapicker

| 属性名         | 子属性名 | 必备  | 类型    | 默认值               | 是否支持脚本 | 样例 |
| -------------- | -------- | ----- | ------- | -------------------- | ------------ | ---- |
| name           |          | true  | string  |                      |              |      |
| required       |          | false | boolean |                      |              |      |
| tooltip        |          | false | string  |                      |              |      |
| inputBoxPrompt |          | false | string  | Input key word here~ |              |      |
| title          |          | false | string  | Data Picker          |              |      |
|                |          |       |         |                      |              |      |

#### 

#### vc-dropzone

| 属性名    | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| --------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name      |          | true  | string |        |              |      |
| model     |          | true  | string |        |              |      |
| component |          | true  | string |        |              |      |
| required  |          | false | bool   |        |              |      |

#### 

#### vc-dynamicbtn

| 属性名 | 子属性名              | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 | 备注              |
| ------ | --------------------- | ---- | ------ | ------ | ------------ | ---- | ----------------- |
| name   |                       | true | string |        |              |      | 不需要暴露给外面  |
| items  | icon,text,target,href | true | array  |        |              |      | 超过4个btn时 下拉 |

#### 

#### vc-edithistory

| 属性名   | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| -------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name     |          | true  | string |        |              |      |
| classes  |          | false | string |        |              |      |
| template |          | false | string |        |              |      |
|          |          |       |        |        |              |      |

#### 

#### vc-error

| 属性名   | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| -------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name     |          | true  | string |        |              |      |
| classes  |          | false | string |        |              |      |
| pagecode |          | false | int    |        |              |      |
|          |          |       |        |        |              |      |

#### 

#### vc-floatingbtn

| 属性名        | 子属性名             | 必备  | 类型    | 默认值 | 是否支持脚本 | 样例                     | 备注             |
| ------------- | -------------------- | ----- | ------- | ------ | ------------ | ------------------------ | ---------------- |
| name          |                      | true  | string  |        |              |                          | 不需要暴露给user |
| top           |                      | false | boolean |        |              |                          |                  |
| bottom        |                      | false | boolean |        |              |                          |                  |
| right         |                      | false | boolean |        |              |                          |                  |
| left          |                      | false | boolean |        |              |                          |                  |
| direction     |                      | false | string  |        |              | top/left/bottom/right    |                  |
| open-on-hover |                      | false | boolean |        |              | =true时，hover自动展开   |                  |
| transition    |                      | false | string  |        |              | 展开时的动画效果         |                  |
| fab           |                      | true  | string  |        |              | 控制icon list的hide/show |                  |
| hideIcon      |                      | true  | string  |        |              |                          |                  |
| showIcon      |                      | true  | string  |        |              |                          |                  |
| icons         | {name,color,onclick} | true  | array   |        |              | 展开的icon列             |                  |

#### 

#### vc-footer

| 属性名 | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ----- | ------ | ------ | ------------ | ---- |
| name   |          | true  | string |        |              |      |
| class  |          | true  | string |        |              |      |
| value  |          | false | string |        |              |      |

#### 

#### vc-form

| 属性名  | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name    |          | true  | string |        |              |      |
| classes |          | false | string |        |              |      |
|         |          |       |        |        |              |      |
|         |          |       |        |        |              |      |

#### 

#### vc-label

| 属性名       | 子属性名 | 必备  | 类型    | 默认值 | 是否支持脚本 | 样例 |
| ------------ | -------- | ----- | ------- | ------ | ------------ | ---- |
| name         |          | true  | string  |        |              |      |
| disableLabel |          | false | boolean |        |              |      |
| tooltip      |          | false | string  |        |              |      |

#### 

#### vc-layout

| 属性名  | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name    |          | true  | string |        |              |      |
| classes |          | false | string |        |              |      |
| style   |          | false | string |        |              |      |
| schemas |          | false | json   |        |              |      |
| options |          | false | json   |        |              |      |

#### 

#### vc-list-item-group

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-multilanguage

| 属性名          | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| --------------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name            |          | true  | string |        |              |      |
| defaultLanguage |          | false | string | zh     |              |      |
|                 |          |       |        |        |              |      |
|                 |          |       |        |        |              |      |

#### 

#### vc-multiselect

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-navigation-drawer

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-pdfviewer

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-peoplepicker

| 属性名         | 子属性名 | 必备  | 类型    | 默认值               | 是否支持脚本 | 样例 | 备注                     |
| -------------- | -------- | ----- | ------- | -------------------- | ------------ | ---- | ------------------------ |
| name           |          | true  | string  |                      |              |      |                          |
| required       |          | false | boolean |                      |              |      |                          |
| tooltip        |          | false | string  |                      |              |      |                          |
| inputBoxPrompt |          | false | string  | Input key word here~ |              |      |                          |
| setValue       |          | false | string  |                      |              |      | 需要思考如何与design对接 |
| isShowDefault  |          | false | boolean |                      |              |      | 是否显示当前用户         |
| onchange       |          | false | string  |                      |              |      |                          |
| title          |          | false | string  | People Picker        |              |      |                          |
| maxSelectCount |          | false | number  | 没有上限             |              |      |                          |

#### 

#### vc-radio

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-rate

| 属性名    | 子属性名 | 必备  | 类型    | 默认值           | 是否支持脚本 | 样例 | 备注 |
| --------- | -------- | ----- | ------- | ---------------- | ------------ | ---- | ---- |
| name      |          | true  | string  |                  |              |      |      |
| dense     |          | false | boolean |                  |              |      |      |
| color     |          | false | string  | orange           |              |      |      |
| bgColor   |          | false | string  | orange           |              |      |      |
| half      |          | false | boolean |                  |              |      |      |
| length    |          | false | boolean |                  |              |      |      |
| hover     |          | false | boolean |                  |              |      |      |
| size      |          | false | number  | 20               |              |      | 大小 |
| readonly  |          | false | boolean | false            |              |      |      |
| emptyIcon |          | false | string  | mdi-star-outline |              |      |      |
| fullIcon  |          | false | string  | mdi-star         |              |      |      |
| halfIcon  |          | false | string  | mdi-star-half    |              |      |      |

#### 

#### vc-rtEditor

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-select

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
| model  |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-sortbtn

| 属性名    | 子属性名       | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 | 备注         |
| --------- | -------------- | ---- | ------ | ------ | ------------ | ---- | ------------ |
| name      |                | true | string |        |              |      | 不暴露给user |
| dataItems | {title,isSort} | true | array  |        |              |      |              |

#### 

#### vc-stepper

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-style

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-switch

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-table

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-tabs

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-template

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-textarea

| 属性名      | 子属性名 | 必备  | 类型                    | 默认值 | 是否支持脚本 | 样例 | 备注       |
| ----------- | -------- | ----- | ----------------------- | ------ | ------------ | ---- | ---------- |
| name        |          | true  | string                  |        |              |      |            |
| counter     |          | false | boolean\|number\|string |        |              |      | 字数计算器 |
| rows        |          | false | number                  |        |              |      | 显示多少行 |
| disabled    |          | false | boolean                 |        |              |      |            |
| readonly    |          | false | boolean                 |        |              |      |            |
| placeholder |          | false | string                  |        |              |      |            |
| rules       |          | false | string                  |        |              |      |            |

#### 

#### vc-textbox

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-toolbar

| 属性名        | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name          |          | true  | string |        |              |      |
| class         |          | false | string |        |              |      |
| width         |          | false | string |        |              |      |
| height        |          | false | string |        |              |      |
| absolute      |          | false | string |        |              |      |
| fat           |          | false | string |        |              |      |
| floating      |          | false | string |        |              |      |
| icons         |          | false | array  |        |              |      |
| multiLanguage |          | false | object |        |              |      |

#### 

#### vc-verify

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-view-card-image

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-view-card-label

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-view-card-list

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-view-card-wrapper

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-view-card

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

#### vc-view

| 属性名 | 子属性名 | 必备 | 类型   | 默认值 | 是否支持脚本 | 样例 |
| ------ | -------- | ---- | ------ | ------ | ------------ | ---- |
| name   |          | true | string |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |
|        |          |      |        |        |              |      |

#### 

# 自定义组件

## 上传