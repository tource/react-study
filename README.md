# Axios

## 1. axios 를 연습할때

- [josn-server](https://www.npmjs.com/package/json-server)
- [참조자료](https://poiemaweb.com/json-server)

## 2. 서버 구축 과정

- D:드라이브에 server 폴더를 만든다.
- VSCode 에서 프로젝트 등록을 한다.
- Node.js 프로젝트로 등록을 한다. (리액트 상관없음)

## 3. Node.js 프로젝트 생성하기

- `npm init` 엔터

## 4. json-server npm 설치

- `npm install -g json-server`
- db.json 파일 생성

```json
{
  "posts": [
    { "id": "1", "title": "a title", "views": 100 },
    { "id": "2", "title": "another title", "views": 200 }
  ],
  "comments": [
    { "id": "1", "text": "a comment about post 1", "postId": "1" },
    { "id": "2", "text": "another comment about post 1", "postId": "1" }
  ],
  "profile": {
    "name": "typicode"
  },
  "todos": [
    {
      "id": 1,
      "content": "HTML",
      "completed": true
    },
    {
      "id": 2,
      "content": "CSS",
      "completed": false
    },
    {
      "id": 3,
      "content": "Javascript",
      "completed": true
    }
  ],
  "users": [
    {
      "id": 1,
      "name": "Lee",
      "role": "developer"
    },
    {
      "id": 2,
      "name": "Kim",
      "role": "designer"
    }
  ]
}
```

## 5. json-server 실행

- `json-server --watch db.json`
- 리액트가 3000 포트를 사용하고 있음.
- json-server 도 3000 포트를 사용하므로 충돌 발생함.
- `json-server --watch db.json --port 5000`
- json-server 포트를 5000 번으로 변경

## 6. package.json 에 script 명령어 추가하기

```json
{
  "name": "server",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "json-server --watch db.json --port 5000"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "json-server": "^1.0.0-beta.0"
  }
}
```

## 7. API 테스트하기

- CRUD 테스트 (크러드)
  : Create (POST)
  : Read (GET)
  : Update (PUT / Fetch )
  : Delete (DELETE)
- Postman (웹 API 테스트시 일반적 사용)
- Swagger (웹 API 테스트시 별도로 BE에서 셋팅)
- Web Browser (웹 프로젝트 CORS 에러 발생 함)
  : package.json 에 "proxy":"주소" 를 작성해야 한다.

## 8. Axios 활용

- [axios](https://axios-http.com/kr/docs/intro)
- `npm install axios`

## 8.1. axios 폴더 추천

- /src/apis 폴더 생성
- /src/apis/config.js

```js
// 서버 주소
export const SERVER_URL = "http://localhost:5000";
```

- /src/apis/todos.js

# 리액트 이벤트 핸들러

## 1. 기본

- click, change

### 1.1. JS 태그버전

- 먼저 내용을 정리하고 아래 내용을 참조합니다.
  : 반드시 소문자 on 에 소문자 이벤트
  : <태그 on이벤트명="함수명()">내용</태그>
  : 소문자 onclick="함수명()"
  : 소문자 onchange="함수명()"
  : 저는 안좋아합니다. 이유는 태그가 복잡해짐.

- 태그에 직접 이벤트 연결하기
  : 반드시 소문자로 on + 이벤트 로 작성한다.
  : 예) onclick

  ```html
  <button onclick="alert('안녕')">클릭</button>
  ```

  : 태그에 JS 를 실행하는 경우 호출(call)을 꼭 해주자.

  ```html
  <script>
    function 함수() {
      alert("안녕");
    }
  </script>
  : 아래의 예는 실행 안됨.
  <button onclick="함수">클릭</button>

  : 아래의 예는 실행됨.
  <button onclick="함수()">클릭</button>
  ```

## 2. JS 태그 메소드 버전

- 먼저 내용을 정리하고 참조하자.
  : 태그를 먼저 찾고 이벤트를 연결한다.
  : 태그.소문자 on이벤트명 연결한다.
  : on이벤트명 함수 연결시 실행(Call)하면 안되는 주의사항
  : 여러개의 함수를 등록할 수 없다. (사용안하게 된 계기)

  ```js
  const btClass = document.querySelector(".bt");
  const btId = document.querySelector("#bt");
  const btTag = document.querySelector("ul li a");
  btClass.onclick = 함수명;
  btId.onclick = 함수명;
  btTag.onclick = 함수명;
  ```

: 객체.메소드
: 아래의 코드는 순서상 html 태그를 못찾아서 에러 발생

```html
<script>
  function 함수() {
    alert("안녕");
  }

  const bt = document.querySelector("#bt");
  // 객체.메소드
  // 아래 코드는 1번 call 즉, 호출되면서 실행됨
  // bt.onclick = 함수();
  // 아래처럼 진행한다. () 를 제거해야 한다.
  bt.onclick = 함수;
</script>

<button id="bt">클릭</button>
```

```html
<button id="bt">클릭</button>

<script>
  function 함수() {
    alert("안녕");
  }
  function 함수2() {
    alert("반가워");
  }

  const bt = document.querySelector("#bt");
  // 객체.메소드
  bt.onclick = 함수;
  // 기능은 1개 밖에 연결이 안되는 단점이 있다.
  bt.onclick = 함수2;
</script>
```

## 3. JS 태그 이벤트 핸들러 등록 버전

- 아래의 내용을 참조하고 코드 보자.
  : 여러개의 함수를 등록할 수 있다.
  : 주의사항은 on 이라는 글자가 제거되어야 함.

```html
<button id="bt">클릭</button>

<script>
  function 함수() {
    alert("안녕");
  }
  function 함수2() {
    alert("반가워");
  }

  const bt = document.querySelector("#bt");
  // 객체 이벤트 핸들러 등록 방식
  // 이벤트 명만 적어야 함. 그래서 오류
  bt.addEventListener("onclick", 함수);
  bt.addEventListener("onclick", 함수2);
  //아래는 이벤트 명을 정확하게 작성하였으므로 정상
  bt.addEventListener("click", 함수);
  bt.addEventListener("click", 함수2);
</script>
```

## 4. React 버전

- 아래의 내용을 먼저 정리합니다.
  : 리액트는 JSX 버전이 기본입니다.
  : 이벤트는 소문자가 아닙니다.
  : 이벤트는 on소문자에 대문자시작하는 이벤트명입니다.
  : 이벤트에 연결될 함수는 2가지 방식으로 작성이 가능하다.
  : 함수명() 로 () 를 붙이면 함수 Call 즉, 실행입니다.
  : 함수명만 적어주어야 합니다.
  : 매개변수 전달되는 함수라면 화살표 함수로 감싸주세요.

  ```jsx
  // 함수가 실행되므로 오류입니다.
  <JSX onClick={함수명()}></JSX>
  <JSX onClick={함수명}></JSX>
  // 매개변수로 값을 전달하고 싶다면
  <JSX onClick={() => { 함수명(매개변수) } }></JSX>

  <JSX onChange={함수명}></JSX>
  ```

  : 예)

  ```jsx
  <button
    onClick={() => {
      getTodos("와아아앙");
    }}
  >
    읽기
  </button>
  <button
    onClick={() => {
      getTodos("ㅋㅋㅋ");
    }}
  >
    하나만 읽기
  </button>
  <button
    onClick={() => {
      getTodos("ㅎㅎㅎㅎ");
    }}
  >
    쓰기
  </button>
  ```

# JS 26장

```txt

25장 클래스

: 단어에 대한 정의가 있으시면 이해가 좀 편합니다.

: 인스턴스, 객체, 프로퍼티, 메소드 를 단어에 대한 이해가 필요

: 문법에 제시되는 클래스라는 것을 현업에서 많이 쓰는가요?
 - 외부 소스 활용시 참조가 필요해요.

: 다른 프로그래밍을 배우신 분들이 js 에 적응하라고 나온 문법

1. 객체 생성 함수 와 클래스를 같이 비교하면 이해가 편합니다.

1.1. 객체 생성자 함수

     객체      :  인스턴스
     생성자    :  constructor () { }   // 고정된 이름
     함수      :  class

    - 객체 생성자 함수
     function Person(){ }
     const a = new Person();

    - class Person {}
      const a = mew Person();

2. 클래스와 생성자 함수의 차이점

2.1. 클래스는 new 연산자 없이 호출하면 에러 발생.
   생성자 함수는 new 연산자 없이 호출하면 일반 함수로서 호출된다.

   function Go(){}   new Go();  Go();
   class Go {}       Go(); 에러

2.2. 클래스는 extends와 super 키워드로 상속 가능.
   생성자 함수는 extends와 super 키워드를 지원하지 않는다.

   function  강아지() extends 동물
   {
       super(); // 에러
   }

   class 강아지 extends 동물 {
       constructor() {
         super();
       }
   }


2.3. 클래스는 호이스팅이 발생하지 않는 것처럼 동작하고,

   const a = new 강아지();

   class 강아지 {}

  함수 선언문으로 정의된 생성자 함수는 함수 호이스팅이,

    const go = new 강아지();
    function 강아지() {}

  함수 표현식으로 정의한 생성자 함수는 변수 호이스팅이 발생한다.

  const 강아지 = function() {}
  const go = new 강아지();


2.4. 클래스 내부에는 자동으로 strict mode가 지정되며 해제할 수 없다.
   생성자 함수는 직접 지정해 줘야한다.

2.5. 클래스의 constructor, 프로토타입 메서드, 정적 메서드는 모두 열거되지 않는다.(`[[Enumerable]]`⇒`false`)

 3. 클래스에서 정의한 메소드의 특징
 class Person {
     // new Person() 하면 자동 실행 되는 메서드 : 인스턴스 생성자 함수
     constructor() {
        // return this; // new 해서 만들어진 인스턴스를 리턴합니다.
     }

    // 일반 메소드
    sayHi() {}
    sayBye() {}

    // 클래스 메소드로서 Person.go() : 반드시 클래스명을 적고 실행
    static go() {}

 }

 4. 접근제한자

   private   속성  :  외부에서 읽기, 쓰기, 변경 안되요.
   public    속성  :  외부에서 읽기, 쓰기, 변경 다~~되요
   protected 속성  :  허락된 환경만 읽기, 쓰기, 변경 다~~되요

 5. 접근자 프로퍼티

 class Person = {

   // 클래스 필드 : 클래스에 정의한 속성
    #firstName: "Ungmo",

    get fullName() {
      return this.firstName;
    }

    set fullName(ha) {
       this.firstName = ha
    }
 }

 const go = new Person();
 go.fullName;
 go.fullName = "홍길동";

 6. 상속에 의한 클래스 확장 ( extends )

 : 오로지 class 에만 작성 가능
 : 속성과 메소드 상속
 : 자기만의 속성과 메소드 정의로 확장

```

# JS 26장

```txt
26 장

1. 우리 반 만 정의한 호칭

- 이제부터 함수 와 메소드 를 명칭을 컨벤션하겠습니다.

- 일반 함수
  function 함수명() {}

- 객체 함수
 {
    함수명: function(){}
 }

- 메소드
 {
   함수명() {}
 }

2. 화살표 함수

2.1. 매개 변수 가 있을 때 모양을 신경쓰자.

 - (x, y) => return x + y;

 - x => return x;

 - () => return 1 + 2;


2.2. return 도 신경 써요.

 : return 작성을 하지 않아도 자동으로 기재 됩니다.
 : 아래는 기본형입니다.

 2.2.1. 실행해야 하는 함수 블록이 1 줄이라면

 - (x, y) => {
        return x + y;
    }

 : 한줄이라서 {} 이 생략가능
 - (x, y) => return x + y;

 : 바로 리턴되는 경우는 return 생략 됨.
 - (x, y) => x + y;


 2.2.2. 실행해야 하는 함수 블록이 1 줄 이상이라면

 - (x, y) => {
        const a = x + y;
        return a;
    }

 : 한줄이라서 {} 이 생략 불가능
 - (x, y) =>  const a = x + y;
          return x + y; // 오류


 2.2.3. 실행해야 하는 함수가   객체 리터럴을 return 하면 ?

 - (x, y) => {
        return {a:x, b:y};
    }

:  1줄이라서 {} 제거, 1줄 리턴하길래 return 도 제거

 - (x, y) => { a:x, b:y }; // 오류

 - (x, y) => ( { a:x, b:y } ); // 정상

 3. Rest 파라메터

 3.1. 파라메터 ( ... parameter )   함수 ( ...매개 변수 )

  : ...매개 변수 는 [] 입니다.

  : ...매개 변수 는 arguments 를 대체합니다.

  3.2. Rest 파라메터 위치를 살펴보면

  : 나머지를 받아서 배열로 만든다.
  : 함수(a, ...rest,  c) // 오류
  : 함수(a, c, ...rest ) // 정상

  4. 함수의 매개변수의 기본값도 셋팅 가능
  : 함수( a = 1,  b = {age:5}, c = 3 ) { }
```

# JS 27 배열

```txt
27 장 배열

 : 저는 배열을 책장으로 비유하겠습니다.

 1. 명칭에 대한 이해가 필수

 - 요소?  특정한 칸에 보관하는 값이다.

 - 인덱스?  특정한 칸에 번호를 말함.
           시작부분부터 <  도착 전까지

 - 길이?    length (칸의 개수)



 2. 왜 필요하니?

  쇼핑몰 운영자

  function GoodRegister = function(이름, 가격, 판매, 할인, 전시장소 = "추천상품"){
    return  {
              이름:이름,
              가격: 가격,
              판매:판매,
              할인: 할인,
              전시장소: 전시장소,
              인사말: function() { alert(this.이름 + "구매해주셔서 감사합니다.")
              }
      };
  }
  const 사과 = new GoodRegister("사과", 1000, true, 0.5}
  const 딸기 = new GoodRegister("딸기", 5000, false, 1.0}

  const good_arr = [사과, 딸기];

 3. 기능들?
    기준은 원본 배열을 훼손 함수
    기준은 원본 배열을 유지하고 복사해서 결과를 돌려주는 함수
    function go(...arr){}

     [...arr]

 4. 원본을 훼손하는 것과 원본을 복사하여서 원본을 유지하고 복사본을 사용하는 이유?
    React 의  Re-Rendering 을 위해서

 5. 배열에서 고차함수들의 기본형을 꼭!!! 알자
   : 원본 데이터 불변성 유지
   : 배열.함수명( (요소, index, 복사배열 ) =>  {   .....   } )


  직렬화 ====> 문자열만들기

  redux  ====>   reduce 를 보고 이름 정함

  [1,2,3,4].reduce( (acc, cur, index, arr) => acc + cur,   0  )
```
