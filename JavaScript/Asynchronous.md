# JavaScript 비동기 처리🥷🏼

# 비동기 처리🥷🏼

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

# Promise🥷🏼

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

# async await🥷🏼

- `async await` 는 `promise` 를 더 간편하고 간결하게 사용할 수 있게 해준다.

```javascript
function sleep(n) {
  return new Promise((resolve) => setTimeout(resolve, n));
}

async function process() {
  console.log("잠에 듭니다..");
  await sleep(1000);
  console.log("잠에 들었습니다..");
}

process();
```

## async await에서 오류 잡아내기

```javascript
function sleep(n) {
  return new Promise((resolve) => setTimeout(resolve, n));
}

async function sleepfail() {
  await sleep(1000);
  const error = new Error();
  error.name = "불면증으로 인한 수면 실패";
  throw error;
}
async function process() {
  try {
    await sleepfail(1000);
  } catch (e) {
    console.error(e);
  }
}

process();
```

- 이런식으로 코드를 작성하여 오류를 잡아낸다.
- `throw` 를 이용하여 오류를 던져주고, `try catch` 로 오류를 잡아낸다.

# Promise.all🥷🏼

- 여러개의 `promise` 를 동시에 처리할 떄 사용함
- `promise.all` 의 인자에서 하나라도 `error` 가 있으면 전체가 `error` 로 간주됨

```javascript
function sleep(n) {
  return new Promise((resolve) => setTimeout(resolve, n));
}
const Human = async () => {
  await sleep(1000);
  return "우가우가";
};
const Rat = async () => {
  await sleep(300);
  return "찍찍!";
};
const Pig = async () => {
  await sleep(3000);
  return "꿀꿀";
};

async function process() {
  const result = await Promise.all([Human(), Rat(), Pig()]);
  console.log(result);
}

process();
```

- 이런식으로 코드를 작성해 한번에 출력되게 해줄 수 있다.

# Promise.race🥷🏼

- 등록한 `promise` 들 중 가장 먼저 나온 것을 출력함
- `promse.race` 에선 `error` 가 발생했을때 가장 빨리 끝난 것을 `error` 로 간주함

```javascript
function sleep(n) {
  return new Promise((resolve) => setTimeout(resolve, n));
}
const Human = async () => {
  await sleep(1000);
  return "우가우가";
};
const Rat = async () => {
  await sleep(300);
  return "찍찍!";
};
const Pig = async () => {
  await sleep(3000);
  return "꿀꿀";
};

async function process() {
  const first = await Promise.race([Human(), Rat(), Pig()]);
  console.log(first);
}

process();
```

- 이런식으로 코드를 입력하면 가장 빠른것이 `Rat` 이므로 `찍찍!` 이 출력된다.

### 피드백은 언제나 환영입니다! 😇
### 오타나 코드에 오류가 있으면 issue를 남겨주세요! 😁
### 출처 : 패스트캠퍼스 강의 - 벨로퍼트와 함께하는 자바스크립트 비동기 처리
