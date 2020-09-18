# HookJS [![gitee.png](https://palerock.cn/api-provider/files/view?identity=L2FydGljbGUvaW1hZ2UvMjAyMDA2MjkxNTQyMTMwNzVXcWZyU2dTbC5wbmc=&w=15)](https://gitee.com/HGJing/everthing-hook)

> 用于劫持方法，进行AOP切面操作

### Hello Word Demo

```javascript
eHook.hookBefore(window,'alert',function(method,args){
	args[0] = args[0] + '[被劫持的参数]';
});
alert('hello eHook'); // hello eHook[被劫持的参数]
```

全局对象：`eHook`，`aHook`

 - `eHook`：包含aop劫持的基本方法 
 - `aHook`：包含 Ajax Url 劫持的基本方法
 
----------

## API 文档
----------
### eHook对象
----------

#### `hookBefore`(parent, methodName, before, context)

在指定方法前执行

`parent`:
类型：`object`，必须，指定方法所在的对象

`methodName`:
类型：`string`，必须，指定方法的名称

`before`:
类型：`function`，必须，回调方法，该方法在指定方法运行前执行
回调参数：  
- `method`: 指定的原方法
- `args`: 原方法运行的参数（在此改变参数值会影响后续指定方法的参数值）

`context`:  
类型：`object`，可选，回调方法的上下文  

返回值：  
类型：`number`，劫持id（用于解除劫持）  


----------
#### `hookCurrent`(parent, methodName, current, context)
劫持方法的运行，在对制定方法进行该劫持的时候，指定方法不会主动执行，替换为执行参数中的current方法

**注意：该方法只能对指定方法进行一次劫持，若再次使用该方法劫持就会覆盖之前的劫持[可以和hookBefore,hookAfter共存，且hookBefore和hookAfter可以对同个指定方法多次劫持]**

`parent`:  
类型：`object`，必须，指定方法所在的对象  

methodName:  
类型：`string`，必须，指定方法的名称  

`current`:  
类型：`function`，必须，回调方法，该方法在指定方法被调用时执行
回调参数及返回值：  
- `parent`: 指定方法所在的对象，类型: `object`
- `method`: 指定的原方法，类型: `function`
- `args`: 原方法的参数，类型: `array`
- `返回值`: 规定被劫持方法的返回值，类型: `*`

`context`:  
类型：`object`，可选，回调方法的上下文  

返回值:  
类型：`number`，劫持id（用于解除劫持） 

例：  
```javascript
eHook.hookCurrent(Math, 'max', function (p, m, args) {
     return m.apply(Math, args) + 1;
});
console.log(Math.max(1, 8)); // 9
```

----------

#### `hookAfter`(parent, methodName, after, context)

在指定方法后执行  

`parent`:  
类型：`object`，必须，指定方法所在的对象  

`methodName`:  
类型：`string`，必须，指定方法的名称  

`after`:  
类型：`function`，必须，回调方法，该方法在指定方法运行后执行  
回调参数及返回值：  
- `method`: 指定的原方法，类型: `function`
- `args`: 原方法的参数，类型: `array`
- `result`: 原方法的返回值，类型: `*`
- `返回值`: 规定被劫持方法的返回值，类型: `*`

`context`:  
类型：`object`，可选，回调方法的上下文  

返回值:  
类型：`number`，劫持id（用于解除劫持）  

例：
```javascript
eHook.hookAfter(Math, 'max', function (m, args, result) {
     return result + 1;
});
console.log(Math.max(1,8)); // 9
```

----------

#### `hookReplace`(parent, methodName, replace, context)

劫持替换指定方法  

**注意：该方法会覆盖指定劫持方法在之前所进行的一切劫持，也不能重复使用，并且不和hookAfter,hookCurrent,hookBefore共存，在同时使用的情况下，优先使用hookReplace而不是其他的方法**

`parent`:  
类型：`object`，必须，指定方法所在的对象  

`methodName`:  
类型：`string`，必须，指定方法的名称  

`replace`:  
类型：`function`，必须，回调方法，该方法的返回值便是替换的方法  
回调参数及返回值：  
- `method`: 指定的原方法，类型: `function`
- `返回值`: 规定被替换的方法内容，类型: `function`

`context`:  
类型：`object`，可选，回调方法的上下文  

返回值:  
类型：`number`，劫持id（用于解除劫持） 

例：  
```javascript
eHook.hookReplace(Math,'max',function (m) {
     return Math.min;
});
console.log(Math.max(1, 8)); // 1
```
----------
### 文档撰写中...
### 如有疑问请评论或留言

