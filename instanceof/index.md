# javascript instanceof 方法

### A instanceof B 判断B是否存在A的原型链上

### 手写
```js
  function myInstanceOf(leftVal, rightVal){
    let rightProto = rightVal.prototype;
    leftVal = leftVal.__proto__;
    while(1){
      if(rightVal === null){
        return false;
      }
      if(leftVal === rightProto){
        return  true;
      }
      leftVal = leftVal.__proto__;
    }
  }
```