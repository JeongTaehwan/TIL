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

# Hooks
- Hooks란 React 버전 16.8부터 React 요소로 새로 추가되었고 Hook을 이용하여 기존 Class 바탕의 코드를 작성할 필요 없이 상태 값과 여러 React의 기능을 사용할 수 있다

## useState
- `useState` 는 컴포넌트의 동적인 상태를 관리할 때 사용된다.
## useRef
- `useRef` 는 특정 `DOM` 을 직접 선택할 때 사용된다.
- 조회나 수정이 가능하 변수를 관리할 때 사용된다.
## useEffect
- `useEffect` 는 컴포넌트가 `Mount` , `UnMount` , `Update` 될때 특정 작업을 처리할 때 사용된다.
## useMemo
- `useMemo` 는 성능 최적화를 위해 연산된 값을 재사용할때 사용한다.
## useCallback
- `useCallback` 은 `useMemo` 와 비슷하다. 
- `useMemo` 는 특정결과 값을 재사용하지만, `useCallback` 은 특정함수를 새로 만들지 않고 재사용할때 사용한다.
## useReducer
- `useReducer` 는 컴포넌트의 상태 업데이트 로직을 컴포넌트에서 분리할 때 사용한다.