# Next 🌂

## 설명

**Next란?**
> `React` 의 프레임워크로, `React` 에서 [SSR](../Basic/ssrandcsr.md)을 쉽게 구현할 수 있게 해주는 간단한 프레임워크이다.

**설치하기**
> 아래의 코드를 터미널에 입력하여 Next 앱을 생성한다.

```
npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn-starter/tree/master/learn-starter"
```
> 포트 3000에서 개발 서버가 시작된다.

---

## Link
> 웹페이지에서 페이지 사이를 연결할 때 `<a>` HTML 태그를 사용한다. Next에서는 Link 컴포넌트를 사용한다. `<Link>`

**사용하는 법** 
> 코드의 맨 윗줄에 다음 코드를 작성한다.

```javascript
import Link from 'next/link'
```
> 그리고 태그를 작성해준다.

```javascript
<h1>
  Read{' '}
  <Link href="이동할 페이지 주소">
    <a>this page!</a>
  </Link>
</h1>
```

> `{' '} 여러 줄에 걸쳐 텍스트를 나누는 데 사용되는 빈 공간을 추가한다.

---

## Image
> `Next`에서 `Image` 태그는 이미지 크기 조정 및 최적화를 담당한다. 다음의 방식으로 불러올 수 있다.
```javascript
import Image from 'next/image'
```

> 코드는 다음의 형태로 작성할 수 있다.
```javascript
const YourComponent = () => (
  <Image
    src="/images/profile.jpg" // 불러올 파일의 루트
    height={144}
    width={144} 
    alt="Your Name"
  />
)
```

---

## Head 
> `Head` 태그는 `title`과 같은 HTML 메타데이터를 처리할 때 사용한다. 다음의 코드로 불러와 사용한다.
```javascript
import Head from 'next/head'
```

>다음의 코드처럼 사용할 수 있다.
```javascript
export default function FirstPost() {
  return (
      <Head>
        <title>First Post</title>
      </Head>
  )
}
```

---

**출처 : Next 공식 문서**