## 1. 功能 throttle
和防抖一样都是减少高频率执行代码的执行频率。


## 2.使用场景
- oninput
- onresize
- onscroll
- onmousemove
- onmousehover
- 等等

## 3.节流 vs 防抖
- 防抖：高频执行函数，降低到执行1次
- 节流：高频执行函数，降低到执行n次，1 < n < 高频次数

## 3.节流原理
### 3.1 利用 setTimeout 延迟执行逻辑代码。在防抖的基础上添加变量，降低 clearTimeout 频率，增加执行次数。

```javascript
  let timer = null;
  let flag = true;
  element2.onmousemove = (event) => {
    if (flag === false) {
      return;
    }
    flag = false;

    if (timer) {
      window.clearTimeout(timer);
    }
    timer = setTimeout(() => {
      flag = true;
      console.log("防抖版本--发送网络请求:", event.target.value);
    }, 1000);
  };
```

### 3.2 封装工具函数


```javascript
  function throttle(fun, delay = 500) {
    let timer = null;
    let flag = true;

    return function () {
      if (flag === false) {
        return;
      }
      flag = false;
      if (timer) {
        window.clearTimeout(timer);
      }
      timer = setTimeout(() => {
        flag = true;
        //无法传递event参数
        // fun();
        fun.apply(this, arguments);
      }, 1000);
    };
  }
```

> [代码链接]()


