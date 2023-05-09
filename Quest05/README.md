# Quest 05. OOP 특훈

## Introduction
* 이번 퀘스트에서는 바닐라 자바스크립트의 객체지향 프로그래밍을 조금 더 훈련해 보겠습니다.

## Topics
* Separation of Concerns
* 객체지향의 설계 원칙
  * SOLID 원칙
* Local Storage

## Resources
* [Separation of concerns](https://jonbellah.com/articles/separation-of-concerns/)
* [SOLID](https://en.wikipedia.org/wiki/SOLID)
* [객체지향 설계 5원칙](https://webdoli.tistory.com/210)
* [MDN - Local Storage](https://developer.mozilla.org/ko/docs/Web/API/Window/localStorage)

## Checklist
* 관심사의 분리 원칙이란 무엇인가요? 웹에서는 이러한 원칙이 어떻게 적용되나요?
- 관심사의 분리 원칙(Separation of Concerns, SoC)은 소프트웨어 설계 원칙 중 하나로, 프로그램을 여러 개의 독립적인 부분으로 분할하여 각각의 부분이 각자 다른 책임을 가지도록 하는 것입니다.
웹에서는 이러한 원칙을 적용하기 위해 보통 MVC(Model-View-Controller) 패턴이나 MVVM(Model-View-ViewModel) 패턴 등을 사용합니다. 이러한 패턴들은 프레젠테이션 로직과 비즈니스 로직을 분리하여 코드를 더욱 간결하고 유지보수하기 쉽게 만들어줍니다

* 객체지향의 SOLID 원칙이란 무엇인가요? 이 원칙을 구체적인 예를 들어 설명할 수 있나요?
- S - 단일 책임 원칙 (Single Responsibility Principle)
각 클래스는 단 하나의 책임을 가져야 하며, 클래스의 변경은 오직 그 책임에만 영향을 미쳐야 합니다.
O - 개방-폐쇄 원칙 (Open-Closed Principle)
기존 코드를 변경하지 않으면서 기능을 추가할 수 있도록 설계되어야 합니다. 즉, 코드는 확장 가능하지만 수정 가능성은 최소화되어야 합니다.
L - 리스코프 치환 원칙 (Liskov Substitution Principle)
자식 클래스는 부모 클래스를 대체할 수 있어야 하며, 이를 통해 다형성을 구현할 수 있습니다.
I - 인터페이스 분리 원칙 (Interface Segregation Principle)
클라이언트는 자신이 사용하지 않는 메서드에 의존하지 않도록 인터페이스를 분리해야 합니다. 인터페이스가 너무 많아지는 경우에는 클라이언트가 필요한 메서드만 사용할 수 있는 더 작은 인터페이스로 분리해야 합니다.
D - 의존 역전 원칙 (Dependency Inversion Principle)
추상화에 의존해야 하며, 구체화에 의존하면 안 됩니다. 즉, 클래스는 인터페이스나 추상 클래스와 같은 추상화된 것에 의존해야 하며, 구체적인 구현체에 의존해서는 안 됩니다.

* 로컬 스토리지란 무엇인가요? 로컬 스토리지의 내용을 개발자 도구를 이용해 확인하려면 어떻게 해야 할까요?
- 로컬 스토리지(Local Storage)는 HTML5에서 추가된 웹 스토리지 API 중 하나로, 클라이언트 측에서 데이터를 로컬에 저장할 수 있게 해주는 기능입니다. 로컬 스토리지에 저장된 내용을 개발자 도구를 이용해 확인하려면 브라우저의 개발자 도구에서 Application 탭을 열어 Local Storage를 클릭하면 로컬 스토리지에 저장된 내용을 확인할 수 있습니다.


## Quest
* 외부 라이브러리나 프레임워크를 사용하지 않고, 자바스크립트를 이용하여 간단한 웹브라우저 기반의 텍스트 에디터를 만들어 보겠습니다.
  * 기본적으로 VSCode와 같이 탭을 이용해 여러 개의 파일을 동시에 편집할 수 있습니다.
  * 탭을 눌러 열려 있는 다른 파일을 편집할 수 있으며 탭을 언제든지 닫을 수 있습니다.
  * VSCode와 같이 새 파일, 로드, 저장, 다른 이름으로 저장 등의 기능을 가집니다. 저장은 웹 브라우저의 로컬 스토리지를 이용합니다.
  * VSCode와 같이 탭이 수정되었는데 저장되기 이전일 경우 이를 알려주는 인디케이터가 작동합니다.
  * 같은 이름의 파일을 저장할 경우 에러를 표시해야 합니다.
* 이번 퀘스트의 결과물은 앞으로의 많은 퀘스트에서 재사용되게 되니, 주의깊게 코드를 작성해 보세요!

## Advanced
* 웹 프론트엔드 개발에서 이러한 방식의 패턴을 더 일반화해서 정리할 수 있을까요? 이 퀘스트에서 각각의 클래스들이 공통적으로 수행하게 되는 일들에는 무엇이 있을까요?
