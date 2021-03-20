# JavaScript👨‍💻

### 자바스크립트란?👨‍💻
- 자바스크립트는 ‘웹페이지에 생동감을 불어넣기 위해’ 만들어진 프로그래밍 언어입니다.
자바스크립트로 작성한 프로그램을 스크립트(script) 라고 부릅니다. 스크립트는 웹페이지의 HTML 안에 작성할 수 있는데, 웹페이지를 불러올 때 스크립트가 자동으로 실행됩니다.
스크립트는 특별한 준비나 컴파일 없이 보통의 문자 형태로 작성할 수 있고, 실행도 할 수 있습니다.

### 자바스크립트는 왜 쓰나요?👨‍💻
- 웹사이트를 더 동적으로 만들기 위해
- 사용자의 행동에 반응 할 수 있기 떄문
- 새로운 HTML 태그를 추가할 수 있기 때문   
- 등등...

# 변수선언👨‍💻
- JavaScript에서의 변수 선언은 ```let``` , ```var``` , ```const```가 있다.   
```let```과 ```var```은 변수로 선언을 한 후 값을 바꾸어도 문제없이 출력이 된다.
```javascript
let a = 'Hello World!🐬';
var b = 'Hello World!🐬';
const c = 'Hello World!🐬';

console.log(a);
console.log(b);
console.log(c);
```

```javascript
let a = 'Hello World!🐬';
a = 'Puwan is Hansome😎';

console.log(a);
```
- 이런식으로 코드를 작성할 시 마지막으로 값을 지정해준 ```'Puwan is Hansome'```이 출력 되어진다.

```javascript
const a = 'Puwan is ugly🤢';
a = 'It is a lie😥';

console.log(a);
```
- 허나 이런식으로 코드를 작성하면 ```const```는 값을 변경할 수 없기 떄문에 오류가 뜬다.

# 연산자👨‍💻
 ## NOT
 - 값을 그 값의 반대값으로 변환해줌. 코드로 표시할땐 ```!```로 표시함.
```javascript
let a = !true;
console.log(a);
```
-  이런식으로 코드를 작성하면 ```true```의 ```NOT```값이므로 반대 값인 ```false```를 출력하게 된다.
 ## AND
 - 두 값이 모두 ```true```값이 나와야 ```true```를 출력함. 코드로 표시할땐 ```&&```로 표시함.

 ```javascript
 let a = true && true;
 console.log(a);
 ```
 - 이렇게 작성하면 값은 ```true```가 나온다.

 ## OR
 - 두 값중 하나라도 ```true```값이 나오면 ```true```가 출력됨. 코드로 표시할땐 ```||```로 표시함.

 ```javascript
 let a = true || false;
 console.log(a);
 ```
 - 이렇게 작성하면 값은 ```true```가 나온다.

# 조건문👨‍💻
- 조건이 ```true```값일때 지정한 값을 출력해주는 문법
 ## if, else if, else
 ```javascript
 let a = 2;
 
 if(a - 1 == 0) {
     console.log('True!');
 } else if(a - 2 == 0) {
     console.log('Second True!');
 } else {
     console.log('Error!');
 }
 ```
 - 이런식으로 코드를 작성하면 조건인 ```a - 2 == 0```이 ```true```값이므로 ```'True2'```가 출력된다. 문법의 처음에 나오는 ```if```의 조건이 일치하지 않으므로 ```else if```로 넘어가 조건을 확인한다. 만약 ```if```와 ```else if```의 조건이 다 ```true```가 아니면 마지막으로 ```else```의 값이 나오게 된다.

 ## switch case

 ```javascript
 let sports = 'soccer';

 switch(sports) {
     case 'soccer':
         console.log('손흥민');
         break;
     case 'baseball':
         console.log('추신수');
         break;
     case 'ssirum':
         console.log('강호동');
         break;
 }
 ```
 - 이런식으로 코드를 작성하면 괄호안에 있는 ```sports```의 값에 따라 조건문의 출력값이 달라진다. 여기선 ```sports``` 변수안에 ```'soccer'```이라는 문자열이 선언되어있으므로 ```case 'soccer':```코드의 값이 출력되 '손흥민'이라는 값이 나오게 된다.

 - ```switch case```문에서 ```break```를 선언하지 않으면 다음 case의 값까지 출력이 된다. 위의 코드로 예를 들면 ```'추신수'```를 출력한 후 ```break```를 안하면 다음 케이스의 값인 ```'강호동'```까지 출력되게 된다.

# 함수👨‍💻
- 특정코드를 하나의 명령어로 실행하게 해주는 기능
- 파라미터가 주어졌을때 결과를 만들어 낼 수 있음
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
## Fuction Template Literal