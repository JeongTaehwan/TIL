# JavaScript 유용한 문법 🌼

> 이번엔 Javascript의 유용한 문법에 대해 소개하려고 한다.

## 삼항연산자 

> `?` 와 `:` 를 사용하여 조건문을 만드는 것 이다. 그리고 삼항연산자를 중첩해서 사용하기 보단, `if` 문을 사용하는 것이 더 효율적이다.

```javascript
const hansome = true;

const value = hansome == true ? "나는 잘생겼다~" : "나는 못생겼다~";
console.log(value);
```

> 이런식으로 코드를 작성하면 `hansome` 의 값이 `true` 이므로 `나는 잘생겼다~` 가 출력된다.

---

## Truthy & Falsy 

> Falsy의 값에는 `undefined` , `null` , `0` , `비어있는 문자열` ,`NaN` 이 있다.

---

## 단축 평가 논리 계산법 

```javascript
// &&
console.log(true && 'true값이 아니므로 이 문장이 출력됩니다.');

// ||
console.log(false || 'false값이므로 이 문장을 출력합니다.');
```
> 이런 식으로 단축 평가 논리 계산법에서 `&&` 은 앞의 것이 `true` 면 `true` 를 출력하고, 아니면 뒤의 것을 출력한다. 그러나 `||` 은 앞의 것이 `false` 면 뒤의 것을 출력한다.

## 함수의 기본 파라미터 

```javascript
const MyHeight = (height) => {
    return height;
}

const result = MyHeight(180);
console.log(result);
```
> 만약 위의 코드처럼 작성을 하면 `180` 이라는 값이 출력 될 것이다. 그러나 여기서 만약 파라미터를 안 써주고 기본적으로 지정을 해주려면 어떤 식으로 해야할까?

```javascript
const MyHeight = (height = 180) => {
    return height;
}

const result = MyHeight();
console.log(result);
```
> 이런 식으로 함수안의 파라미터에 미리 값을 넣어주면 된다.

---

## 조건문 더 스마트하게 쓰기 
```javascript
function AnimalSound(animal) {
        if(animal === 'dog') return '왈왈';
        if(animal === 'elephant') return '뿌우우';
        if(animal === 'croco') return '아거아거';
        if(animal === 'rino') return '코뿔코뿔';

        return '소리가 안들려!';
}

console.log(AnimalSound('dog'));
console.log(AnimalSound('elephant'));
console.log(AnimalSound('croco'));
console.log(AnimalSound('rino'));
console.log(AnimalSound('Human'));
```
> 이런식의 가독성이 떨어지는 코드를 더 가독성 있게 바꿀 수 있다.

```javascript
function AnimalSound(animal) {
    const tasks= {
        dog() {
            console.log('왈왈!');
        },
        elephant() {
            console.log('뿌우우!');
        },
        croco() {
            console.log('아거아거');
        },
        rino() {
            console.log('코뿔코뿔');
        }
    };
    if(!tasks[animal]) {
    console.log('소리가 안들려!');
    return;
    }
    
    tasks[animal]();
}

AnimalSound('dog');
AnimalSound('elephant');
AnimalSound('croco');
AnimalSound('rino');
AnimalSound('Human');
```

--- 

## 비구조화 할당 

> 비구조화 할당은 객체와 배열,함수등에서 할 수 있다.

**객체에서의 비구조화 할당** 

```javascript
const Object = {name: 'Taehwan', age: 18};

const {name, age} = Object;

console.log(name);
console.log(age);
```

**배열에서의 비구조화 할당** 

```javascript
const Array = ['Taehwan', 18];

const [name, age] = Array;

console.log(name);
console.log(age);
```

## 함수의 파라미터에서의 비구조화 할당 

> 비구조화 할당은 이전의 객체를 배울때 잠깐 사용했었다.

**값이 주어졌을때** 
```javascript
const Introduce = {
    height: 180,
    weight: 200
};

function print({height, weight}) {
    console.log(height);
    console.log(weight);
}

print(Introduce);
```

**값이 안주어졌을때** 

```javascript
const Introduce = { height: 180 };

function print({height, weight = 200}) {
    console.log(height);
    console.log(weight);
}

print(Introduce);
```

---

## spread와 rest 

> `spread` 는 객체혹은 배열에서 같은 인자를 퍼트릴수 있다.

### spread 

**객체** 
```javascript
const Goblin = {
    name: 'goblin'
};

const Powergoblin = {
    ...Goblin,
    power: true
};

const Kinggoblin = {
    ...Powergoblin,
    army: true
};

console.log(Goblin);
console.log(Powergoblin);
console.log(Kinggoblin);
```

**배열** 

```javascript
const Goblin = ['goblin'];
const Powergoblin = [...Goblin, 'Power!'];
const Kinggoblin = [...Goblin, ...Powergoblin, 'King has army!'];

console.log(Goblin);
console.log(Powergoblin);
console.log(Kinggoblin);
```
> 이런식으로 `...` 을 사용하여 코드를 작성할 수 있다.

### rest 

> `rest` 는 객체,배열,함수의 파라미터에서 사용할 수 있다.

**객체** 

```javascript
const Kinggoblin = {
    name: 'goblin',
    power: true,
    army: true
};

const {name, ...rest} = Kinggoblin;

console.log(name);
console.log(rest);
```

**배열** 

```javascript
const Kinggoblin = ['Goblin', 'Im strong!', 'The king has army!'];

const [name, ...rest] = Kinggoblin;

console.log(name);
console.log(rest);
```
> 이런 식으로 비구조화 할당을 이용하여 코드를 작성할 수 있다. 추가적으로 배열에서의 `rest` 는 맨 앞에 나올 수 없다.

**함수 파라미터에서의 rest** 
```javascript
function add(...rest) {
    return rest.reduce((acc, current) => acc + current, 0);
}

console.log(add(1,2,3,4,5,6,7));
```

> 위의 코드처럼 작성하면 `rest` 가 `add` 함수의 파라미터로 들어간다. 그 이후 받아오는 값들을 배열로 받아오는데, 여기서 배열 내장함수인 `reduce` 를 사용하여 입력받는 값들을 다 더해준다. 결과는 `28` 이 나온다.

**함수 인자에서의 spread** 

- 파라미터: 함수 안에서 괄호안에 받아오는 값
- 인자 : 함수를 사용하기 위해 변수안에 넣어주는 값

```javascript
function add(...rest) {
    return rest.reduce((acc, current) => acc + current, 0);
}
const spread = [1,2,3,4,5,6,7];
console.log(add(...spread));
```

> 이런식으로 인자 안에서 `spread`를 받아올 수 있다.

---

# scope 
- `scope` 란 변수나 함수를 선언할 때 어디서 어디까지 유효한지의 범위를 의미한다.
- ``Global`` , ``Function`` , ``Block`` 가 있다.
- `Global` : 코드 전역에서 쓸 수 있다.
- `Function` : 함수 내부에서만 쓸 수 있다.
- `Block` : 조건문 등의 내부에서만 쓸 수 있다.

```javascript
const result = 'Im Global!';

function Say() {
    const result = 'Im Function!';

    if (true) {
        const result = 'Im Block!';
        console.log(result);
    }
    console.log(result);
}

Say();
console.log(result);
```

- 이런 식으로 코드를 작성할 수 있다. 
- 맨 처음의 `result` 는 `Global` 이므로 코드 어느곳에서든 호출을 할 수 있다. 
- 두번째 `result` 는 `function` 이므로 함수 안에서만 호출이 가능하다. 
- `if` 문 안의 `result` 는 `Block` 이므로 `if` 문 안에서만 호출이 가능하다.

---

# hoisting
> `hoisting` 이란 선언전에 호출이 되었을때 선언을 코드 맨 위로 올려주는 것이다. `let` 과 `const` 는 `hoisting` 이 발생하지 않는다.

```javascript
Say();

function Say() {
    console.log('Hello👋');
}
```
> 이런식으로 코드를 작성해도 실행이 된다.

---

**피드백은 언제나 환영입니다! 😇**   
**오타나 코드에 오류가 있으면 issue를 남겨주세요! 😁**   
**출처 : 패스트캠퍼스 강의 - 벨로퍼트와 함께하는 자바스크립트 유용한 문법**