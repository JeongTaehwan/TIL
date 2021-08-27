# Recoil 🛁

## 설명 
> `Recoil` 은 `React` 를 위한 상태 관리 라이브러리이다.

## 주요개념 

**Atoms** 
> `Atoms` 는 상태의 단위이며, 업데이트와 구독이 가능하다. `Atoms` 는 `React` 의 로컬 컴포넌트의 상태 대신 사용할 수 있다.

```javascript
const fontSizeState = atom({
  key: 'fontSizeState',
  default: 14,
});
```
> `Atoms` 는 위의 코드같이 `atom` 함수를 사용해 생성한다.

> 컴포넌트에서 `Atoms` 를 읽고 쓰려면 `useRecoilState` 라는 훅을 사용한다.

```javascript
const [fontSize, setFontSize] = useRecoilState(fontSizeState);
```

**Selector** 
> `Selector` 는 `atoms` 나 다른 `selector` 를 입력으로 받아들이는 순수 함수(pure function)이다. 

> 컴포넌트의 관점에서 보면 `selectors` 와 `atoms` 는 동일한 인터페이스를 가지므로 서로 대체할 수 있다.

```javascript
const fontSizeLabelState = selector({
  key: 'fontSizeLabelState',
  get: ({get}) => {
    const fontSize = get(fontSizeState);
    const unit = 'px';

    return `${fontSize}${unit}`;
  },
});
```
> `Selector` 는 위의 코드같이 `selector` 함수를 사용해 생성한다.

> `get` 속성은 계산될 함수다. 전달되는 `get` 인자를 통해 `atoms` 와 다른 `selectors` 에 접근할 수 있다.

---

**출처 : Recoil 공식문서**