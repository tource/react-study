# main 영역 html, css

## 1. html

- 레이아웃을 공통적용을 위해서 inner div 작성(header 처럼)
- main-top 과 main-bottom 을 inner 안쪽으로 배치
- main-top 클래스에 왼쪽, 오른쪽 영역 잡기

## 2. css

- 화면의 너비 즉, vw 를 이용해서 높이에 반영
- 너비와 높이가 같이 변하는 반응형 작성시
  : `보여줄 높이 / 화면의 너비 * 100 = 결과값 vw`
  : `보여줄 너비 / 화면의 너비 * 100 = 결과값 %`

- 모서리를 둥글게
  : `border-radius: 20px`
- 내용 일부 가리기
  : `overflow:hidden`
