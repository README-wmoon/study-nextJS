# **코리아 IT 아카데미**
## NextJS 수업정리

### 리액트에서 라우팅(경로에 따라서 알맞은 페이지를 보여주는 방법)
1. react-router-dom 라이브러리 
2. next.js 프레임워크 를 사용하는 방법

### next js 
- 리액트를 활용하여 만든 프레임워크
- 라우팅까지 자동으로 될 수 있도록 함

### 리액트
```
SPA + CSR(Client Side Rendering)
html파일은 하나밖에 없기 때문에 페이지 별 서로 다른 
meta 태그를 설정할 수 없고, 
검색 했을 때 노출이 쉽게 되지 않는 단점이 존재(SEO에 불리하다)
```

### 넥스트js 
- 기존 react + 라우팅기능 + SSR(Server Side Rendering) 
- SEO에 최적화가 가능, 라우팅도 쉽게 다룰 수 있다 <br>
- app 폴더 내의 layout.js가 그려지고, <br>
비어있는 body태그 안에 page.js 에서 export default 되고 있는 컴포넌트가 그려진다
```
app 폴더 내에 다른 폴더를 만들고, 
그 폴더 안에 page.js 를 만들면 자동으로 라우팅 처리가 된다 
http://localhost:3000/abc 
  입력을 하면 
app/abc/page.js 파일에서 export default 되고있는 컴포넌트가 layout의 body 안쪽에 
그려진다 
```

### 라이브러리
1. 라이브러리 bsy 를 설치하고 싶다
```
npm 
  npm install bsy
yarn 
  yarn add bsy 
```
2. 라이브러리 bsy를 삭제하고 싶다 
```
npm 
  npm uninstall bsy

yarn 
  yarn remove bsy 
```
3. node-modules 폴더가 없어서 설치하고 싶다
```
npm 
  npm install
    --> package.json에 dependencies를 보고 거기 있는 라이브러리를 모두 설치

yarn 
  yarn install 
    --> package.json에 dependencies를 보고 거기 있는 라이브러리를 모두 설치
```

※yarn은 npm을 통해서 설치해야한다 
```
npm install yarn --> 로컬영역에서만 설치 
npm install --global yarn --> 전체 영역에서 yarn을 사용하겠다
```

## nextjs 기본 프로젝트 구조 설치
### npm 
```
npx create-next-app 
  npm 5.2버전 부터 npx를제공, 기존방식은 npm을 통해 사용할 모듈을 
  지역 공간에 설치를 해야만 실행시킬수 있었는데, 
  모듈을 설치하지 않고도 매번 최신 버전 파일만 불러와서 실행시키고, 
  그 파일은 사라지는 방식으로 사용할 수 있도록 npx가 제공된다 .
```

### yarn
```
yarn create next-app
```

### 넥스트js 프로젝트 서버 실행
```
npm 
  npm run dev 
yarn 
  yarn run dev 
  혹은 
  yarn dev 
```

### test 리액트 프로젝트 
- 간단한 구조로 연습
- +npm으로 설치

### dashboard 넥스트 프로젝트 
적용, yarn 으로 설치

### 포트번호
실행되고있는 컴퓨터의 프로그램을 식별하기 위해 사용하는 번호
```
localhost = 127.0.0.1
localhost:3000 --> 127.0.0.1:3000 --> 컴퓨터주소:3000

카카오톡, zoom, 필기프로그램, vscode .....
8080 포트에서 data base 프로그램 

기본적으로 react 프로젝트나 nextjs 프로젝트는 3000번에서 동작하도록 설정 
하나의 포트에서는 하나의 프로그램 
```

### react를 기본 포트인 3000번이 아닌 다른 포트에서 동작시키기
```
package.json에서 
  scripts 부분에 
  mac, linux 
    "start" : "export PORT=포트번호 && react-scripts start"
  window 
    "start" : "set PORT=포트번호 && react-scripts start"
```
- npm start를 통해 react 프로젝트를 실행하면 <br> 
  설정된 포트에서 실행이 된다 

### 리액트 프로젝트 
```
npm start
yarn start
```

### 넥스트 프로젝트
```
yarn dev 
npm run dev 
```

## css 문법
### 선택자
```
div:hover{
  color:red;
} 

※ 가상클래스 
:root {
  //html태그에 적용하고 싶은
  // 대상이 있을 때 사용
}
```

### css에서 변수
```
글자색 
a =  #000000
b = #ffffff 

h1{
  color:a;
}

h2{
  color:a;
}

.detail{
  color:a;
}

.content{
  background-color:b
}
```

### css에서 변수 만들기
```
--변수이름 : 값;
--변수이름 : 값;
--a : #000000;
--b : 0, 0, 0;
--c : 3px solid black;
--d : 배상엽;
```

### css에서 변수 사용하기 
var(--변수이름)
```
div{
  color : var(--a);
  border : var(--c);
  display: var(--d);

  background-color : rgb(0, 0, 0);
  background-color : rgba(var(--b), 0.5);
}
```

## react vs nextJS 차이점
### react
1. index.html 을 화면에 렌더링을 한다 <br>
  (id가 root인 비어있는 div태그가 그려진다)
2. index.js 가 <br>
  id가 root인 div태그를 찾아서 그 속에다가 <br>
  <App/>을 그려준다 
3. App.js 안에있는 App 컴포넌트가 그려진다(비어있는 div 안쪽에)

### next js
1. app폴더 안에있는 layout.js 가 그려진다 <br>
  html태그와 body태그 를 그려줌 
2. body태그 안쪽에는 app폴더 안에있는 page.js 가 그려진다
- app 폴더 안에 또다른 폴더를 만들고, 그 폴더 안에 page.js 를 만들면 <br>
  자동으로 라우팅이 된다
```
ex) 
  app/test/page.js 
  
  const AAA = ()=>{
    return (<h1>안녕</h1>);
  }
  export default AAA;

  경로 : localhost:3000/test 
  --> 
  app/layout.js 가 그려진다 
  <html>
    <body>
      
    </body>
  </html>

  app/test/page.js 가 body태그 안쪽에 그려진다
  <html>
    <body>
      <h1>안녕</h1>
    </body>
  </html> 
```

### react 18버전 업데이트된 내용
react로 server side rendering이 가능 해짐

### Client Side Rendering(CSR)
서버로부터 필요한 데이터만 받아오고 <br>
받아온 데이터를 브라우저가 javascript를 실행함으로써 <br>
직접 html 파일을 만드는 것

### Server Side Rendering(SSR)
서버에서 완성된 html을 받아오고 <br>
브라우저는 단순히 받아논 html 파일을 <br>
보여주는 것

## 컴포넌트
### react
```
리액트는 기본적으로 모든 컴포넌트가 
CSR으로 동작 하도록 만들어져 있다 
  --> 18버전이 되며 SSR 방식으로 동작하는 컴포넌트 업데이트 
  (여전히 기본적으로 컴포넌트를 만들면 Client 컴포넌트로 만들어짐)

nextjs 13버전 업데이트가 되면서 리액트의 서버컴포넌트를 적극적으로 도입했고,
nextjs에서 만드는 기본 컴포넌트는 모두 서버 컴포넌트로 만들어 진다 

순수 react에서 내가 만든 컴포넌트는 클라이언트 컴포넌트이고, 
서버 컴포넌트로 사용하고 싶으면 추가적인 코드를 작성 

next에서 기본으로 만든 컴포넌트는 서버 컴포넌트이고 
클라이언트 컴포넌트로 사용하고 싶으면 추가적인 코드를 작성 

emotion 과 같은 라이브러리는 클라이언트 컴포넌트에서 동작하도록 만들어놓았다

next에서 만든 컴포넌트를 서버컴포넌트가 아닌 클라이언트 컴포넌트로 
동작하게 만드는 방법 
파일 맨 위에다 
'use client'
를 추가한다 
```

### nextJS
```
next js 컴포넌트를 만들 때 항상 맨위에 
'use client' 를 작성하여 
react의 클라이언트 컴포넌트를 사용해서 공부

image 다루기 
이미지는 public 폴더 안에 넣어 놓는다 
이미지를 사용할 때는 
next/image 에서 Image 컴포넌트를 사용해야 한다


<Image width={100} height={100} src={이미지경로} alt={대체텍스트} />
이때 이미지 경로는 
'/' 부터 시작을 하는데, 그 이유는 
기본 경로가 public폴더로 설정되어있기 때문이다 

'/tmp.jpg'; --> public/tmp.jpg 
'/a/b/c.png'; --> public/a/b/c.png 

mui icon 
  아이콘을 무료로 사용할 수 있도록 제공해주는 
  라이브러리 
```

### 문법
```
next js에서 사용하는 문법은 모두 리액트의 문법이다 
("use client", <Image/> 만 빼고)
따라서 리액트에서 그대로 사용하면 된다 
리액트에서 이미지는 기본 html <img/> 사용
next에서 이미지는 <Image/> 를 사용한다 

리액트에서 css파일이 여러개라고 하더라도 
모두 통합되어 적용되기 때문에 웬만하면 리액트 css파일은
index.css 하나만 사용한다 
```

### next js 이미지
```
public 폴더에 있는 이미지 --> '/a.png' --> public/a.png
<Image src="" alt="" width={} height={}/>
```

### react js 이미지
```
public 폴더에 있는 이미지 --> '/a.png' --> public/a.png
<img src="" alt="" />
```

### props와 조건부 렌더링 
조건에 따라서 적용되어야 하는 css가 달라져야한다
```
emotion에서 
`
`
안에는 css의 속성을 작성하고, 이것이 css로 반영이 되는데, 
만일 `` 안에 ${} 이 부분에 함수를 넣어주면 
해당 함수의 return되는 값이 ${} 자리에 쓰여있다고 판단한다

ex)
const Title = styled.h1`
  color:r${()=>{return 'aaa'}}ed;
`;

const Title = styled.h1`
  color:raaaed;
`;

이때 해당 함수의 매개변수에는 props(속성들)이 객체로 담겨서 전달이 된다

<Title a='ddd' b='ccc'>abc</Title>

{
  a:'ddd',
  b:'ccc',
  children:'abc',
  theme:{}
}
--> 매개변수에 들어있는 속성 값에 따라서 return되는 값을 다르게 해주면 
css가 다르게 적용되는 컴포넌트가 만들어진다 

${} 안에 있는 함수가 객체가 return되는 경우에는 해당 객체를 
css로 해석하여 적용 시켜준다 
```

### hover
- 자기자신 안에있는 p태그 
- 자기자신이 hover가 된다면
