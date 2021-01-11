## 1. 功能 debounce
减少高频率执行代码的执行频率。


## 2.使用场景
- oninput
- onresize
- onscroll
- onmousemove
- onmousehover
- 等等

## 3.防抖原理
### 3.1 利用 setTimeout 延迟执行逻辑代码。通过 clearTimeout 将执行次数降低 1

```javascript
  let timer = null;
  element2.onkeyup = (event) => {
    if (timer) {
      window.clearTimeout(timer);
    }
    timer = setTimeout(() => {
      console.log("防抖版本--发送网络请求:", event.target.value);
    }, 1000);
  };
```

### 3.2 封装工具函数


```javascript
  function debounce(fun, delay = 500) {
    let timer = null;
    return function () {
      if (timer) {
        window.clearTimeout(timer);
      }
      timer = setTimeout(() => {
        //无法传递event参数
        // fun();
        fun.apply(this, arguments);
      }, 1000);
    };
  }
```

> [代码链接]()
