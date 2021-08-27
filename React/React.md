# React 🤡

## 설명

**React란?** 
> React는 웹 프레임워크로, 자바스크립트 라이브러리의 하나로서 사용자 인터페이스를 만들기 위해 사용된다. React는 facebook에서 제공하는 프론트엔드 라이브러리라고 볼 수 있다.

**왜 React?** 
> React를 사용하지 않아도, html과 css, javascript를 이용해서 웹 페이지를 만들 수 있지만, React를 이용해 사용자와 상호작용할 수 있는 동적인 UI를 쉽게 만들 수 있기 때문이다.

**React의 특징** 
- Date Flow
- Component 기반 구조
- Virtual Dom
- Props and State
- JSX

---

## Component 
> Component란 React로 만들어진 앱을 이루는 최소한의 단위를 뜻한다. React에서의 가장 중요한 요소이다.

```javascript
import React from 'react';

function App() {
  return <div>안녕하세요</div>
}

export default App;
``` 
> 컴포넌트를 만들 땐 `import React from 'react';` 를 통해 불러와야한다.  코드의 맨 아래엔 `export default App` 이런식으로 컴포넌트를 내보내주어야한다.  

## Hook
> `Hook` 이란 React 16.8에서 새롭게 추가된 개념이다. `Hook`을 통해 `class`를 작성하지 않고도 `state` 와 같은 `React` 기능들을 사용할 수 있다.   

**useState**
```javascript
const [state, setState] = useState(initialState);
```
> `useState` 는 상태 유지 값과 그 값을 갱신하는 함수를 반환한다. `setState` 는 `state` 를 갱신할 때 사용한다. 새 `state` 값을 받아 컴포넌트 리렌더링을 큐에 등록한다.

> 최초로 렌더링을 할 때, 반환된 `state` 는 첫 번째 전달된 인자(`initialState`)의 값과 같다. 

**useEffect**
```javascript
useEffect(didUpdate)
```
> `useEffect` 는 명령형 또는 어떤 `effect` 를 발생하는 함수를 인자로 받는다. 

> 기본적으로 동작은 모든 렌더링이 완료된 후에 수행되지만, 어떤 값이 변경되었을 때만 실행되게 할 수도 있다.

**useContext**
```javascript
const value = useContext(MyContext);
```
> `useContext` 는 `context` 객체를 받아 그 `context` 의 현재 값을 반환합니다. 

> `context` 의 현재 값은 트리 안에서 이 `Hook` 을 호출하는 컴포넌트에 가장 가까이에 있는 `<MyContext.Provider>`의 `value` prop에 의해 결정된다.

> useContext로 전달한 인자는 context 객체 그 자체이여야 함을 잊으면 안된다.

- 맞는 사용: useContext(MyContext)
- 틀린 사용: useContext(MyContext.Consumer)
- 틀린 사용: useContext(MyContext.Provider)
---

**출처 : React 공식 문서**