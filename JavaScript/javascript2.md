# JavaScript 유용한 문법🌼

# 삼항연산자

- `?` 와 `:` 를 사용하여 조건문을 만드는 것 이다.
- 삼항연산자를 중첩해서 사용하기 보단, `if` 문을 사용하는 것이 더 효율적이다.

```javascript
const hansome = true;

const value = hansome == true ? "나는 잘생겼다~" : "나는 못생겼다~";
console.log(value);
```

- 이런식으로 코드를 작성하면 `hansome` 의 값이 `true` 이므로 `나는 잘생겼다~` 가 출력된다.

# Truthy & Falsy

- Truthy 와 Falsy는 코드보단 설명으로 하는게 이해가 더 잘되는 것 같다.
- Falsy의 값에는 `undefined` , `null` , `0` , `비어있는 문자열` ,`NaN` 이 있다.
