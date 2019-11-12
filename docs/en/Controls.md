## vc-select

Type: form, query

#### example

```json
{
	"component": "vc-select",
    "name": "Event",
	"label": "Meetings",
	"model": "Event",
	"query": {
		"type": "list",
		"id": "MeetingType",
        "queryKey": "Type"
    }
}
```

### itemText

Type: String

Default: value

Determine which field to be used for displaying

### itemValue

Type: String

Default: value

Determine which field to be used for filling model

### Multiple

Type: Boolean

Default: false

Determine if mulitple value can be selected



## vc-textbox

Type:  form

#### example

```json
{
	"component": "vc-textbox",
    "name": "Event",
	"label": "Meetings",
	"model": "Event",
	"required": true,
	"pattern": "^[a-zA-Z]*$"
}
```

## vc-radio

Type: form, query

#### example

```json
{
	"component": "vc-radio",
    "name": "Event",
	"label": "Meetings",
	"model": "Event",
	"required": true,
	"query": {
		"type": "list",
		"id": "MeetingType"
    }
}
```

## vc-rtEditor

Type: form

```json
{
	"component": "vc-rtEditor",
    "name": "Event",
	"label": "Meetings",
	"model": "Event",
	"required": true,
}
```

## vc-peoplepicker

Type: form

```json
{
 "name": "ClientPicker", 
 "model": "ClientPicker", 
 "component": "vc-peoplepicker",
 "required":true,
 "tooltip":true, 
 "setValue":["##190709102213221"],//暴露方法：传入staffCode设置已选
 "isShowDefault":false, //是否将当前登录人作为已选||默认false
 "inputBoxPrompt":"Input key word here.",
 "title": "Picker",//对应弹窗上的picker名称 || People PickerPeople 
 "maxSelectCount": "5",//设置可以选择的最大数量 || 默认没有上限
},
```

## vc-checkbox

Type: form

```json
{
	"component": "vc-checkbox",
    "name": "Event",
	"label": "Meetings",
	"model": "Event",
	"required": true,
}
```



## vc-datetime-picker

Type: form

```json
{
    "component": "vc-datetime-picker",
    "label": "Client Meeting Date & Time",
    "model": "MeetingDate",
    "name": "ClientMeetingDate",
    "mode": "date"
}
```

## vc-form

Type: default

```json
{
	"component": "vc-form",
    "pageView":"meeting",
	"schemas": []
}
```

### pageView

Type: String

- Required
- unique
- case-insensitive

This field has to be identical with the name of the form. This setting will also override its child controls.

## vc-layout

Type: default

```json
{
	"component": "vc-layout",
	"items": []
}
```

### items

```json
{
	"classes":"sm6 xs12",
	"schemas":[]
}
```

#### classes

Type: String

Set to "xs12" by default.

## vc-tabs

Type: default

```json
{
	"component": "vc-tabs",
	"name": "tab-1",
	"items": []
}
```

### items

```json
{
	"name":"basic",
    "label":"Basic Information",
	"schemas":[]
}
```

## vc-panel

Type: default

```json
{
	"component": "vc-panel",
	"name": "tab-1",
	"expand": true,
	"items": []
}
```

### expand

Type: Boolean

Determine if the panel items shall expand on loaded

### items

```json
{
	"name":"basic",
    "label":"Basic Information",
	"schemas":[]
}
```

## vc-stepper

Type: query

```json
{
	"name": "State",
	"component": "vc-stepper",
	"label": "State",
	"model": "State",
	"query": {
		"type": "list",
		"id": "Opportunity_Workflow"
	}
}
```

## vc-template

Type: default

```json
{
	"component": "vc-template",
	"name": "section2-note",
	"template": {
		"template": "<div class='pa-3' style='color:red'><p>{{label}}</p></div>",
		"name": "section2-note-template"
	}
}
```

### Type

Type: String

options: form.query, default

Determine which type the template will be

### template

Type: Object

```json
{
	"template": "<div class='pa-3' style='color:red'><p>{{ data.dateString }}</p></div>",
	"name": "section2-note-template",
	"data":{
		"dateString": "YYYY-MM-DD"
	}
}
```

#### data

Type： Object

Assign to data object

## vc-button-group

Type: default

```json
{
    "name": "button-1",
    "component": "vc-button-group",
    "items": []
}
```

### items

```json
{
	"name": "button3",
	"label": "Reopen",
	"action": "b7b23ab3ddc7415cb8beee92a1e10101",
	"type": "submit",
	"showCondition": ["return model.Ng_WorkflowStateDisplayName==='Completed'"]
}
```

#### action

Type: String

Set to workflow action code

#### type

Type: String

Option: "button", "submit"

button type

#### showCondition

Type: Function

Determine the condition of the button displaying, must return value.

## Customized control

### Type

Type: String, Array

Option: form, query,

### Control

Type: Object

Native VUE component object

```javascript
{
    template: '<button :class="bg" @click.stop="getClasses(i, items[0])">{{current}}</button>',
    props: {
      items: {
        type: Array,
        required: true
      },
      current: Object
    },
    computed: {
      bg: function () {
        return "color-" + this.items.indexOf(this.current);
      }
    },
    methods: {
      getClasses: function (i, item) {
        var ccs = {};
        ccs["color-" + i] = 1;
        ccs["active"] = item === this.current;
        return ccs;
      }
    }
  }
```

### name

Type: String

- Required
- Unique

### example

tenant-app.js

```javascript
var ctls = (window.customizedControls = window.customizedControls || []);
var control = {
	name:"button-control-1",
	control:{
		template: "", //...
	},
    type: ["form", "query"]
}
ctls.push(control);
```

schema

```json
{
	"component":"button-group-1",
    "name":"button-group-1-name",
    "query":{
        "id":"query-id",
        "type":"list"
    }
}
```

