# requestAnimationFrame

### 告诉浏览器在下载重绘之前调用callback函数
```ts
// timestamp 时间戳
var animationId =  window.requestAnimationFrame(callback: (timestamp: number) => any)
// 取消callback
window.cancelAnimationFrame(animationId)
```