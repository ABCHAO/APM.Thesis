# default

## Schema Properties

Schema properties may be set in schema

### name

Type: String

- Required
- Unique

An Unique ID of a schema control which is also used as key for locale settings.

### component

Type: String

- Required

Determine which control to render.

### model

Type: String

Determine which property of the model object to be used as value.

### classes

Type: String

Assign to the class attribute of the root element of a control.

### style

Type: Object

Assign to the style attribute of the essential element of a control which may vary between controls.

### created

Type: Function

If available, called synchronously on VUE instance created hooks.

### label

Type: String

Used as fallback label when locale setting 

### direction

Type: String

Used for determining the layout of control

### tooltipName

Type: String

Used for tooltip displaying

### show

Type: Boolean

Deterimine if to render control 

## Properties

These properties can be accessed in template

### pageView

Type: String

- ReadOnly

Current pageView name, can be overrided by vc-form.

### isNew

Type: Boolean

- ReadOnly

Determine if the current page is in add mode.

### isVertical

Type: Boolean

Default: true

- ReadOnly

Determine if the control layout is vertical

### permission

Type: Boolean

read/white to the property "show"



# form

## Schema Properties

### required

Type: Boolean

Determine if a control shall be validate on form submission.

### mode

Type: String

option: readonly

Determine if a control to be editable

## Properties

### isEdit

Type: Boolean

- RealOnly

Determine if the control is editable.

### value

Read/write to the property defined in schema property "model"

# query

### query

#### list - a.k.a SystemDataSources

```json
{
	"type":"list",
    "id":"SubTopic",
    "queryKey":"Topic"
}
```

id: need to case-sensitively match the "Name" fields in SystemDataSources

queryKey:  need to case-sensitively match the "Name" field in the fields setting in SystemPageSettings. 



#### form - a.k.a SystemQuerySettings

```json
{
    "type": "form",
    "id": "response",
    "searchValues":{
        "searchId":"_id"
    }
}
```

id: need to case-sensitively match the "Code" fields in SystemQuerySettings,

searchValues: see the example below

```json
[{"Name":"CentralisedConsultationSystemId","Value":"@@searchValue","Operator":"Equal","Method":"And"}] 
```

This is a Filter setting in SystemQuerySettings, which defines a variable "id". Accordingly, the searchValues will be 

```json
{
	"searchValue":"source"
}
```

when the model is something like

```json
{
    "source": "8fa371c4-8c3f-400c-aa23-aa5d342f7f2f"
}
```

the searchValue will be assemble as

```json
{
	"searchValue": "8fa371c4-8c3f-400c-aa23-aa5d342f7f2f"
}
```

In the back end, the query will be

```json
{
	"CentralisedConsultationSystemId": "8fa371c4-8c3f-400c-aa23-aa5d342f7f2f"
}
```

### beforeQuery

Type: Function

Run before query request being called

### afterQuery

Type: Function

Run after query response recevied and data been assigned to queryResult



## Example

```
[{
    "name": "toolbar",
    "model": "toolbarObj",
    "component": "vc-toolbar",
    "ins": 1,
    "class": "tool-box",
    "multiLanguage": {
      "name": "multilanguage",
      "component": "vc-multilanguage",
      "defaultLanguage": "zh"
    }
  },
  {
    "component": "vc-layout",
    "classes": "container justify-center",
    "items": [{
      "schemas": [{
        "component": "vc-form", 
        "schemas": [{
          "name": "state",
          "component": "vc-stepper",
          "model": "state",
          "query": {
            "type": "list",
            "id": "OpportunityStatus"
          }
        }]
      }]
    }]
  }
]

```

##

# Function

The function provides ways to run JavaScript code snippets on various occasions during the VUE component instance lifecycle . By default, schema and model objects will be passed to the constructed function.

### Syntax

[["arg1" [, "arg2"[, ..."argN"],] script]]

### Parameters

##### arg1,arg2,...argN

Names to be used by the function as formal argument names, which must be valid property names of an VUE component instance or an undefined parameter will be passed.

##### script

A string containing JavaScript scripts.

### Example

["$set", "$route", "$set(model, 'name', $route.name)"]

This will be used to construct a function as following:

```javascript
function(){ 
	return (function(model, schema, $set, $route){ 
        $set(model, 'name', $route.name) 
    })(this.model, this.schema, this.$set, this.$route)
}.bind(this)
```

