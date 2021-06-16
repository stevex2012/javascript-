# javascript 数据类型

## 基本数据类型
undefined null boolean number string symbol bigint
## 引用数据类型
object function

### 如何判断数据类型
- typeof
- Object.prototype.toString.call(arg)

### eg
- typeof undefined  --> 'undefined'
- typeof null  --> 'object' (一个js历史bug)
- typeof true/false  --> 'boolean'
- typeof 0  --> 'number'
- typeof Symbol(1)  --> 'symbol'
- typeof BigInt(1)  --> 'bigint'

- 看看typeof 遇上引用数据类型
- typeof []  --> 'object'
- typeof {}  --> 'object'
- typeof function foo(){}  --> 'function'

### typeof 只能判断基础数据类型（仅限于字面量式变量除开null）和函数，不能判断Array和Object
- typeof new String('1') --> 'object'

### Object.prototype.toString.call(arg) 可以判断所有数据类型，返回数据 "[object xxx]"
- Object.prototype.toString.call(undefined) --> '[object Undefined]'
- Object.prototype.toString.call(null) --> '[object Null]'
- Object.prototype.toString.call(true) --> '[object Boolean]'
- Object.prototype.toString.call(Symbol(1)) --> '[object Symbol]'
- Object.prototype.toString.call(BigInt(1)) --> '[object BigInt]'
- Object.prototype.toString.call([]) --> '[object Array]'
- Object.prototype.toString.call({}) --> '[object Object]'
- Object.prototype.toString.call(function foo(){}) --> '[object Function]'

### 判断数据类型函数
```js
function dataType<T>(data: T): string{
  var result = Object.prototype.toString.call(data)
  return result.replace(/\[/g,'').replace(/\]/g,'').split(' ')[1].toLowerCase()
}
```
