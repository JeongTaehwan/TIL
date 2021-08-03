# React로 API 연동하기 🐱‍🐉

## 설치 🐱‍🐉
> 먼저 API 호출을 위한 `axios` 라이브러리를 설치한다

```
$ cd api-integrate
$ yarn add axios
```
---

## axios를 사용하여 할 수 있는 것 🐱‍🐉
> `axios`를 사용하여 `GET, PUT, POST, DELETE` 등의 메서드로 API 요청을 할 수 있다.

- **GET**: 데이터 조회
- **POST**: 데이터 등록
- **PUT**: 데이터 수정
- **DELETE**: 데이터 제거
---

## axios 사용법 🐱‍🐉

```javascript
import axios from 'axios';

axios.get('/users/1');
```
> get이 위치한 자리에는 메서드 이름을 소문자로 넣는다. 예를 들어서 새로운 데이터를 등록하고 싶다면 `axios.post()` 를 사용하면 된다. 

> 그리고 파라미터에는 API의 주소를 넣는다.
```javascript
axios.post('/users'. {
    username: 'tapuwan',
    name: 'taehwan'
});
```
> `axios.post()` 로 데이터를 등록할 떄에는 두번째 파라미터에 등록하고자 하는 정보를 넣을 수 있다.

---

## 마무리 🐱‍🐉

> React에서의 API 연동은 다음과 같은 `Hooks`와 함께 사용 할 수 있다.
- useState
- useEffect
- useReducer
- useAsync 커스텀 Hook
> 위와 같은 `Hooks` 말고도 `react-async` , `Context API` 와도 사용할 수 있다.

--- 

**피드백은 언제나 환영입니다! 😇**   
**오타나 코드에 오류가 있으면 issue를 남겨주세요! 😁**   
**출처 : 패스트캠퍼스 강의 - 벨로퍼트와 함께하는 API 연동하기**