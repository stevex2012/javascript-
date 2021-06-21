# 类型转换

- 强制类型转换
- 隐式类型转化

### 强制类型转换

- Boolean(xxx)
- Number(xxx)
- String(xxx)
用这三个函数之一转换值，将创建一个新值，存放由原始值直接转换成的值。这会造成意想不到的后果。

### 隐式类型转化

- boolean 隐式转换
 ```js
 const a = 0;
 const b = 1;
 if(a) console.log(1)
 if(b) console.log(0)
 ```
- 字符串隐式转换
当对字符串进行运算的时候
```js
const foo = '123';
const bar = foo - 10; // 113
const f = foo / 10 // 12.3
const b = foo * 2 // 248
const c = foo + 123; // '123123'
```
- 对象隐式转换
当对象进行运算的时候, 
-- 当转换成number的时候，
1.调用 valueOf()。如果结果是原始值（不是一个对象），则将其转换为一个数字。
2.否则，调用 toString() 方法。如果结果是原始值，则将其转换为一个数字。
3.否则，抛出一个类型错误。
-- 转换成string类型的时候，先调用toString，在调用valueOf
```js
  const obj = {}
  const obj2 = {valueOf: () => return 1}

  const r1 = obj + 1; //'[object Object]1'
  const r2 = obj2 + 1 // 2

  const r3 = obj * 2 // NaN

```

