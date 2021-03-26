# JavaScript 유용한 문법🌼

# 삼항연산자🌼

- `?` 와 `:` 를 사용하여 조건문을 만드는 것 이다.
- 삼항연산자를 중첩해서 사용하기 보단, `if` 문을 사용하는 것이 더 효율적이다.

```javascript
const hansome = true;

const value = hansome == true ? "나는 잘생겼다~" : "나는 못생겼다~";
console.log(value);
```

- 이런식으로 코드를 작성하면 `hansome` 의 값이 `true` 이므로 `나는 잘생겼다~` 가 출력된다.

# Truthy & Falsy🌼

- Falsy의 값에는 `undefined` , `null` , `0` , `비어있는 문자열` ,`NaN` 이 있다.

# 단축 평가 논리 계산법🌼

```javascript
// &&
console.log(true && 'true값이 아니므로 이 문장이 출력됩니다.');

// ||
console.log(false || 'false값이므로 이 문장을 출력합니다.');
```
- 이런 식으로 단축 평가 논리 계산법에서 `&&` 은 앞의 것이 `true` 면 `true` 를 출력하고, 아니면 뒤의 것을 출력한다. 그러나 `||` 은 앞의 것이 `false` 면 뒤의 것을 출력한다.

# 함수의 기본 파라미터🌼

```javascript
const MyHeight = (height) => {
    return height;
}

const result = MyHeight(180);
console.log(result);
```
- 만약 위의 코드처럼 작성을 하면 `180` 이라는 값이 출력 될 것이다. 그러나 여기서 만약 파라미터를 안 써주고 기본적으로 지정을 해주려면 어떤 식으로 해야할까?

```javascript
const MyHeight = (height = 180) => {
    return height;
}

const result = MyHeight();
console.log(result);
```
- 이런 식으로 함수안의 파라미터에 미리 값을 넣어주면 된다.

# 조건문 더 스마트하게 쓰기🌼
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
- 이런식의 가독성이 떨어지는 코드를 더 가독성 있게 바꿀 수 있다.

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