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
import Link from "next/link";
```

> 그리고 태그를 작성해준다.

```javascript
<h1>
  Read{" "}
  <Link href="이동할 페이지 주소">
    <a>this page!</a>
  </Link>
</h1>
```

> `{' '} 여러 줄에 걸쳐 텍스트를 나누는 데 사용되는 빈 공간을 추가한다.

**추가**

- 외부링크에 연결해야 하는 경우 `Link` 대신 `a` 태그를 사용한다.
- `className`등을 사용할 땐 `Link` 가 아닌 태그에 사용해야 한다.
- `Next.js`는 `next/link` 가 있는 페이지에선 연결된 페이지를 자동 프리패치해준다.  
  👉 예시) 개발자도구를 키고 `html` 태그에 `background-color` 를 적용시키면 Link로 연결된 페이지도 `background-color` 값이 바뀐걸 알 수 있다.

---

## Image

> `Next`에서 `Image` 태그는 이미지 크기 조정 및 최적화를 담당한다. 다음의 방식으로 불러올 수 있다.

```javascript
import Image from "next/image";
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
);
```

---

## Head

> `Head` 태그는 `title`과 같은 HTML 메타데이터를 처리할 때 사용한다. 다음의 코드로 불러와 사용한다.

```javascript
import Head from "next/head";
```

> 다음의 코드처럼 사용할 수 있다.

```javascript
export default function FirstPost() {
  return (
    <Head>
      <title>First Post</title>
    </Head>
  );
}
```

---

## getStaticProps & getServerSideProps란 ?

**getStaticProps**

> 정적 페이지 생성(SSG) 시 활용하는 메서드이다. 해당 메서드는 번들링(빌드) 단계에서 데이터 패칭이 이루어진다.

```javascript
export async function getStaticProps(context) {
  return (
    props: {}, // Page Component의 Props로 전달되는 객체
  )
}
```

**getStaticProps는 언제 써야 할까?**

- 변하지 않는 공개적인 캐시 데이터를 가져올 필요가 있을 떄
- SEO를 필요로 하는 웹사이트이며 CDN 서버에 정적 페이지 배포가 필요할 때

**getServerSideProps**

> 서버 사이드 렌더링(SSR) 시 활용하는 메서드이다. 해당 메서드는 런타임 환경에서 페이지에 접근 시 서버 측에서 실행된다.

```javascript
export async function getServerSideProps(context) {
  return (
    props: {}, // Page Component의 Props로 전달되는 객체
  )
}
```

**getServerSideProps는 언제 써야 할까?**

- 미리 외부로 부터 데이터를 요청하여 페이지에 렌더링이 필요한 경우에 사용한다.
- 단, `getServerSideProps` 는 페이지 컴포넌트에 접근할 때마다 서버에서 항상 실행되기 때문에 `getStaticProps` 보다 속도가 느리고 추가 구성 없이는 결과 데이터를 캐싱할 수 없다.
- 데이터를 미리 렌더링 할 필요가 없는 경우 클라이언트 측에서 데이터를 패칭하는 것이 더 효율적이다.
