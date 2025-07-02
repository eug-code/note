### JavaScript Event Loop

#### 微任務(micro task)
#### 宏任務(macro task)

```
console.log('Script start');

// 宏任務
setTimeout(() => {
  console.log('setTimeout 1'); // 這是一個宏任務
}, 0);

// 微任務
Promise.resolve().then(() => {
  console.log('Promise 1'); // 這是一個微任務
});

Promise.resolve().then(() => {
  console.log('Promise 2'); // 這是一個微任務
});

console.log('Script end');

// 宏任務
setTimeout(() => {
  console.log('setTimeout 2'); // 這是一個宏任務
}, 0);
```

macro task會將回調函數放入任務隊列，需要等待當前的所有micro task和同步代碼執行完畢，並且事件循環進入下一個macro task階段時才會執行。