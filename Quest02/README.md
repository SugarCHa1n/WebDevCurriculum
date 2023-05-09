# Quest 02. CSS의 기초와 응용

## Introduction
* CSS는 Cascading StyleSheet의 약자입니다. 웹브라우저에 표시되는 HTML 문서의 스타일을 지정하는 (거의) 유일하지만 다루기 쉽지 않은 언어입니다. 이번 퀘스트를 통해 CSS의 기초적인 레이아웃 작성법을 알아볼 예정입니다.

## Topics
* CSS의 기초 문법과 적용 방법
  * Inline, `<style>`, `<link rel="stylesheet" href="...">`
* CSS 규칙의 우선순위
* 박스 모델과 레이아웃 요소
  * 박스 모델: `width`, `height`, `margin`, `padding`, `border`, `box-sizing`
  * `position`, `left`, `top`, `display`
  * CSS Flexbox와 Grid
* CSS 표준의 역사
* 브라우저별 Developer tools

## Resources
* [MDN - CSS](https://developer.mozilla.org/ko/docs/Web/CSS)
* [Centering in CSS: A Complete Guide](https://css-tricks.com/centering-css-complete-guide/)
* [A complete guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* [그리드 레이아웃과 다른 레이아웃 방법과의 관계](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Grid_Layout/%EA%B7%B8%EB%A6%AC%EB%93%9C_%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83%EA%B3%BC_%EB%8B%A4%EB%A5%B8_%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83_%EB%B0%A9%EB%B2%95%EA%B3%BC%EC%9D%98_%EA%B4%80%EA%B3%84)

## Checklist
* CSS를 HTML에 적용하는 세 가지 방법은 무엇일까요?
-  inline, internal, external 방법이 있다.

  * 세 가지 방법 각각의 장단점은 무엇일까요?
  - inline: HTML 태그 안에 스타일 속성으로 CSS를 적용하는 방법으로, 간단하고 빠르게 스타일을 적용할 수 있다. 하지만 유지보수가 어렵고, 중복 코드 발생과 가독성 저하 문제가 있을 수 있다.
internal: HTML 문서 안에 <style> 태그를 이용하여 CSS를 적용하는 방법으로, inline보다 유지보수가 용이하며 중복 코드를 줄일 수 있다. 하지만 HTML 문서 내부에 스타일 코드가 들어가므로 파일 크기가 커질 수 있다.
external: CSS 파일을 따로 만들어 HTML 문서에서 link 태그를 이용하여 불러오는 방법으로, 가장 일반적으로 사용되는 방법이다. 유지보수성이 우수하고 캐싱 효과로 인해 파일 다운로드 시간이 단축된다. 하지만 네트워크 연결 문제로 파일을 불러올 수 없는 경우가 있을 수 있다.

* CSS 규칙의 우선순위는 어떻게 결정될까요?
- !important 규칙
inline 스타일 규칙
ID 선택자로 적용한 규칙
class, attribute, pseudo-class 선택자로 적용한 규칙
요소 선택자로 적용한 규칙
상위 요소에 의해 상속된 규칙
우선순위는 이러한 순서에 따라 결정되지만, 적용된 스타일이 같은 우선순위를 가지는 경우, 나중에 적용된 규칙이 우선한다.

* CSS의 박스모델은 무엇일까요? 박스가 화면에서 차지하는 크기는 어떻게 결정될까요?
- CSS의 박스모델은 HTML 요소를 박스 형태로 간주하며, 콘텐츠 영역(content), 패딩 영역(padding), 테두리 영역(border), 마진 영역(margin)으로 구성된다

* `float` 속성은 왜 좋지 않을까요?
- float 속성은 레이아웃을 만들 때 예상치 못한 결과를 가져올 수 있어서 사용을 지양해야 함

* Flexbox(Flexible box)와 CSS Grid의 차이와 장단점은 무엇일까요?
- Flexbox는 1차원 레이아웃에 강점을 가지고, CSS Grid는 2차원 레이아웃에 강점을 가짐. 각각의 장단점을 고려하여 사용해야 함

* CSS의 비슷한 요소들을 어떤 식으로 정리할 수 있을까요?
- CSS의 비슷한 요소들은 기능, 사용 방법, 속성 등에 따라 카테고리화하고, 관련된 요소끼리 그룹화하면 코드의 유지 보수성과 가독성이 좋아짐

## Quest
* Quest 01에서 만들었던 HTML을 바탕으로, [이 그림](screen.png)의 레이아웃과 CSS를 최대한 비슷하게 흉내내 보세요. 꼭 완벽히 정확할 필요는 없으나 align 등의 속성은 일치해야 합니다.
* **주의사항: 되도록이면 원래 페이지의 CSS를 참고하지 말고 아무것도 없는 백지에서 시작해 보도록 노력해 보세요!**

## Advanced
* 왜 CSS는 어려울까요?
* CSS의 어려움을 극복하기 위해 어떤 방법들이 제시되고 나왔을까요?
* CSS가 브라우저에 의해 해석되고 적용되기까지 내부적으로 어떤 과정을 거칠까요?
* 웹 폰트의 경우에는 브라우저 엔진 별로 어떤 과정을 통해 렌더링 될까요?
