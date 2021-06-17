# requestIdleCallback

### 在浏览器空闲时，调用回调函数，可以执行一些后台操作/第优先级任务，返回一个 任务id，可以通过 cancelIdleCallback(id) 取消回调任务

```ts
interface IdleDeadlineProps {
  didTimeout: boolean // 回调函数是否超时还未执行
  timeRemaining: () => number //  并且是浮点类型的数值，它用来表示当前闲置周期的预估剩余毫秒数。如果idle period已经结束，则它的值是0
}
interface OptP {
  timeout: number //期望在多少秒后执行，如果超时未执行，那么didTimeout = true,并且将会在下次空闲的时候被强制执行
}
var handleId:number = window.requestIdleCallback( callback : (IdleDeadline: IdleDeadlineProps) => any,  options?: { timeout: number })
```

