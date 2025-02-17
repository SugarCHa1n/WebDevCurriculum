# Quest 01. HTML과 웹의 기초

## Introduction
* HTML은 HyperText Markup Language의 약자로, 웹 브라우저에 내용을 표시하기 위한 가장 기본적인 언어입니다. 이번 퀘스트를 통해 HTML에 관한 기초적인 사항들을 알아볼 예정입니다.

## Topics
* HTML의 역사
  * HTML 4.01, XHTML 1.0, XHTML 1.1
  * XHTML 2.0과 HTML5의 대립
  * HTML5와 현재
* 브라우저의 역사
  * Mosaic와 Netscape
  * Internet Explorer의 독점시대
  * Firefox와 Chrome의 등장
  * iOS Safari와 모바일 환경의 브라우저
  * Edge와 Whale 등의 최근의 Chromium 계열 브라우저
* HTML 문서의 구조
  * `<html>`, `<head>`와 `<body>` 등의 HTML 문서의 기본 구조
  * 시맨틱 엘리먼트
  * 블록 엘리먼트와 인라인 엘리먼트의 차이

## Resources
* [MDN - HTML](https://developer.mozilla.org/ko/docs/Web/HTML)
* [HTML For Beginners](https://html.com/)
* [History of the web browser](https://en.wikipedia.org/wiki/History_of_the_web_browser)
* [History of HTML](https://en.wikipedia.org/wiki/HTML)
* [StatCounter](https://gs.statcounter.com/)

## Checklist
* HTML 표준의 역사는 어떻게 될까요?
  * HTML 표준을 지키는 것은 왜 중요할까요?
  - HTML (HyperText Markup Language) 는 웹을 만드는 기본 구성요소이다. 웹컨텐츠의 의미와 구조를 정의한다. Html외 에는 보통 웹페이지의 보여지는 부분을 기술 할 때  CSS, 기능, 행동을 기술 할 때 Javascript를 사용한다.

  * XHTML 2.0은 왜 세상에 나오지 못하게 되었을까요?
  - 새로운 표준에 웹브라우저들이 렌더링 엔진을 수정해야하는데 웹이 문서중심이 아니라 어플리케이션 중심으로 가면서 xml기반 웹으로 변화하지 못한 상황에서 HTML5 표준이 만들어지고 HTML5를 기반으로 XHTML5가 나타나며 W3C가 XHTML2 활동을 접는다고 발표 

  * HTML5 표준은 어떤 과정을 통해 정해질까요?
  - World Wide Web Consortium(W3C)의 정기적인 컨소시엄을 통해서 지난 10년간 80여개의 W3C 권고안을 발표하였습니다. 또한 웹에 관하여 토론할 수 있는 열린 포럼, 심포지엄을 통하여 사용자의 불편을 이해하고 차기 표준안에 반영할 수 있도록 지속적인 활동을 수행합니다.

* 브라우저의 역사는 어떻게 될까요?
- 1990년, 팀 버너스리(Tim Berners-Lee)는 CERN(유럽 입자 물리 연구소)에 있었는데, 연구 자료의 관리와 공유를 쉽게 하기 위해 어디서든 자료를 열람할 수 있는 시스템을 만들었다.
하이퍼링크(참조)를 통해 한 문서에서 다른 문서로 접근할 수 있는 **하이퍼텍스트(Hypertext)**기반의 정보 저장 시스템이다. 그리고 어느 컴퓨터에서든 사용가능하도록 하기 위해, 브라우저가 서버에게 요청해서 문서를 받아올 수 있는 규칙인 HTTP(Hypertext Transfer Protocol), 각 하이퍼링크가 가리키는 고유 주소인 URI 그리고 문서의 형식을 HTML로 정의했다.
이때 HTTP는 오로지 문서를 가져오는 용도로만 쓰였기 때문에 GET 메서드만 있었다.
1993년, 인터넷이 막 보급되면서 사람들이 브라우저를 조금씩 쓰기 시작했는데, 텍스트로만 페이지를 작성하다보니 어느정도 한계가 존재했다.
당시 NCSA에 다니고 있던 마크 앤드리슨(Marc Andreessen)이 최초로 텍스트와 이미지를 함께 보여주는 브라우저 Mosaic을 만들었다. 인터넷을 사용하는 사람이 2천만 명도 안되던 시기에, 1년 반만에 2백만 다운로드가 될 정도로 유명한 브라우저가 되었다.

  * Internet Explorer가 브라우저 시장을 독점하면서 어떤 문제가 일어났고, 이 문제는 어떻게 해결되었을까요?
  - 독점 시장에서 기능개선이 거의 이루어지지 않았고 IE는 웹표준을 에 맞지 않게 기능 확장을 Active X라는 프로그램을 통해서 했으며 이는 상호 호환성이 떨어지는 문제를 가지고 있었는데 새로운 브라우저의 등장(크롬, 파이어 폭스 등)하면서 문제가 해결되고 또 현재 브라우저 시장에서 IE의 사용율도 적어짐

  * 현재 시점에 브라우저별 점유율은 어떻게 될까요? 이 브라우저별 점유율을 알아보는 것은 왜 중요할까요?
  - 내는 크롬 > IE > 엣지 > 웨일
세계적으로는 크롬 > 파이어폭스 / 사파리 > 엣지
개발시 브라우저마다 지원하는 기능이 다르고 크로스 브라우징에 대응 하기 위해 

  * 브라우저 엔진(렌더링 엔진)이란 무엇일까요? 어떤 브라우저들이 어떤 엔진을 쓸까요?
  - 요즘 추세는 오픈소스 렌더링 엔진 Webkit을 사용한 브라우저가 추세
렌더링이란 브라우저 화면에 내용을 그리는 것 (HTML, XML 문법을 화면에 그림으로 그려준다, plug-in이나 확장기능을 통해 다른타입의 데이터들도 표시 가능)

  * 모바일 시대 이후, 최근에 출시된 브라우저들은 어떤 특징을 가지고 있을까요?
  - 다양한 모바일 기기에 맞춘 반응형 웹뷰를 제공, 애플이나 삼성에서는 기기 뿐 아니라 직접 브라우저 개발도 함 모바일환경에 필요한 블루투스 컨트롤이나 자이로 센서 기능등 브라우저의 기능이 확장되었다.

* HTML 문서는 어떤 구조로 이루어져 있나요?
  * `<head>`에 자주 들어가는 엘리먼트들은 어떤 것이 있고, 어떤 역할을 할까요?
  - head에는 HTML의 메타 데이터(다른 데이터를 설명해주는 데이터)가 포함된다. 
<meta> 태그 의 요소로 charactor 인코딩, author, comment 추가가능
<title> 제목태그
<link> favicon 및 css 참조

  * 시맨틱 태그는 무엇일까요?
  - 시멘텍 태그란 의미가 있는 태그라는 뜻 

    * 시맨틱 엘리먼트를 사용하면 어떤 점이 좋을까요?
    - 검색엔진 최적화 : 검색엔진은 태그를 기반으로 페이지 내의 검색 키워드의 우선순의를 판단 의미에 따라 올바른 태그를 사용해야한다. ( h1은 제목 중요한 단어는 strong 또는 em을 사용 하듯이 나는 보통 이것들을 사이즈나 폰트조정하는데 사용하였지... 의미보단 보여지는중심으로...)
웹 접근성 : 시각장애가 있는 사용자가 스크린 리더를 사용하여 페이지를 탐색할 때 올바르게 화면을 이해할 수 있게 도와준다. (ex : img 태그의 alt 요소로 이미지의 설명을 붙여준다)
W3C에 따르면 시맨틱 웹을 사용하면 애플리케이션, 기업 및 커뮤니티에서 데이터를 공유하고 재사용  할 수 있다고 한다. (모두가 규칙을 알고 준수하면 데이터를 이해하기가 쉽다)

    * `<section>`과 `<div>`, `<header>`, `<footer>`, `<article>` 엘리먼트의 차이점은 무엇인가요?
    - <div> : html문서의 구획을 구분하여 보통 css 나 javascript로 스타일링을 하기위한 의미가 없는태그
<article> : 내용 단락, 그 자체로 의미가 있는 웹사이트의 부분 
            독립적으로 배포 또는 재사용되도록 의도 된 문서이다.
<aside> : 부가 단락, 본문과 관련된 부가정보를 노출, 사이드바 또는 콜아웃 상자로 사용된다.
<details> : 클릭했을 때 확장되는 UI, 공지사항/FAQ
<figcaption> : figure 부가 설명
<figure> : 독립적인 콘텐츠
<footer> : 회사 정보, 소셜미디어 정보, 약관, 저작권
<header> : 페이지의 제목과 같은 소개내용을 포함한다.
           일반적으로 heading 태그나 로고 또는 아이콘, 저작권 정보, 검색 양식, 작성자 이름 
           등을 포함한다.
<main> : 문서에서 오직 한 번만 사용. 본문, 콘텐츠 내용 전체(지배적인 콘텐츠 영역)
<mark> : 하이라이트, 강조
<nav> : 메뉴, 목차
<section> : 형식 단락, 구체적 시맨틱 태그가 없는 문서의 독립적인 영역 
            (섹션에는 매우 소수의 예외를 제외하고 항상 제목이 있는 것이 일반적이다)
<summary> : 클릭했을 때 확장되는 UI, 공지사항/FAQ
<time> : 시간 내용

  * 블록 레벨 엘리먼트와 인라인 엘리먼트는 어떤 차이가 있을까요?
  - 인라인엘리먼트는 줄바꿈이 안되고 블록레벨엘리먼트는 줄바꿈이 된다.(print 와 println)
주의할점 블럭레벨 태그는 인라인 태그의 상위구조이기 때문에 블럭레벨태그안에 인라인 태그를 둘수 있지만 인라인 태그 요소안에 블록레벨 태그를 위치 시키면 안된다.


## Quest
* [이 화면](screen.png)의 정보를 HTML 문서로 표현해 보세요. 다만 CSS를 전혀 사용하지 않고, 문서의 구조가 어떻게 되어 있는지를 파악하여 구현해 보세요.
  * [CSS Naked Day](https://css-naked-day.github.io/)는 매년 4월 9일에 CSS 없는 웹 페이지를 공개하여 내용과 마크업에 집중한 HTML 구조의 중요성을 강조하는 행사입니다.
* 폴더에 있는 `skeleton.html` 파일을 바탕으로 작업해 보시면 됩니다.
  * 화면을 구성하는 큰 요소들을 어떻게 처리하면 좋을까요?
  * HTML 문서상에서 같은 층위에 비슷한 요소들이 반복될 때는 어떤 식으로 처리하는 것이 좋을까요?

## Advanced
* XML은 어떤 표준일까요? 어떤 식으로 발전해 왔을까요?
* YML, Markdown 등 다른 마크업 언어들은 어떤 특징을 가지고 있고, 어떤 용도로 쓰일까요?
