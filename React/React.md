# React🤡

### React란?
- React는 웹 프레임워크로, 자바스크립트 라이브러리의 하나로서 사용자 인터페이스를 만들기 위해 사용된다. React는 facebook에서 제공하는 프론트엔드 라이브러리라고 볼 수 있다.

### React는 왜 쓰나요?
- react를 사용하지 않아도, html과 css, javascript를 이용해서 웹 페이지를 만들 수 있지만, react를 이용해 사용자와 상호작용할 수 있는 동적인 UI를 쉽게 만들 수 있기 때문이다.

### React의 특징
- Date Flow
- Component 기반 구조
- Virtual DOm
- Props and State
- JSX

# Component
- Component란 React로 만들어진 앱을 이루는 최소한의 단위를 뜻한다. React에서의 가장 중요한 요소이다.

```javascript
import React from 'react';

function App() {
  return <div>안녕하세요</div>
}

export default App;
```
- 이런식으로 리액트 컴포넌트를 만든다. 
- 컴포넌트를 만들 땐 ```import React from 'react';``` 를 통해 불러와야한다.
- 코드의 맨 아래엔 ```export default App``` 이런식으로 컴포넌트를 내보내주어야한다.