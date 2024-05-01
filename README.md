# css 최적화

# js Syntax 1장

1. Syntax (구문) : 약속된 문법

2. Interpreter (번역 ) : 갤럭시 AI/웹브라우저

3. 프로그래밍은 요구사항을 분석하고, (개인별로 작성 : 의사코드 )
   Syntax 를 이용해서
   적절한 자료구조 + 적절한 함수를 활용하고,
   흐름을 제어하여 요구사항을 만족 시킨다.

# js Syntax 코드 위치

1. inline 방식

```html
<div class="wrap" onclick="alert('안녕');"></div>
```

2. 태그 방식

```html
<script>
  alert("반가워");
</script>
```

3. 외부파일 방식

```html
<script src="./js/script.js">
  alert("반가워"); // 실행안됨
</script>
```

# Swiper Slide 적용해 보기

- Slide 를 직접 코딩하지 마세요.
- 사용법을 배운다.
- Swiper(https://swiperjs.com/), Slick(https://kenwheeler.github.io/slick/), BxSlider(https://bxslider.com/) 가 있어요.

## 1. Swiper 슬라이드 적용시 주의 사항

- html 로드 완료 및 이미지 로드 완료 후 실행 권장.

```js
window.addEventListener("load", function () {
  // 실제 슬라이드 코드 배치하자.
});
```

# js 2장

```txt

  mp3  실행하려면? mp3 Player
  .hwp 실행하려면? 한글 Player

   javaScript 뭐지 ?


   publisher : 웹브라우저용 프로그래밍 언어 (html, css 다룬다)
   FE        : node.js (웹브라우저용 pg 아니고, pc 용 프로그래밍 언어)
               서버(dothome... db... html, css ...)

   웹 브라우저 player 마다 다 다르다.
   IE, Chrome, Opera, Safari..... (모두 다 다르다. Syntax )
   예) 메뉴하나를 만들어도 다시 각각에 웹브라우저에 맞게 마이그레이션을 해야.



   ES6

   렌더링 (목표는 html, css, js 로 문서 만들기)

    SSR (Server Side Redering)
     : php, spring (WAS), Next.js

    CSR (Client Side Redering) 이 있어요.
     : React, Vue, Angular ..

    Ajax (아작스, 에이젝스..) : 데이터(json) 통신
      : 비동기 (Request 요청  Response 회신) / 동기 구분
      : XML Http Request (XHR 통신)
      : vanila JS / pure JS (fetch/async await)     <=====>    jQuery (ajax)


      Node.js 하실 수 있나요?
       서버(Express.js), DB(MongoDB, MySql) 가능합니까?

      SPA : Single Page Application
      CBD : Component based Developement

      객체 지향
      : 모든 코드의 시작은 객체로 설계하여 전개한다.

      예) 기획자 : xls 로 제공한다.
          - 인터파크 상품(최상단 배치되는 제품의 정보를 노출)
          - 상품의 기본 정보
           : 할인율, 가격, 제목, 이미지 보여주면 되겠다.
           : 제품상세 정보로 이동하는 경로를 제공

          디자이너
          - UI 및 UX 배치

          BE 개발자
          - 제품의 정보를 DB 저장해둠. (일부만 Response )

          FE 개발자 :
          const Good = {
            ratio : 할인율,
            price : 가격,
            title : 제목,
            pic  : 이미지주소,
            link : 제품주소
          }

          const 객체명 = {
             속성명 : 속성값,
             기능   : function(){ 기능 }
          }


          Const TodoList = () => {
            const gogo = (e) => {
              alert ("클릭")
            }
            return (
               <>
                 <div className="a" onClick="gogo">
                   ~~~~
                  </div>
               </>
             )
          }


      프로토타입 기반 : 프로토타입(유전자)를 상속받아 덧댄다.

      Babel 이란 : 현재 최신 코드를 옛날 코드로 변환해 준다.


```

# Swiper Slide 적용해 보기 2.

- 데모사이트의 core 메뉴를 통해서 참조한다.
- 기본 css 와 js 파일은 CDN 으로 참조한다.

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css"
/>
<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
```

- 기본형 코드를 작성해서 원하는 영역에 배치한다.
- 슬라이드 개수 만큼 swiper-slide div 를 만든다.

```html
<div class="swiper 원하는이름">
  <div class="swiper-wrapper">
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
  </div>
</div>
```

- css 로 `원하는이름` 을 찾아서 width, height 를 100% 주자.
- css 로 `원하는이름` 에 절대로 display 등을 넣으면 안되요.

# Swiper Slide 적용해 보기 3.

- 외부 데이터 연동(json)
- 데이터의 구조를 설계
- json 이란 javaScript Object Notation 입니다.

```json
[
  { "키": 값, "키": 값, "키": 값 },
  { "id": 2, "pic": "b2.png", "url": "#" },
  { "id": 3, "pic": "b3.png", "url": "#" },
  { "id": 4, "pic": "b4.png", "url": "#" }
]
```

# Swiper Slide 적용해 보기 4.

- 비동기 호출하기(vanila/pure js)
  : BE 와 협업시 활용합니다.
- fetch 를 활용 가능
- async await 활용 가능

# js 3장

```txt
DOM(Document Object Model)
   - html 을 읽고, 수정 등등의 조작을 하는
     함수 (DOM API)
     document.querySelector(".wrap")

    클라이언트 사이드 API
    DOM, BOM, Canvas, XMLHttpRequest, fetch
    requestAnimationFrame, SVG, Web Storage,
    Web Component, Web Worker 등..

    Node.js   설치를 하면 자동으로
    npm 설치 됩니다. Node Package(js 소스) Manager
    https://www.npmjs.com/

    npm install 패키지명@버전
    node -v
    npm -v

    nvm (Node.js 의 버전을 자유롭게 변경하고, 설치)

    yarn install 패키지명@버전
```

# Swiper Slide 적용해 보기 5.

- 외부 js 파일을 이용한다.

```html
<script src="./js/파일명.js"></script>
```

```js
window.addEventListener("load", function () {
  //내용작성;
});
```

- swiper 에 보여줄 데이터를 외부 .json 파일로 연동한다.
  : 자료(데이터)를 만들어주는 동료가 BackEnd 입니다.
  : BE 와 협의가 필요하다. (협업의 기본)
  : 초기에는 가짜데이터(Dummy, Mockup) 을 가지고 작업

```json
[
  { "키명": "키값" },
  { "키명": "문자열" },
  { "키명": 55},
  { "키명": true},
  { "키명": []}
  { "키명": {} }
]
```

```json
[
  {
    "id": 1,
    "pic": "b1.png",
    "url": "#",
    "title": "AI 헬스케어의 <br/> 마일스톤을 찍다"
  },
  {
    "id": 2,
    "pic": "b2.png",
    "url": "#",
    "title": "카카오브레인의 <br/> 연구문화"
  },
  {
    "id": 3,
    "pic": "b3.png",
    "url": "#",
    "title": "PathFinder 2기의 <br/> 언어모델 활용기"
  },
  {
    "id": 4,
    "pic": "b4.png",
    "url": "#",
    "title": "칼로리의 꿈 <br/> 시리즈 ③"
  }
]
```

- json 데이터를 이용해서 자료를 추출한다.
  : 외부 주소를 통해서 자료를 불러들이기 위해 fetch 를 알고 적용한다.
  : 더불어서 크롬 개발자 도구 (F12) 의 NetWork 탭을 알아야 한다.
  : 옵션으로 Fetch/XHR 을 선택할 수 있어야 한다.
  : request 와 response 를 구별하여 파악할 수 있어야 한다.

```js
fetch("주소").then().then().catch();
```

```js
fetch("주소")
  .then((결과) => {
    const 접속결과 = 결과.json();
    return 접속결과;
  })
  .then()
  .catch();
```

```js
fetch("주소")
  .then((결과) => {
    const 접속결과 = 결과.json();
    return 접속결과;
  })
  .then(function (최종자료) {
    // 하고 싶은 일 마음대로....
  })
  .catch();
```

```js
fetch("주소")
  .then((결과) => {
    return 접속결과;
  })
  .then((최종자료) => {
    // 하고 싶은 일 마음대로....
    // 우리가 할 일을 진행한다.
  })
  .catch((오류) => {
    // 오류처리
  });
```

- 추출된 데이터로 html 을 생성한다.
  : 백틱(``)을 적극적으로 사용한다.

```js
let slideTags = "";

for (let i = 0; i < result.length; i++) {
  const data = result[i];
  // 템플릿 문법 필요 (html)
  const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background:url('./images/${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
  slideTags = slideTags + test;
}
```

: html 을 배치한다.

```js
// 원하는 장소에 출력해 보자.
const whereTag = document.querySelector(".topslide .swiper-wrapper");
whereTag.innerHTML = slideTags;
```

- swiper 를 작동시킨다.
  : html 완료 후 슬라이드 생성하자.

```js
// DOM 을 다루려고 하는 목적인 경우
window.addEventListener("load", function () {
  // 1. 외부에서 자료를 불러온다.
  const dataUrl = "./apis/topslide.json";

  fetch(dataUrl)
    .then((response) => {
      const data = response.json();
      // 변환된 결과를 돌려주기
      return data;
    })
    .then((result) => {
      // Step 2. json 변경된 데이터 활용하기
      // 전체 글자 모음
      let slideTags = "";

      for (let i = 0; i < result.length; i++) {
        const data = result[i];
        // 템플릿 문법 필요 (html)
        const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background:url('./images/${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
        slideTags = slideTags + test;
      }

      // 2. 자료를 이용해서 슬라이드에 배치할 html 을 만든다.
      // 원하는 장소에 출력해 보자.
      const whereTag = document.querySelector(".topslide .swiper-wrapper");
      whereTag.innerHTML = slideTags;

      // 3. html 완성후 swiper 를 생성한다.
      // 기본코드를 넣어보자.
      var topSlide = new Swiper(".topslide", {});
    })
    .catch((error) => {
      console.log(error);
    });
});
```

# Swiper Slide 적용해 보기 6.

- [옵션](https://swiperjs.com/demos)
  : loop
  : autoplay
  : effect
  : speed
  : pagenation(https://swiperjs.com/demos#pagination)
  : 페이지네이션 디자인 수정하기 참조!
  ```css
  .bannerslide .swiper-pagination {
    bottom: 30px !important;
  }
  .bannerslide .swiper-pagination-bullet {
    width: 4px !important;
    height: 4px !important;
    background: #ffffff !important;
    opacity: 0.7 !important;
    border-radius: 4px !important;
    transition: width 0.3s;
    margin: 0 2px !important;
  }
  .bannerslide .swiper-pagination-bullet-active {
    background: #ffffff !important;
    opacity: 1 !important;
    width: 20px !important;
  }
  ```

# js 4장

- var 변수명 = 변수값;
- let 변수명 = 변수값;
- const 변수명 = 변수값;

```txt
  호이스팅(hoisting) 은 변수, 함수를 선언하지 않았는데도
  사용할 수 있음. (hoisting 이 일어나지 않도록 주의: var 쓰지 말자)
```

# css 의 opacity 와 position 의 이해.

- opacity 는 DOM의 내용까지도 투명도가 적용된다.
- position
  : position 중에 absolute 로 픽셀 위치 설정의 경우 주의
  : 반드시 position 코드가 바깥 영역에도 있어야 합니다.
  : position 중에 fixed 는 웹브라우저를 기준으로 배치
  : fixed 는 반드시 left, top, right, bottom 을 주자
  : fixed 는 보통 z-index 를 준다.
  : fixed 는 높이에 반영이 안되므로 주의하자.(레이아웃 배치 문제)

```css
대상 {
  position: relative;
}
대상 {
  position: absolute;
}
대상 {
  position: fixed;
}
```

- 주의하자

```css
.box-wrap {
  position: relative;
  margin: 0 auto;
  width: 600px;
  height: 300px;
  background: orange;
}
.box {
  position: absolute;
  right: 80px;
  bottom: 20px;

  width: 200px;
  height: 200px;
  background: red;
}
```

# js 윈도우 스크롤의 위치를 알아내기

```js
window.addEventLinstenr("scoll", function () {
  // 하고 싶은 일
});
```

```js
window.addEventLinstenr("scoll", function () {
  // 스크롤바의 위치
  const scY = window.scrollY;
});
```

# js 로 css 의 클래스 동적으로 활용하기

```js
// DOM 찾아서 변수로 레퍼런스 하기
const tags = document.querySelector(".클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 추가
tags.classList.add("클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 제거
tags.classList.remove("클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 추가 / 제거
tags.classList.toggle("클래스명");
// DOM 을 이용해서 선택한 곳에 적용된 css 클래스 목록 포함여부
tags.classList.contain("클래스명");
```

# js 의 함수란 ? 1번

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복은 되지 않더라도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하자.
- 복잡하지는 않는데 코드가 너무 길어지면 함수로 묶어주려고 노력하자.
- 실행의 결과가 그때, 그때 다른 경우에도 함수를 만들자.

```js
// 함수만들기(함수선언)
function 적절한동사() {
  // 하고 싶은 일 작성 ....
}
// 함수사용하기(함수호출)
적절한동사();
// 예 (함수 체이닝)
fetch().then().then().catch();
```

- 함수는 무조건 1개의 값을 리턴하도록 규정되어 있습니다.
- 리턴이라는 것은 함수 실행() 후 값을 돌려주는 것을 말합니다.

```js
function 함수명() {
  // 몰래 작성됨 return undefined;
}
함수명();
```

# JS 5장

```txt
코딩에서 값이라고 할 수 있는 것은
  변수에 할당(보관한)된 결과를 말한다.

  변수란? 컴퓨터 공간에 이름을 붙여둔 방 한개

  표현식이

  평가(식을 해석해서 값을 생성하고 참조하는 것)된
   결과를 말한다.


   리터럴 이란?
   사람이 이해할 수 있는 문자 또는 약속된 기호를
   사용해서     값   을    생성하는 표기법

   리터럴은 값을 평가해서 코드에 활용하기 위한 문법


  "function"
  var function

  function gg(){}

  표현식 expressioin
  : 리터럴 값으로 평가가 되면 OK!
     5  숫자 리터럴 값으로 평가가 되면 OK!
     "안녕" 문자열 리터럴 값으로 평가가 되면 OK!

     var num = 5;
     var num:number = 5;


  문(statement) :  프로그램을 구성하는 기본단위/최소 실행단위

  {}


  var foo = x = 100
```

# js 의 함수란 ? 2번

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복은 되지 않더라도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하자.
- 복잡하지는 않는데 코드가 너무 길어지면 함수로 묶어주려고 노력하자.
- 실행의 결과가 그때, 그때 다른 경우에도 함수를 만들자.
- 함수 정의 문

```js
function 함수이름() {
  // 할일
}
```

- 함수 실행/호출(call) 문

```js
함수이름();
```

# js 의 함수의 매개변수란 ? 3번

- 초기 기능 즉, 함수를 정의하기 전에 기능 상 자주 변하는 데이터를 고민한다.
- 기능은 스크롤시 특정 위치 보다 커지면 css 추가하기
- 이전 코드는 좋지 않은 코드라고 생각이 든다.
- 함수는 스스로 지역 즉, Local 영역(Scope) 에서 처리되는 것이 좋다고 봐요.
- `처리` 라는 말은 변수를 찾는다 던가
- `처리` 라는 말은 잘못된 값이 전달되어서 오류가 나는 것을 방지하는 것을 말합니다.

```js
// 홍길동에게 줄 함수
const a = 5;
const b = 0;
function 나누기(_num1, _num2) {
  if (_num2 === 0) {
    alert("나눗셈에서 0은 안됩니다");
  }
  return _num1 / _num2;
}
나누기(a, b);
```

# JS 6장

```txt
   데이터 타입 ( Data Type ) : 자료형
   타입 이라는 말이 자료의 형태
   JS의 리터럴로 처리될 수 있는 자료의 종류

   타입 스크립트 : 데이터 종류를 표현해 주는 방식

    '5'   , "55", `555`
    'a'   , "ab", `55555`

    "안녕
      반가워
    "
    `안녕 ${100}
      반가워
    }
    `

    undefined 와  null 헷갈려요.
    const a = undefined; (모르겠다.)
    const b = null; (개발자가 직접 진짜 값이 비었다고 알려줌)

    Symbol 은 중복되지 않는다고 보장하는 값 타입
    Symbol()

    데이터 타입 ( Data Type ) : 자료형
    불변성(immutable) : 데이터 값이 변경될 수 없다.
    데이터는 immutable 해야 합니다.
    상태는   immutable 해야 합니다.
    state는  immutable 해야 합니다.

    1 = 1;


    가변성(mutable) : 데이터 값이 변경될 수 있다.


    원시데이터 6가지가 있는데 immutable 한 데이터 타입입니다.

    number   1
    string   'a'
    undefined undefined
    boolean    true, false
    null       null
    symbol     Symbol() 만들어진 값은 변경 불가

     복합형 데이터 객체
     객체는 원시데이터를 모아서 저장하고 관리하는 것.

    // 묶어라, Block
    const hong = {
        age: 20,
        marry : true
     }


     // 내가 c 라는 이름으로 저장할 거야
     // c 라는 공간은 글자를 보관할 거야
     // 그러니, 공간을 좀 마련해 줄래?

     // C 를 사용하는 프로그래머는
     char c = 'a'
     int num = 5;

     // js 를 사용하는 프로그래머는
     const c = 'a';
     const num = 5;

     // ts 를 사용하는 프로그래머는
     const c:string = 'a';
     const num:number = 5;


     // 오늘, 그리고 다음을 위해서 꼭 알아야 하는 단어

     1. 데이터 타입 : 자료(리터럴 값)의 종류

     2. js 에서는 값 리터럴에 따라 변수의 종류를 타입추론 한다.

     3. 타입을 추측해서 프로그래머에게 물어보지않고 타입을 변경한다. (암묵적 타입변경)

        let a = 1;
        a = "안녕";

        2번 3번은 원하지 않는 결과를 언젠가 실행됩니다.
        의도하지 않은 오류를 일으킨다.

        TypeScript

        let a:number = 1;
        a = "안녕"; // 오류 발생

  // 코딩 할 때 스스로 고민해 보자.

   1. 꼭 필요한 경우인지를 파악하고 변수를 만들자.
   2. 변수 유효범위는 좁게 (블록을 가능하면 쓰자)
   3. 전역변수는 가능하면 만들지 말자.
   4. 변수는 상수를 쓰세요.

      let a = 1; (X)

      const count = 1;

      {
        let count = 2;
      }
```

# 함수의 이해 7번

1. 함수를 만들어야겠다고 판단하는 케이스

- 동일한 코드가 2번 이상 반복되면 함수를 만들려고 노력하자.
- 반복은 되지 않더라도 하나의 기능이 너무 복잡하면 함수를 만들려고 노력하자.
- 복잡하지는 않는데 코드가 너무 길어지면 함수로 묶어주려고 노력하자.
- 실행의 결과가 그때, 그때 다른 경우에도 함수를 만들자.

2. 왜 화살표 함수를 만들지?

- 트랜드를 쫒아가자. (있어보이잖아요.)
- 코드가 해석하기 더 어려워집니다.

```js
function say() {
  console.log("안녕", this);
}
```

: step 1.

```js
say() => {
  console.log("안녕", this);
}
```

: step 2.

```js
const say = () => {
  console.log("안녕", this);
};
```

: 매개 변수가 있는 경우

```js
function say(_who) {
  console.log("안녕", _who, this);
}
```

: step 1.

```js
say(_who) => {
  console.log("안녕", _who, this);
}
```

: step 2.

```js
const say = (_who) => {
  console.log("안녕", _who, this);
};
```

- this 를 정확히 지정하기 위해서 활용한다.
  : 화살표 함수를 사용하면 일반적으로 큰 고민사용하면 됩니다.
  : 하지만, 함수 안에 this 를 작성하시면 상황이 달라집니다.
  : 화살표 함수에서 this 는 window 를 가르킵니다.
  : 결론은 화살표 함수에서 this 를 사용한다면 console.log(this) 확인필수!
  : 화살표 함수는 예전 일반 함수에서 window 를 참조하지 못하는 문제를 해결함.

```js
// this 의 차이(어렵지만 이해해야 해요.)
const btWrap = document.querySelector(".bt-wrap");
// 일반 함수는 this 가 타이핑이 된 곳을 가르킨다.
btWrap.addEventListener("click", function () {
  console.log(this);
});
// 화살표 함수는 this 가 window 를 가르킨다.
btWrap.addEventListener("click", () => {
  console.log(this);
});
```

# 배열의 이해

- [요소, 요소, 요소, 요소]
  : 요소로 담을 수 있는 자료형은 7가지 입니다.
- 배열의 속성(배열을 위한 특별한 변수)은 1개가 있습니다.
  : length 가 있어요. (요소의 개수)
- 배열의 메소드(배열을 위한 특별한 함수)는 너무 많아요.
- 상당히 많은 메소드(배열을 위한 함수) 가 있습니다.
- 배열.forEach((요소)=>{}), 배열.map((요소)=>{}), 배열.filter((요소)=>{}), 배열.find((요소)=>{})
- 배열의 요소를 하나씩 접근해서 활용하기
- 바보 카멜케이스 였는데. (배열.forEach ( ) )

```js
// 배열이라면 반복하자.
result.forEach((item) => {
  const tag = `<a href=${item.link} class="list-box">
        <div class="list-box-img br-20" style="background: url('./images/${item.imgpath}') no-repeat center; background-size: cover"></div>
        <div class="list-box-cate">
          <img src="./images/icon/${item.icon}" alt="${item.category}" />
          <span style="color:${item.txtcolor};">${item.category}</span>
        </div>
        <p class="list-box-title">${item.title}</p>
        <span class="list-box-day">${item.day}</span>
        </a>`;
  allTag = allTag + tag;
});
```

# JS 7장

```txt
operator (연산자)

   이  항   :   2개의 항목 을 처리하는 연산자 값만들기
   삼  항   :   3개의 항목 을 처리하는 연산자 값만들기
   단  항   :   1개의 항목 을 처리하는 연산자 값만들기

   +   -    *    /   % (모듈러 연산자)

   5 % 3 = 2 (나누고 난 후 나머지 값, 게시판 목록..)

    단  항   :   1개의 항목 을 처리하는 연산자 값만들기

    let a = 1;
    a = a + 1;
    a++;    // 원 값에 1을 더하라
    ++a;    // 원 값에 1을 더하라
    --a;    // 원 값에 1을 빼라
    a--;    // 원 값에 1을 빼라
    for(let i = 0; i < 10; i++) {
    }
    장바구니 개수 추가
    let bucket = 0;
    bucket++;

    알고리즘 공부
    let a = 1;
    let b = a++;   // b?  1   a = 2
    let b = ++a;   // b? 2

   1 + 2 = 3
   '1' + 2 = "12"
   글자도 더할 수 있다.

   const filePath = "./images/"
   const fileName = ".jpg";
   for(let i = 0; i < 10; i++) {
      const img = filePath + i + fileName;
      const img = "./images/" + 0 + ".jpg";
      const img = "./images/" + 1 + ".jpg";
      const img = "./images/" + 2 + ".jpg";
   }

    처음 코딩 배우면 어려워 하는 것

    문법
        []  ....
        for  문....
        할당 문...
        let num = 0;
        num = num + 1;
        num ++;
        num += 1;

==================== 적절한 구조를 어떻게? ====
    변수, 함수, 객체 구조?


   1 == '1'        같다 (true)
   암묵적으로 타입 변환 시켜서 진행 :  나중에 오류의 원인
   절대로 사용하지 마세요.


   1 === '1'  다르다.
     1. 먼저 데이터 종류 (data type) 비교합니다.
     2. 데이터 값 (data value) 비교합니다.

     !==



     (조건) ? 참실행 : 거짓실행

     (level > 10) ?  <div>주인님</div>    :   <div>일반회원</div>

     if(isLogin) {

        <div>"반가워"</div>

     }else{

        <div>회원가입</div>
     }

     const 객체 = {
         프로퍼티명 : 프로퍼티값
     }
     객체 in 프로퍼티명
     delete 객체.프로퍼티명;

     const sw = new Swiper(".slide", {} )

     const a = (1 + 10) * 100
```

- 함수 리턴의 이해

```txt
함수의 리턴 ?

     골치아프지만 그래도 일단 알아는 둡시다.

    1. 함수 정의
     function 함수이름(매개변수) {
     }

    2. 함수 호출
     const gogo = 함수이름(100); // gogo 에는 undefined;

    3. 리턴이 여러개인 경우

    : return 의 의미는 함수 결과값 돌려주기
    : return 은 함수 종료하기

     function 함수이름(매개변수) {
        return 1;
        return 2; // 영원히 실행이 안됨.
     }

```

# JS 8장

```txt
제어문은 조건에 따라서 코드 진행 방향이 결정된다

    고차함수 란 ? 함수의 매개변수로 함수를 전달한다.
    window.addEventListener(문자열타입, 함수타입)
    글자, 숫자, boolean, null, undefined, symbol
     객체 : [], funciton, {} ...

    버스를 기다린다.
     300 번은 5분마다 온다.  둘다 시내로 가요
     700 번은 10분마다온다.

     if(300 번 === 버스번호) {

     }else if(조건) {

     } else {

     }

     조건문으로 if 와  switch 문이 있다.
     주로~~~~   if 문을 우선 활용하세요.

     그리고, 나중에 리액트 하실 때, reducer 라는 것을 할때
     switch 를 그때 다시 접근하시길 권장해요.

     for 문은 반복 횟수가 명확할 때 주로 사용
     while 문은 반복 횟수가 불명확 할 때 주로 사용

     for (var i = 0; i < string.length; i++) {

           if(i === 3) {
             break;
           }

           console.log("안녕 ^^")
    }

> 반복을 대체할 수 있는 다양한 기능*
>
- forEach 메서드 : 배열을 순회할 때 사용
    [1,2,3]

- for in 문 : 객체의 프로퍼티를 열거할 때 사용
    {
      age: 1,
      marry: false,
      nicName: "Chlie"
    }

- for of 문 : 이터러블(itrable : 순서가 있는)을 순회 가능


```

# JS 9장

```txt
     명시적 타입 변환
      : 개발자가 타입을 강제 변환
      : 타입캐스팅

     암묵적 타입 변환 (코드에러가 아니고 원하는 결과가 아닌 경우)
      : JS가 타입을 몰래 변환
      : 타입 강제 변환
      : 개발자가 결과를 예측할 수 있어야 합니다. (대비책)

      :  + 연산자는
            '글자' + '글자' = '글자'
             숫자  +  숫자  =  숫자
            '글자' + 숫자   = '글자'     원칙(일단 숫자로 바꾼다.)


      :  - 연산자는
            '글자' - '글자' = NaN
             숫자  -  숫자  =  숫자
            ' 5 ' - 숫자   = '글자'     원칙(일단 숫자로 바꾼다.)

            console.log(typeof 결과)


        : Boolean    true/false

          Falsy 한 것들을 반드시 알아야해요  결과값 false 가 나옴
            false, undefined, null, 0, NaN, ''

            if (userId) {
               alert("아이디가 있어요")
            }else{
               alert("아이디가 없어요")
            }

      문자열 데이터 지정 만들기
        변수 + ''

      숫자 데이터 지정 만들기
        parseInt(변수)     :    정수 만들기
        parseFloat(변수)   :    실수 만들기

단축평가
 : 리액트에서 엄~~~~~~~~~~~~청 사용합니다.
 : 반드시 정말 알아야 합니다.

 : false, undefined, null, 0, NaN, ''

 - 논리곱(&&)
   true && true  결과는 true 입니다.

   "비욘세" && "디카프리오"  결과는 죄송하지만 true 가 아닙니다.
                            결과는 "디카프리오"

   const isLogin = true;
      isLogin &&  "<div>안녕</div"> 결과는 "<div>안녕</div">  출력

 - 논리합(||)

   true   || true  결과는 true 입니다.
   '10억' || '1원'    // '10억'
   ''     || '1원'    // '1원'

- 옵셔널 체이닝 나오게 된 이유  (?.)

   : Syntax 에러로 js 가 멈추고 나머지 전체 js 중지..
   var elem = null;
   var result = elem.gogo;

   : 해결하기 위해서
   var elem = null;
   var result = elem && elem.gogo;

   : Synatax 에러로 js 가 멈추지 않기를 바란다.

   var elem = null;
   var result = elem ? elem.gogo : undefined;
   var result = elem ?. gogo

- 병합연산자 (??)

const result = null   ?? "없군요"   결과값은 "없군요"
const result = "안녕" ?? "없군요"    결과값은 "안녕"
```

# JS 10장

```txt
- 너무 중요해요.
   : 활용빈도 말도 안되게 높고,
   : 본인 및 타소스를 이해하려면 알아야 해요.
   : 핵심은 JS 의 모든 자료타입은 객체입니다.

   - 타입(js가 리터럴로 인정하는 자료의 종류)

   : 원시 타입
    ( string, number, null, undefined, bool, symbol )

   : 객체타입
     ( [ 원시타입들... ] ,  { 속성명:원시타입 }, function ....  )


   - 객체 구성 ( 객체가 가진 데이터를 객체 내에서 제어하겠다.)

   : 객체에 포함된 변수를 `프로퍼티/속성` 이라고 호칭
   : 객체에 포함된 함수를 `메소드/기능` 이라고 호칭
      const obj = {

        "프로퍼티명" : 원시값 또는 다른 객체,
        "프로퍼티명" : string,
        "프로퍼티명" : [],
        "프로퍼티명" : {},
        "메소드명" : function () {},
      }

    - 객체 만드는 법
       인스턴스 란 ?
          : 남에게 말해주기가 어려운 개념
          : `객체를 생성하는 방법을 활용` 해 생성한 변수를 인스턴스라고 한다.

     1. 객체 리터럴 문법 : 활용빈도 높다. const 인스턴스 = {}

     const  인스턴스 = {
         "myName"  : 5,
          myJob     : 5,
         "my-age"   : 5,
         say   : function () { this["my-age"]  },
         sayHi : () => { this["my-age"]  },
     }
     인스턴스.myName
     인스턴스["myJob"]
     인스턴스.say()
     인스턴스["say"]()
     인스턴스.gogo = "안녕"

      : 객체 리터럴 문법 보완 및 축약 (ES6)

        // 기본형
        const 인스턴스변수 = {
          프로퍼티명: 프로퍼티값 ,
          프로퍼티명: 프로퍼티값 ,
          메소드명 : function() { },
          메소드명 : function() { }
        };

        const age = 10;
        const nickName = "홍길동";

        // 외부 변수 전달 받는데    이름이 똑~~ 같다?
        const person = {
           age      : age,
           nickName : nickName
        };

        //  축약형
        const person = {age, nickName};

        // 메소드 기본형
        const person = {
           say      : function() { }
        };

        // 메소드 축약형
        const person = {
           say() { }
        };



     2. Object 함수 문법

     3. 생성자 함수 문법 : 활용빈도 높다.

     4. Object.create 함수 문법

     5. class 함수 문법 : 활용빈도 높다.
```

# 카카오 브레인 블로그 사이트

- 반드시 저작권을 밝혀야 한다.
- 첫 화면만 연습 하면 됩니다. (첫 화면이 가장 난이도가 높다)
- 리액트 작업

# js 10장

```txt
일반 변수는 값이 보관되고    값이 복사된다.

    객체 변수는 주소가 보관되고 주소가 복사된다.
    : 중요한 것은 객체를 복사하는 것은 주의하자. (얕은복사)
    : 가능하면 객체는 깊은 복사를 활용하도록 노력하자.
```

# 깃 협업 (반드시 순서를 꼭! 지켜주세요.)

# JS 12 장

```txt
원시 데이터        ===> 단일 값
복합 데이터 : 복잡한 속성, 메서드를 가진 객체 ===> function, [], {}.

함수는 객체 의 문법을 따르는 값이다.


    function 함수이름(매개 변수) {
      return 문장을 작성 (값을 반드시 출력 : 표현식!!)
    }

    함수이름(인자)  :  함수 호출, 함수 실행, 함수 콜..


    리터럴은 JS 가  알아먹을 수 있는 데이터 형태로 작성한 것
    const a   = 1;             숫자 리터럴
    const add = function() {} ; 함수 리터럴


    const 더하기 =  function (){
    }
    console.log(더하기)  ???


    JS 의 일급객체에 대해서 말해 보시오.

    1. 값처럼 변수에 할당할 수 있는가?
      const add = function() {}

    2. 객체의 프로퍼티의 값으로 담을 수 있는가?
      const obj = { add : function(){}}

    3. 배열의 값으로 담을 수 있는가?
       const arr = [1, 2, 3, 4, function(){}, {}, [] ]

    4. 함수의 매개변수 값으로 전달할 수 있는가?
       function 말해봐(기능) {
           기능();
       }

       const 안녕 = function(){
        console.log("안녕하세요")
       }
       말해봐(안녕)


       말해봐( function(){ console.log("반가워요") } )

   - 함수가  객체를 생성하는 함수를 객체 생성자 함수 라고 합니다.

   - JS 의 함수에 전달되는 매개변수 목록을 arguments 라는 객체 라고 한다.

   - 함수의 매개변수로

     1. 원시 값을 인자로 전달하는 경우

     const age = 15;
     function grow( _value ) {
         return _value + 5;
     }

     grow(age);

     age 는 변화가 없다.


     2. 객체를 인자로 전달하는 경우 (정말 조심해야 해요)
     const person = { age: 10 }

     function growObject(_who) {
         _who.age = 150;
     }

     // 객체의 참조(주소) 값 전달
     growObject(person);

     // 객체의 상태가 변경이 일어난다.



     - 중첩 함수

        function Outer (){

            const handelClick = () => {

            }

            handelClick();

            return ( JSX 구문)
        }

     - 콜백 함수

        window.addEventListener( "이벤트글자", function(){ } )


     - 순수 함수
       function add(a, b) {
          return a + b;
       }

     - 비순수 함수
        const age = 10;
       function add( b) {
          return age + b;
       }
```

# 스코프(scope) : 대상을 사용할 때 찾을 범위

```txt
- 대상 : 함수, 변수, 클래스 등...
- var 변수
- let 변수, 또는 const 변수 가 차이가 큽니다.

  // 설명으로 바깥쪽 (함수의 바깥쪽) 를
  // 통상 `전역(global) 스코프`라고 합니다.

  var age = 15;

  function say() {
  // 통상 `지역(local) 스코프`라고 합니다.
   console.log(age)
  console.log(name)
  }

  say(); // ?

  // 설명으로 바깥쪽 (함수의 바깥쪽) 를
  // 통상 `전역(global) 스코프`라고 합니다.

  var age = 15;

  function say() {

      var age = 100;
      console.log(age)

  }

  say(); // ?

  var var_1 = 1;
  if(true) {
  var var_2 = 2;

      if(true) {
        var var_3 = 3;
      }

  }
  function say() {
  var var_4 = 4;
  }
  console.log(var_1)
  console.log(var_2)
  console.log(var_3)
  console.log(var_4)

  렉시컬 환경 (실행과 작성위치)

  JS 는 렉시컬 스코프 를 기본으로 합니다.

  : js 는 대상이 코딩 즉, 작성할때 스코프가 정해진다.
  : 즉, 그때 그때(실행할때 마다) 스코프가 달라지지 않는다.

  var age = 15;

  function say() {

            age += 1;
       var id = "hong";

  }

  say();

  - 앞으로 살펴볼 내용 예습

  let age = 1;

  if(true) {
  let age = 2;

      if(true) {
         let age = 3;
      }

  }
  function gogo() {
  let age = 100;
  }

  console.log(age)
```

# React 기초 1.

```txt
1. 사전준비
- node.js 설치 (nvm을 통해서 버전 교체 가능)
- npm은 자동으로 설치됨.
- yarn은 직접 설치하여야 함.

1. 프로젝트 생성법
- 폴더명은 규칙( 소문자로)
- 리액트 프로젝트
    - npx create-react-app ./ --template typescript

1. 진행순서
- public폴더에 www 폴더 생성 후 퍼블리싱 작업 진행 밑 테스트
- React js 버전으로 진행. (CSR)
- React ts 버전으로 진행.
- Next js 버전으로 진행. (SSR)

1. 프로젝트 내용 기본 파악하기

3.1. node_modules

- npm또는 yarn으로 다운로드 받은 파일 보관 폴더
-
- npm install 라이브러리명을 이용하여 다운로드 받고 활용
-
- 만약 프로젝트가 라이브러리등의 오류가 발생했다면 node_modules 폴더 삭제
    - node_modules 폴더 삭제
    - package-lock.json 파일 삭제
    - 이후 `npm i` 를 작성 후 실행(터미널)

- 깃허브에 push 대상에서 제외하기 위해 .gitignore에 자동 입력됨.

3.2. public폴더

- index.html
- 최초 웹서비스 실행시 실행되는 파일명.(파일명 변경 불가)
- lang=”ko” 수정
- favicon 아이콘 수정
- SEO 관련 내용은 별도 추가 (네이버 검색, 구글 검색, GA4)
- apple-touch-icon 수정
- title 내용 수정
- manifest.json은 추후 내용 수정필요
(https://web.dev/articles/add-manifest?hl=ko)
- id=”root”는 리액트 미리보기 및 결과물이 배치되는 장소
```

```js
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <!-- SEO 적용 필요 : 네이버 검색 및 구글 검색 등록 예정, GA4 예정 -->
    <meta name="description" content="카카오 브레인 블로그 클론 코딩" />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <title>카카오 브레인블로그</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>

```

: manifest.json

```json
{
  "short_name": "카카오 브레인 블로그 클론코딩",
  "name": "카카오 브레인 블로그 클론코딩",
  "icons": [
    {
      "src": "favicon.ico",
      "sizes": "64x64 32x32 24x24 16x16",
      "type": "image/x-icon"
    },
    {
      "src": "logo192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "logo512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": ".",
  "display": "standalone",
  "theme_color": "#000000",
  "background_color": "#ffffff"
}
```

: robots.txt

- 검색엔진 로봇이 내용을 접근해서 보관하는 여부 설정
- 상세 경험은 네이버 및 구글 검색엔진 등록시 실습

  3.3. src 폴더

- webpack 의 대상폴더
- index.js
  : 리액트 실행시 최초 실행되는 파일

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";
// 아래 라이브러리는 구글의 웹 성능 리포트 기능
// import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  // <React.StrictMode>
  <App />
  // </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
// reportWebVitals();
```

- TDD 관련 파일 제거 (Test Driven Develop)
  : 테스트 주도 개발
  : App.test.js
  : setupTests.js
- 성능 측정 파일 제거
  : reportWebVitals.js

- App.js는 최초 화면에 보여지는 내용

  3.4. .gitignore 파일

- 깃허브 파일 예외 사항 기재
- 폴더 및 파일 작성하면 제외됨.
- 추후 내용 작성 필요(예. 인증키)

  3.5. package-lcok.json

- node_modules에서 사용된 라이브러리들의 버전 보관

  3.6. package.json

- node.js 프로젝트 생성시 기초 정보 관리내용
- dependencies 항목이 중요합니다.
  : 프로젝트에 실제 활용한 라이브러리 목록(파악용도)
  : 개발 / 최종 빌드한 소스에 포함이 되는 라이브러리들 목록
  : npm start 개발시 포함
  : npm build 배포시 포함

# React 기초 1.
