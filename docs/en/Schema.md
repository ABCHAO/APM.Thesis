# Schema

## Properties

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

### required

Type: Boolean

Determine if a control shall be validate on form submission.

### label

Type: String

Used as fallback label when locale setting 

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

