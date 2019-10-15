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
## **vc-peoplepicker**
#### 1、在页面中如何引用？
##### 直接在schema中写入如下格式的，示例：
```json
{
 //必填属性：
 "name": "ClientPicker", 
 "model": "ClientPicker", 
 "component": "vc-peoplepicker",
 //非必填属性：
 "required":true, //默认false
 "tooltip":true, //默认false
 "setValue":["##190709102213221"],//暴露方法：传入staffCode设置已选
 "isShowDefault":false, //是否将当前登录人作为已选||默认false
 "onchange":"console.log(888)",//当选项改变的时候，就会执行
 "inputBoxPrompt":"输入关键字搜索你想要的哇~",//对应弹窗里search-input的placeholder || Input key word here~
 "title": "Picker",//对应弹窗上的picker名称 || People PickerPeople 
 "maxSelectCount": "5",//设置可以选择的最大数量 || 默认没有上限
},
```
#### 2、组件内部属性 & 暴露公共方法
##### 组件内部属性
| 属性名  | 描述 | 必填  |  类型  | 默认值 | 是否支持脚本 | 样例 |
| :-----: | :------: | :---: | :----: | :----: | :----------: | :--: |
|  required   |    是否必选      | false  | string |    false    |              |      |
| tooltip |     浮窗提示文案     | false | string |        |              |    这是给XXX用的peoplepicker  |
| setValue  |    设置默认已选项      | false | arr |    |              |    ["staffCode"]  |
| onchange  |    选项变更执行的方法      | false | string |        |              |    console.log(888)  |
| inputBoxPrompt  |   对应弹窗里search-input的placeholder       | false | string |     Input key word here~   |              |   Input key word here~   |
| title  |   picker对应弹窗上的标题名称       | false | string |       People Picker |              |  People Picker    |
| maxSelectCount  |   设置可以选择的最大数量       | false | string |   没有上限     |              |   5   |
| isShowDefault  |   是否将当前登录人作为已选       | false | string |  false      |              |   true   |

##### 组件暴露外部方法
| 属性名  | 描述 | 必备  |  类型  | 默认值 | 是否支持脚本 | 样例 |
| :-----: | :------: | :---: | :----: | :----: | :----------: | :--: |
|  setValue   |   设置默认选项       | false  | string |        |              |   ["$raiseEvent","$raiseEvent(`peoplepickerName`,`setValue`,`setValue([staffCode])`)"]   |
| onchange |   选项变更执行的方法       | false | string |        |              |     console.log(888) |

#### 3、开发须知
##### getData请求参数说明：
```json
{
         Method: "all",   //返回数据参数：all , user , group
        selectedDatas: selectedDatas || [], //已经选择的数据
        IgnoreStaffs: IgnoreStaffs || [],//不需要返回的数据
        queryContent: queryContent || "",//search的input输入
        index: this.index,//页码
        size: 5,//返回每页的数据个数
        filters: [],//Field Filter --design
        organizationCode: app.tenantId,//tenantId
        appCode: app.appCode,//appCode
        range: [],//Tenant -- design
        showPrivateGroup: false,//是否返回我所在的私有组里面的所有人—design
        searchByGroup: false,//通过group filter ---design
        searchByRole: false,//通过role filter ---design
        groupName: "",//通过group filter时，groupName ---design
        roleName: "",//通过role filter时，roleName ---design
        attribute1: "",//group的attribute1 --- design
        attribute2: "","",//group的attribute2 --- design
        attribute3: "","",//group的attribute3 --- design
        currentStaffCode: currentUserData.staffId,//当前登陆人的staffId
        firstLineDesc: [],//返回的第一行数据显示—design
        firstLineSeparator: "",[],//返回的第一行数据显示分隔符--design
        secondLineDesc: [],[],//返回的第2行数据显示--design
        secondLineSeparator: "",[],//返回的第2行数据显示分隔符--design
        thirdLineDesc: [],[],//返回的第3行数据显示--design
        thirdLineSeparator: "",[],//返回的第3行数据显示分隔符--design
        additionalSearchKey: [],//配置搜索字段，原来的字段（staffname,staffcode,email）会被干掉--design
        withExtendData: false,//是否返回user的全部数据
        relationskey: "StaffCode,StaffName,Email,OrganizationCode,UserID",//用户需要前端保存的数据，就是真正保存到数据库里的数据
        showTermUser: false // 是否显示离职人员

},
```
##### getData 常见返回数据说明：
```json
{
 ActiveFlag：true  //true—未离职  false—已离职
AvatarUrl :    // user对应的avatar图片url  ,  group没有图片，使用默认图
Count ： 5  //返回的数据个数
Email : 
FirstLineDesc
OrganizationCode
Phone
SecondLineDesc
StaffCode //staffId
ThirdLineDesc
Type:1 – user    2—group
UserId
UserName: // staffName
UserInfos:{} 更加详细的个人信息
},
```



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

| 属性名        | 子属性名 | 必备  | 类型            | 默认值 | 是否支持脚本 | 说明               | 样例数据                                  |
| ------------- | -------- | ----- | --------------- | ------ | ------------ | ------------------ | ----------------------------------------- |
| name          |          | true  | string          |        |              |                    |                                           |
| chartType     |          | true  | string          |        |              | 图标类型           |                                           |
| data          |          | false | json            |        |              |                    |                                           |
| colors        |          | false | array           |        |              | 设置颜色主题       |                                           |
| chartSettings |          | false | object          |        |              | 图表全局选项设置   | {"symbol": "diamond"}                     |
| chartExtends  |          | false | array of object |        |              | 图标特定列选项设置 | [{"symbol":"rect"},{"symbol":"triangle"}] |

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

| 属性名  | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例   |
| ------- | -------- | ----- | ------ | ------ | ------------ | ------ |
| name    |          | true  | string |        |              |        |
| classes |          | false | string |        |              |        |
| method  |          | false | string |        |              | get    |
| action  |          | false | string |        |              | /form  |
| target  |          | false | string |        |              | _blank |
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

| 属性名        | 子属性名 | 必备  | 类型    | 默认值 | 是否支持脚本 | 样例 |
| ------------- | -------- | ----- | ------- | ------ | ------------ | ---- |
| name          |          | true  | string  |        |              |      |
| model         |          | true  | string  |        |              |      |
| classes       |          | false | string  |        |              |      |
| isVertical    |          | false | boolean | false  |              |      |
| disabled      |          | false | boolean | false  |              |      |
| required      |          | false | boolean | false  |              |      |
| queryId       |          | false | string  |        |              |      |
| query         |          | false | string  |        |              |      |
| multiple      |          | false | boolean | false  |              |      |
| selectOptions |          | false | array   |        |              |      |
| itemText      |          | false | string  |        |              |      |
| itemValue     |          | false | string  |        |              |      |
| isSolo        |          | false | boolean |        |              |      |
| disableLabel  |          | false | boolean |        |              |      |

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

| 属性名   | 子属性名 | 必备  | 类型   | 默认值 | 是否支持脚本 | 样例 |
| -------- | -------- | ----- | ------ | ------ | ------------ | ---- |
| name     |          | true  | string |        |              |      |
| template |          | true  | object |        |              |      |
|          | created  | false | string |        | true         |      |
|          | methods  | false | object |        | true         |      |
|          | data     | false | object |        |              |      |
|          | template | true  | string |        |              |      |
|          | type     | false | string |        |              |      |

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

| 属性名        | 子属性名 | 必备  | 类型    | 默认值 | 是否支持脚本 | 样例 |
| ------------  | -------- | ----- | ------- | ------ | ------------ | ---- |
| name          |          | true  | string  |        |              |      |
| model         |          | true  | string  |        |              |      |
| classes       |          | false | string  |        |              |      |
| isVertical    |          | false | boolean | false  |              |      |
| disabled      |          | false | boolean | false  |              |      |
| required      |          | false | boolean | false  |              |      |
| inputType     |          | false | string  | text   |              |      |
| preinicon     |          | false | string  |        |              |      |
| isSolo        |          | false | boolean |        |              |      |
| disableLabel  |          | false | boolean |        |              |      |
| preinicon     |          | false | string  |        |              |      |

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