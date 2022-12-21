## Set HTML Input value

https://stackoverflow.com/questions/36470788/why-the-difference-between-setting-the-value-of-an-input-via-setattribute-or-dir

The main difference between both the approach is setting the underlying `defaultValue` property. when you use `setAttribute`, the both `defaultValue` property as well as the `value` property will be updated/set. whereas using `.value` will update/set the `value` property of it only.

Behavior 1: (setting value using setAttribute)

```javascript
x.setAttribute("value","test");
x.defaultValue; //"test"
x.value; //"test"
```

Behavior 2: (setting value directly using value property)

```javascript
x.value = "test";
x.defaultValue; //""
x.value; //"test"
```



const { title } = document like thing safe or not?