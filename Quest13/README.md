# Quest 13. 웹 API의 응용과 GraphQL

## Introduction
* 이번 퀘스트에서는 차세대 웹 API의 대세로 각광받고 있는 GraphQL에 대해 알아보겠습니다.

## Topics
* GraphQL
  * Schema
  * Resolver
  * DataLoader
* Apollo

## Resources
* [GraphQL](https://graphql.org/)
* [GraphQL.js](http://graphql.org/graphql-js/)
* [DataLoader](https://github.com/facebook/dataloader)
* [Apollo](https://www.apollographql.com/)

## Checklist
* GraphQL API는 무엇인가요? REST의 어떤 단점을 보완해 주나요?
- GraphQL은 Facebook에서 개발한 API Query 언어입니다. REST API와 달리 클라이언트에서 필요로 하는 데이터의 구체적인 요구사항을 전달할 수 있습니다.

* GraphQL 스키마는 어떤 역할을 하며 어떤 식으로 정의되나요?
- GraphQL 스키마는 GraphQL API에서 지원하는 데이터 타입과 해당 타입의 필드, 쿼리와 뮤테이션(Operation) 등을 정의하는 것으로, GraphQL API에서 제공하는 데이터의 구조와 유형을 나타냅니다.
스키마를 작성할 때는 SDL(Schema Definition Language)이라는 GraphQL의 특수 언어를 사용합니다. 스키마는 GraphQL API의 핵심이며, 스키마에 기반하여 GraphQL 쿼리를 작성하고 실행할 수 있습니다.

* GraphQL 리졸버는 어떤 역할을 하며 어떤 식으로 정의되나요?
- GraphQL에서는 데이터 소스에서 직접 데이터를 가져오는 대신, 데이터를 가져오는 방법에 대한 로직을 리졸버에서 작성하고 그 결과를 반환합니다. 리졸버는 GraphQL 스키마의 필드와 1:1 매칭됩니다. 스키마에서 정의된 필드에 대해 어떤 데이터를 반환할지 결정하는 함수를 리졸버로 작성합니다. 리졸버는 함수로 작성되며, 첫 번째 인수로는 부모 객체, 두 번째 인수로는 인자, 세 번째 인수로는 컨텍스트, 네 번째 인수로는 GraphQL 쿼리 정보가 전달됩니다. 이러한 인수들을 활용하여 데이터를 가져오고 가공하여 반환하게 됩니다.

  * GraphQL 리졸버의 성능 향상을 위한 DataLoader는 무엇이고 어떻게 쓰나요?
  - DataLoader는 여러 데이터 요청 사이에서 중복된 데이터를 효율적으로 로드하고 캐시하며, 데이터 요청의 수를 줄여 성능을 향상시킵니다. DataLoader를 사용하려면 GraphQL 리졸버에서 호출할 데이터 로더를 정의하고 필요한 곳에서 사용하면 됩니다.

* 클라이언트 상에서 GraphQL 요청을 보내려면 어떻게 해야 할까요?
- 클라이언트에서 GraphQL 요청을 보내기 위해서는 보통 HTTP POST 요청을 사용합니다. 

  * Apollo 프레임워크(서버/클라이언트)의 장점은 무엇일까요?
  - 
쉬운 설정: Apollo는 GraphQL의 서버 및 클라이언트를 설정하는 데 필요한 모든 기능을 제공합니다. 또한 Apollo Client는 React, Angular, Vue 등 다양한 프레임워크와 함께 사용할 수 있습니다.
상태 관리: Apollo Client는 GraphQL의 캐시를 통해 상태를 관리합니다. 이를 통해 로컬 상태와 서버에서 가져온 데이터를 효율적으로 관리할 수 있습니다.
데이터 소스: Apollo는 REST API, 데이터베이스, 마이크로서비스 등 다양한 데이터 소스를 지원합니다.
성능 최적화: Apollo는 데이터를 요청하는 방식과 캐싱을 최적화하여 불필요한 데이터 요청을 줄입니다. 또한 GraphQL의 쿼리를 사용하여 필요한 데이터만 가져올 수 있습니다.
유지 보수성: Apollo는 GraphQL의 타입 시스템을 사용하여 코드의 안정성을 높입니다. 또한 타입 시스템을 통해 API의 변경 사항을 더 쉽게 파악할 수 있습니다.
개발 생산성: Apollo는 GraphQL의 스키마 및 리졸버 생성 등 개발 생산성을 높이는 기능을 제공합니다.
커뮤니티: Apollo는 활발한 개발자 커뮤니티를 가지고 있으며, 다양한 문제에 대한 해결책을 찾을 수 있습니다.

  * Apollo Client를 쓰지 않고 Vanilla JavaScript로 GraphQL 요청을 보내려면 어떻게 해야 할까요?
  - XMLHttpRequest 객체를 생성합니다.
GraphQL API의 엔드포인트 URL을 설정합니다.
HTTP 요청 메소드를 POST로 설정합니다.
요청에 필요한 HTTP 헤더를 설정합니다. Content-Type 헤더는 application/json으로 설정해야 합니다.
요청 바디에 GraphQL 쿼리를 JSON.stringify() 메소드를 이용해 JSON 문자열로 변환하여 설정합니다.
send() 메소드를 호출하여 서버에 요청을 보냅니다.
서버로부터 응답을 받으면 responseText 속성을 이용하여 응답 바디를 가져옵니다.
받아온 응답 바디는 JSON.parse() 메소드를 이용하여 JavaScript 객체로 변환합니다.

* GraphQL 기반의 API를 만들 때 에러처리와 HTTP 상태코드 등은 어떻게 하는게 좋을까요?
- GraphQL 쿼리가 유효하지 않거나, 데이터베이스 오류 등으로 인해 GraphQL 서버가 예기치 않은 응답을 반환할 수 있습니다. 이러한 경우, GraphQL 서버는 응답의 "errors" 필드를 포함하여 에러에 대한 정보를 클라이언트에게 전달할 수 있습니다. 이를 통해 클라이언트는 어떤 에러가 발생했는지에 대한 정보를 받을 수 있습니다.


## Quest
* 메모장의 서버와 클라이언트 부분을 GraphQL API로 수정해 보세요.

## Advanced
* GraphQL이 아직 제대로 수행하지 못하거나 불가능한 요구사항에는 어떤 것이 있을까요?
* GraphQL의 경쟁자에는 어떤 것이 있을까요?
