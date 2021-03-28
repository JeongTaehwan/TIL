# JavaScript 비동기 처리

# 비동기 처리

- 비동기 처리란 어떤 작업을 수행중일때 다른 작업이 대기 상태가 아닌 동시에 작업을 하는 것을 의미한다.
- 주로 `Ajax Web API 요청` , `파일 읽기` , `암호화 복호화` , `작업 예약` 등에 사용된다.
- 비동기 처리가 끝난후 무언가를 하고싶으면 `callback` 함수를 사용하면 된다.

```javascript
function hunt(callback) {
  setTimeout(() => {
    const hunt = Date.now();
    for (let i = 0; i >= 10000000000; i++) {}
    const endhunt = Date.now();
    console.log(endhunt - hunt + "ms");
    callback(endhunt - hunt);
  }, 0);
}

console.log("사냥을 시작합니다!🦴");
hunt((ms) => {
  console.log("사냥을 마쳤습니다.🦴");
  console.log(ms + "ms 걸렸습니다..🦴");
});
console.log("다음 사냥을 시작합니다!🦴");
```

- 이런 식으로 코드를 출력하면 `사냥을 시작합니다!🦴` 가 출력되고 함수가 호출이 되어 함수가 실행되고, 함수가 실행되는 동안 `다음 사냥을 시작합니다!🦴` 가 실행된다. 그 후 함수가 다 돌면 `console.log(endhunt - hunt + "ms");` 가 수행되고 그 다음 `callback` 함수가 실행되어 `사냥을 마쳤습니다.🦴` 와 `console.log(ms + "ms 걸렸습니다..🦴");` 가 출력된다.

# Promise

- `callback` 함수가 많으면 코드가 난잡해져 일명 `callback 지옥`이 만들어진다.
- 이런 상황을 대비할땐 `Promise` 를 사용하면 된다.

```javascript
function increaseAndPrint(n) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const value = n + 1;
      if (value === 5) {
        const error = new Error();
        error.name = "Error!";
        reject(error);
        return;
      }
      console.log(value);
      resolve(value);
    }, 1000);
  });
}

increaseAndPrint(0)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .then(increaseAndPrint)
  .catch((e) => {
    console.error(e);
  });
```

- 이런식으로 코드를 작성해 코드의 가독성을 높힐 수 있다.
- `Promise` 선언은 `new Promise` 를 붙여 사용할 수 있다.
- `resolve` 와 `reject` 는 성공 실패여부에 따라 나뉜다.
- `catch` 는 오류를 출력해준다.
