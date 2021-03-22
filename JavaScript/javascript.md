# JavaScript👨‍💻

### 자바스크립트란?👨‍💻

- 자바스크립트는 ‘웹페이지에 생동감을 불어넣기 위해’ 만들어진 프로그래밍 언어.
  자바스크립트로 작성한 프로그램을 스크립트(script) 라고 부름. 스크립트는 웹페이지의 HTML 안에 작성할 수 있는데, 웹페이지를 불러올 때 스크립트가 자동으로 실행됨.
  스크립트는 특별한 준비나 컴파일 없이 보통의 문자 형태로 작성할 수 있고, 실행도 할 수 있음.

### 자바스크립트는 왜 쓰나요?👨‍💻

- 웹사이트를 더 동적으로 만들기 위해
- 사용자의 행동에 반응 할 수 있기 떄문
- 새로운 HTML 태그를 추가할 수 있기 때문
- 등등...

# 변수선언👨‍💻

- JavaScript에서의 변수 선언은 `let` , `var` , `const`가 있음
- `let`과 `var`은 변수,즉 선언을 한 후 값을 바꾸어도 문제없이 출력이 됨
- `const`는 상수, 즉 선언을 한 후 값을 바꾸면 오류가 출력 됨

```javascript
let a = "Hello World!🐬";
var b = "Hello World!🐬";
const c = "Hello World!🐬";

console.log(a);
console.log(b);
console.log(c);
```

```javascript
let a = "Hello World!🐬";
a = "Puwan is Hansome😎";

console.log(a);
```

- 이런식으로 코드를 작성할 시 마지막으로 값을 지정해준 `'Puwan is Hansome'`이 출력 되어진다.

```javascript
const a = "Puwan is ugly🤢";
a = "It is a lie😥";

console.log(a);
```

- 허나 이런식으로 코드를 작성하면 `const`는 값을 변경할 수 없기 떄문에 오류가 뜬다.

# 연산자👨‍💻

## NOT

- 값을 그 값의 반대값으로 변환해줌. 코드로 표시할땐 `!`로 표시함

```javascript
let a = !true;
console.log(a);
```

- 이런식으로 코드를 작성하면 `true`의 `NOT`값이므로 반대 값인 `false`를 출력하게 된다.

## AND

- 두 값이 모두 `true`값이 나와야 `true`를 출력함. 코드로 표시할땐 `&&`로 표시함

```javascript
let a = true && true;
console.log(a);
```

- 이렇게 작성하면 값은 `true`가 나온다.

## OR

- 두 값중 하나라도 `true`값이 나오면 `true`가 출력됨. 코드로 표시할땐 `||`로 표시함

```javascript
let a = true || false;
console.log(a);
```

- 이렇게 작성하면 값은 `true`가 나온다.

# 조건문👨‍💻

- 조건이 `true`값일때 지정한 값을 출력해주는 문법

## if, else if, else

```javascript
let a = 2;

if (a - 1 == 0) {
  console.log("True!");
} else if (a - 2 == 0) {
  console.log("Second True!");
} else {
  console.log("Error!");
}
```

- 이런식으로 코드를 작성하면 조건인 `a - 2 == 0`이 `true`값이므로 `'True2'`가 출력된다. 문법의 처음에 나오는 `if`의 조건이 일치하지 않으므로 `else if`로 넘어가 조건을 확인한다. 만약 `if`와 `else if`의 조건이 다 `true`가 아니면 마지막으로 `else`의 값이 나오게 된다.

## switch case

```javascript
let sports = "soccer";

switch (sports) {
  case "soccer":
    console.log("손흥민");
    break;
  case "baseball":
    console.log("추신수");
    break;
  case "ssirum":
    console.log("강호동");
    break;
}
```

- 이런식으로 코드를 작성하면 괄호안에 있는 `sports`의 값에 따라 조건문의 출력값이 달라진다. 여기선 `sports` 변수안에 `'soccer'`이라는 문자열이 선언되어있으므로 `case 'soccer':`코드의 값이 출력되 '손흥민'이라는 값이 나오게 된다.

- `switch case`문에서 `break`를 선언하지 않으면 다음 case의 값까지 출력이 된다. 위의 코드로 예를 들면 `'추신수'`를 출력한 후 `break`를 안하면 다음 case의 값인 `'강호동'`까지 출력되게 된다.

# 함수👨‍💻

- 특정코드를 하나의 명령어로 실행하게 해주는 기능
- 파라미터가 주어졌을때 결과를 만들어 낼 수 있음
- 함수안에서 조건문이나 반복문을 사용하여 더욱 유용한 함수를 만들 수 있음

```javascript
const a = 1;
const b = 2;
const add = a + b;

console.log(add);
```

위의 코드를👇

```javascript
function add(a, b) {
  return a + b;
}

const result = add(1, 2);
console.log(result);
```

- 이런 식으로 하나의 명령어로 설정하여 코드를 더 가독성있게 만들 수 있다.

## Function Template Literal

```javascript
function Introduce(hobby) {
  console.log(`Im doing ${hobby} now!`);
}

const result = Introduce("Soccer");
console.log(result);
```

- 이런 식으로 `` ` ``키를 이용하여서도 함수를 선언할 수 있다.

## Arrow Function

```javascript
const Introduce = (hobby) => {
  console.log(`Im doing ${hobby} now!`);
};

Introduce("Soccer");
```

- 이런 식으로 코드를 더 간결하게 해주는 화살표 함수 라는 것도 있다.

# 객체👨‍💻

- 어떠한 값을 선언하게 될때 하나의 이름에 여러 값을 넣을 수 있게 해줌

```javascript
const Me = {
  name: "Taehwan",
  age: 18,
  height: "250cm",
  weight: "300kg",
  girlfriend: undefined,
};

console.log(`저의 이름은 ${Me.name} 입니다. 
            키는 ${Me.height} 이고 몸무게는 ${Me.weight}입니다.
            여자친구는 ${Me.girlfriend} 입니다.`);
```

- 이런식으로 Me라는 객체안에 이름,나이,키,몸무게,여자친구 여부를 넣어주었다.

## 객체 비구조화 할당

```javascript
const Me = {
  name: "Taehwan",
  age: 18,
  height: "250cm",
  weight: "300kg",
  girlfriend: undefined,
};
const { name, age, height, weight, girlfriend } = Me;
console.log(`저의 이름은 ${name} 입니다. 
            키는 ${height} 이고 몸무게는 ${weight}입니다.
            여자친구는 ${girlfriend} 입니다.`);
```

- 이런식으로 비구조화 할당을 사용해 좀 더 편하게 객체를 사용할 수 있다.

## 객체안에 함수넣기

```javascript
const korean = {
  name: "승철",
  sound: "안녕하세요!",
  say: function () {
    console.log(this.sound);
  },
};

const american = {
  name: "Mikle",
  sound: "Hello!",
  say: function () {
    console.log(this.sound);
  },
};

korean.say();
american.say();
```

- 이런식으로 객체안에 함수를 넣을 수 있다. 함수안의 `this`는 `this`가 포함된 객체를 가리킨다.

## 객체안의 Getter Setter함수

## Getter

```javascript
const Taehwan = {
  age: 18,
  name: "taehwan",
  get _name() {
    console.log("이름을 출력합니다...");
    return this.name;
  },
};

console.log(Taehwan._name);
```

- 위의 코드에서 보다시피 `get`이라는 함수를 불러와 `'이름을 출력합니다'`라는 문장을 return하게 된다.
- `get`함수는 반드시 `return`값이 필요하다.

## Setter

```javascript
const Taehwan = {
  _age: 18,
  name: "taehwan",
  set age(value) {
    this._age = value;
  },
};

console.log(Taehwan._age);
Taehwan._age = 17;
console.log(Taehwan._age);
```

- 이런식으로 코드를 작성하면 처음의 `console.log`는 초깃값의 18이 나오지만 다시 재정의를 해준 후 출력을 하면 17이 나오게된다.

# 배열👨‍💻

- 여러개의 항목들의 담겨있는 리스트
- 배열의 `index`값은 `0`부터 시작함
- `javascript`에서의 배열은 인덱스의 형이 굳이 일치할 필요가 없음

```javascript
const arr = [1, true, { a: 1 }, 4];

console.log(arr);
console.log(arr[0]);
console.log(arr.length);
```

- 이런식으로 코드를 작성하면 처음 출력한 값은 `[1, true, { a: 1 }, 4]`가 나오고, 두번째 출력 값은
  `1`이 나온다. 변수명 뒤에 `[]` 를 붙이면 그 `[]` 안의 인덱스 값을 보여준다. 그리고 배열 내장함수인 length는 배열의 길이를 알려준다. 이 코드의 경우 `4`가 출력된다.

# 배열 - 2 (내장함수)

## forEach

```javascript
const country = ["america", "korea", "china", "japan", "france"];

country.forEach((manycountry) => {
  console.log(manycountry);
});
```

- 이런 식으로 forEach문을 사용해 같은 결과를 주는 다른 코드들 보다 더 간결하게 작성할 수 있다.

## Map

- `Map` 은 배열 안의 원소를 변환할 때 사용한다.

```javascript
const array = [1, 2, 3, 4, 5];

const squared = array.map((n) => n * n);
console.log(squared);
```

- 위의 코드에선 `array` 에 `Map` 함수를 사용하여 제곱시켰으니 `1 , 4 , 9 , 16 , 25` 가 출력된다.

## Filter

- `Filter` 함수는 특정 조건을 만족하는 원소들을 찾아 그 원소들을 가지고 새로운 배열을 만드는 함수이다.

```javascript
const fruits = [
  {
    name: "apple",
    smell: false,
  },

  {
    name: "banana",
    smell: false,
  },

  {
    name: "durian",
    smell: true,
  },
];

const SmellOnOff = fruits.filter((fruits) => fruits.smell === true);
console.log(SmellOnOff);
```

- 이런 식으로 코드를 작성하면 `filter` 함수가 `smell` 의 값이 `true` 인 객체를 꺼내어 새로운 배열을 만들어준다.

## Splice & Slice

## Splice

- `Splice` 함수는 배열의 어떠한 값부터 지정한 값까지 지워주는 함수이다.

```javascript
const soccerplayer = ["messi", "ronaldo", "neymar", "pogba", "ramos"];

const index = soccerplayer.indexOf("ronaldo");
const spliced = soccerplayer.splice(index, 1);
console.log(soccerplayer);
```

- 이런식으로 코드를 작성하면 `indexOf` 로 선택한 `ronaldo` 부터 `1` 칸을 지워주는 것이므로 `["messi", "neymar", "pogba", "ramos"]` 가 출력된다.

## Slice

- `Slice` 함수는 `Splice` 와는 달리 기존의 배열은 건들이지 않고 따로 빼내어 출력한다.

```javascript
const soccerplayer = ["messi", "ronaldo", "neymar", "pogba", "ramos"];

const sliced = soccerplayer.slice(0, 2);
console.log(sliced);
console.log(soccerplayer);
```

- 이런식으로 코드를 작성하면 `slice`하여 `index[0]`의 값부터 2칸을 자르는 거니까 `["messi", "ronaldo"]` 가 출력되고 기존의 배열은 그대로 출력된다.

<!--
## Shift Pop Unshift Push

```javascript

```

## Reduce

````javascript

``` -->

## Plus +

- 추가적으로 `indexOf` , `findIndex` , `find` 등의 함수가 있다.
- `indexOf` : 찾고자하는 원소의 위치를 찾을 때 , index값을 반환한다.
- `findIndex` : 찾고자하는 원소의 위치를 `indexOf` 만으로 찾을 수 없을 때 , index값을 반환한다.
- `find` : 찾은 값을 반환한다.

# 반복문👨‍💻

- 특정 작업을 반복적으로 사용할 때 사용하는 구문

## For

```javascript
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

- 이런 식으로 `For`문을 작성할 수 있다 `()`안의 내용은 `0`으로 초기화한 변수 `i`를 설정한 후 `i`가 `10`보다 작을 떄까지 돌아가며 `1`씩 증가한다는 뜻이다.

```javascript
const arr = ["태환이는", "매우", "잘생겼다"];

for (let i = 0; i <= arr.length; i++) {
  console.log(arr[i]);
}
```

- 이런 식으로 배열과도 함께 사용할 수 있다.

## While

```javascript
let handsome = false;
let i = 0;

while (!handsome) {
  console.log(i);
  i++;

  if (i === 18) {
    handsome = true;
    console.log("Im Hansome!");
  }
}
```

- 이런식으로 For문의 경우는 보통 숫자가 어느 정도에 도달하면 멈추는 조건을 자주 사용하지만 While문은 주로 어떠한 값의 True 나 False값으로 조건을 사용한다.

## For Of

- 보통 배열을 사용할 때 주로 사용함

```javascript
const arr = [1, 2, 3, 4, 5];

for (let array of arr) {
  console.log(array);
}
```

- 이런 식으로 코드를 작성하면 1,2,3,4,5가 출력된다.

## For in

- 보통 객체를 사용할 때 주로 사용함

```javascript
const dog = {
  name: "Johnny",
  age: 1,
};

for (let key in dog) {
  console.log(`${key} : ${dog[key]}`);
}
```

- 이런 식으로 코드를 작성하면 `name: Johnny age: 1`가 출력된다.

## Continue Break

```javascript
for (let i = 0; i <= 10; i++) {
  if (i === 2) continue;
  console.log(i);
  if (i === 7) break;
}
```

- 이런 식으로 코드를 작성하면 `i` 가 `2` 를 만났을때 `continue` 를 실행해 다음 동작을 수행하고, `i` 가 `7` 을 만나면 반복문이 멈추게 된다. 즉 결과값은 `0 , 1 , 3 , 4 , 5 , 7 ` 가 된다.
