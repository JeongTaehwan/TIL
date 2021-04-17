## Scss 컴파일방법

```
npm init -y //package.json 생성
npm i -D parcel-bundler // parcel-bundler 설치
npx parcel "실행할 파일" // 실행
```

## Scss의 데이터 종류

- `Number`: 숫자
- `Strings`: 문자
- `Colors`: 색상 표현
- `Booleans`: 논리
- `Nulls`: 아무것도 없음
- `Lists`: 공백이나 , 로 구분된 값의 목록 | ex) `(apple, orange, banana)`
- `Maps`: `Lists`와 유사하나 값이 `Key: Value` 형태 | `ex) (apple: a, orange: o, banana: b)`

## 데이터 종류의 특이사항

- `Number`: 숫자에 단위가 있거나 없습니다.
- `Strings`: 문자에 따옴표가 있거나 없습니다.
- `Nulls`: 속성값으로 `null`이 사용되면 컴파일하지 않습니다.
- `Lists`: `()`를 붙이거나 붙이지 않습니다.
- `Map`: `()`를 꼭 붙여야 합니다.

## 상위 선택자 참조 (Ampersand)

- `&`를 사용함
- `&`는 바로 윗단계의 선택자를 참조함

```scss
.btn {
  position: absolute;
  &.active {
    color: red;
  }
}

.list {
  li {
    &:last-child {
      margin-right: 0;
    }
  }
}
```

## @at-root (중첩 벗어나기)

- `@at-root`를 사용
- ex) 변수를 선언하고 중괄호 밖에선 사용을 못하니 안쪽에서 사용을 해야하는데 중첩은 되면 안될때

```scss
.list {
  $w: 100px;
  $h: 50px;
  li {
    width: $w;
    height: $h;
  }
  @at-root .box {
    width: $w;
    height: $h;
  }
}
```

## 중첩된 속성

- ex) `css`에선 `margin-...` 등으로 사용헀다면 `Scss`에선 `margin` 안에 `top, bottom` 등등을 사용할 수 있음

```scss
.box {
  font: {
    weight: bold;
    size: 10px;
    family: sans-serif;
  }
  margin: {
    top: 10px;
    left: 20px;
  }
  padding: {
    bottom: 40px;
    right: 30px;
  }
}
```

## 변수

- `$`로 시작함
- `$변수이름: 속성값;` <- 이런식으로 작성함

```scss
$color-primary: #e96900;
$url-images: "/assets/images/";
$w: 200px;

.box {
  width: $w;
  margin-left: $w;
  background: $color-primary url($url-images + "bg.jpg");
}
```

## 변수 - 2

- 변수의 유효범위는 선언된 블록 `{}` 안에서만 사용 가능하다
- 변수의 유효범위는 선언된 블록 `{}` 안에서만 사용 가능하다

```scss
.box1 {
  $color: #111;
  background: $color;
}
// 에러발생
.box2 {
  background: $color;
}
```

## 변수 재 할당

- 변수를 선언하고 또 다른 변수에 변수를 넣을 수 있다.

```scss
$red: #ff0000;
$blue: #0000ff;

$color-primary: $blue;
$color-danger: $red;

.box {
  color: $color-primary;
  background: $color-danger;
}
```

## 전역설정 (!global)

- `!global` 키워드를 사용함
- 박스 안에서 선언한 변수를 바깥에서도 사용할 수 있음

```scss
.box1 {
  $color: #111 !global;
  background: $color;
}
.box2 {
  background: $color;
}
```

## 기본값 설정

- `!default` 키워드를 사용함
- 변수와 값을 선언하되 기본 변수값이 있으면 현재 설정한 값은 사용하지 않음

```scss
$color-primary: red;

.box {
  $color-primary: blue !default;
  background: $color-primary;
}
```

## 문자보간

- `#{}`를 사용함
- `#{}`를 이용하여 코드 어디서든 변수 값을 넣을 수 있음

```scss
$family: unquote("Droid+Sans");
@import url("http://fonts.googleapis.com/css?family=#{$family}");
```

## 가져오기

- `@import` 키워드를 사용함
- 외부에서 가져온 Sass파일들은 모두 CSS 출력 파일로 병합됨
- `@import "경로";`로 사용함

```scss
@import "hello.css";
@import "http://hello.com/hello";
@import url(hello);
@import "hello" screen;
```

- Sass `@import`는 기본적으로 Sass 파일을 가져오는데, CSS `@import`규칙으로 컴파일되는 몇 가지 상황이 있음.

```
1. 파일 확장자가 .css일때
2. 파일 이름이 http://로 시작하는 경우
3. url()이 붙었을 경우
4. 미디어쿼리가 있는 경우
```

## 연산

- 산술 연산자
  - `+` 더하기
  - `-` 빼기
  - `*` 곱하기 (하나 이상의 값이 반드시 숫자(Number))
  - `/` 나누기 (오른쪽의 값이 반드시 숫자(Number))
  - `&` 나머지
- 비교 연산자
  - `==` 동등
  - `!=` 부등
  - `<` 대소 / 보다 작은
  - `>` 대소 / 보다 큰
  - `<=` 대소 및 동등 / 보다 작거나 같은
  - `>=` 대소 및 동등 / 보다 크거나 같은
- 논리(불린, Boolean) 연산자
  - `and` 그리고
  ```scss
  $width: 90px;
  div {
    @if ($width < 100px and $width = 90px) {
      height: 300px;
    }
  }
  ```
  - `or` 또는
  ```scss
  $width: 90px;
  div {
    @if ($width > 100px or $width > 30px) {
      height: 300px;
    }
  }
  ```
  - `not` 부정
  ```scss
  $width: 90px;
  div {
    @if not($width > 100px) {
      height: 300px;
    }
  }
  ```
- 문자 연산
  - 기본적으로 `+`를 사용함
  - 첫번째 피연산자에 따옴표가 붙어있으면 연산결과도 따옴표가 붙어있고, 그렇지 않으면 그대로 나옴
- 색상 연산
  - 색상 또한 연산할 수 있음
  - 그러나 `rgba` 의 `a` 값은 두 연산하는 값이 일치해야함
  - `rgba` 의 `a`값을 연산하기 위해 `opacify()`와 `transparentize()`함수를 사용하여 연산할 수 있음

```scss
div {
  color: #123456 + #345678;
  // R: 12 + 34 = 46
  // G: 34 + 56 = 8a
  // B: 56 + 78 = ce
  background: rgba(50, 100, 150, 0.5) + rgba(10, 20, 30, 0.5);
  // R: 50 + 10 = 60
  // G: 100 + 20 = 120
  // B: 150 + 30 = 180
  // A: Alpha channels must be equal
}
```

```scss
$color: rgba(10, 20, 30, 0.5);
div {
  color: opacify($color, 0.3); // 30% 더 불투명하게 / 0.5 + 0.3
  background-color: transparentize($color, 0.2); // 20% 더 투명하게 / 0.5 - 0.2
}
```

## 재활용 (Mixins)

- `Mixins`으로 자주 사용하는 코드를 따로 선언하여 사용할 수 있다.
- `Mixins` 를 선언하고 불러올땐 `@include`를 사용한다.
- `mixin`의 괄호안에 있는 것은 매개변수(Parameters)라고 부르고 `include`안에 있는 것은 인수(자) 라고 부른다
- 인수를 선언하지 않으면 매개변수안의 값이 기본 값으로 들어간다.

```scss
@mixin size($w: 100px, $h: 100px) {
  width: $w;
  height: $h;
}

.container {
  $change: 10px;
  .item {
    @include size(200px, 200px);
    background: tomato;
    @if ($change == 10px) {
      background: yellowgreen;
    }
  }
}
```

## 가변 인수

- 입력해야 할 인수가 불확실한 경우에 사용함
- 가변 인수는 매개변수 뒤에 `...`을 붙여서 사용함

```scss
@mixin bg($width, $height, $bg-values...) {
  width: $width;
  height: $height;
  background: $bg-values;
}

div {
  @include bg(
    100px,
    200px,
    url("/images/a.png") no-repeat 10px 20px,
    url("/images/b.png") no-repeat,
    url("/images/c.png")
  );
}
```

- 인수에도 가변 인수를 사용할 수 있음

```scss
@mixin font($style: normal, $weight: normal, $size: 16px, $family: sans-serif) {
  font: {
    style: $style;
    weight: $weight;
    size: $size;
    family: $family;
  }
}

a {
  // 매개변수 순서와 개수에 맞게 전달
  $font-values: italic, bold, 16px, sans-serif;
  @include font($font-values...);
}
```

## Content

- `mixin`에 스타일이 포함되 있으면 스타일을 `@contents`로 추가할 수 있음
- `@include`뒤에 중괄호를 열어 스타일을 추가해줌

```scss
@mixin icon($url) {
  &::after {
    content: $url;
    @content;
  }
}
.icon1 {
  @include icon("/images/icon.png");
}
.icon2 {
  @include icon("/images/icon.png") {
    position: absolute;
  }
}
```

## 확장

- `@extend 선택자` 키워드를 사용함
- 자바스크립트의 rest,spread와 비슷함
- 선택자 안의 값들을 가져옴

```scss
.btn {
  padding: 10px;
  margin: 10px;
  background: blue;
}
.btn-danger {
  @extend .btn;
  background: red;
}
```

- 확장을 추천하지 않는 이유
  - 내 선택자가 어디에 첨부될 것인가?
  - 원치 않는 부작용이 초래될수도 있음
  - 한 번의 확장으로 큰 css파일이 만들어 질 수 있음

## 함수

- `mixin`과 문법이 비슷함
- 함수는 값을 `@return` 키워드로 반환함
- 함수는 지시어가 없이 함수이름을 바로 사용함
- 함수이름은 내장함수와 겹치지 않게 지명해야함

```scss
@function columns($number: 1, $columns: 12, $width: 1200px) {
  @return $width * ($number/$columns);
}

.container {
  $width: 1200px;
  width: $width;
  .item:nth-child(1) {
    width: columns();
    height: 200px;
    background: red;
  }
  .item2:nth-child(2) {
    width: columns(8);
    height: 100px;
    background: blue;
  }
  .item3:nth-child(3) {
    width: columns(3);
    height: 50px;
    background: yellow;
  }
}
```
