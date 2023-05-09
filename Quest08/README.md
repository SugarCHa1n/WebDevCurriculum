# Quest 08. 웹 API의 기초

## Introduction
* 이번 퀘스트에서는 웹 API 서버의 기초를 알아보겠습니다.

## Topics
* HTTP Method
* node.js `http` module
  * `req`와 `res` 객체

## Resources
* [MDN - Content-Type Header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type)
* [MDN - HTTP Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
* [MDN - MIME Type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type)
* [Postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop)
* [HTTP Node.js Manual & Documentation](https://nodejs.org/api/http.html)

## Checklist
* HTTP의 GET과 POST 메소드는 어떻게 다른가요?
-   get방식이든 post방식이든 둘 다 브라우저가 서버에 요청하는 것이지만, GET은 요청을 전송할 때 필요한 데이터를 Body에 담지 않고, 쿼리스트링을 통해 전송
반면 post방식은 GET과 달리 전송해야될 데이터를 HTTP 메세지의 Body에 담아서 전송합니다

  * 다른 HTTP 메소드에는 무엇이 있나요?
- put, patch, delete 등이 있습니다.

* HTTP 서버에 GET과 POST를 통해 데이터를 보내려면 어떻게 해야 하나요?
- get 요청을 보내려면 URL에 요청 파라미터를 포함시키고, post 요청을 보내려면 http 요청 본문에 데이터를 담아서 보내면 됩니다

  * HTTP 요청의 `Content-Type` 헤더는 무엇인가요?
  - HTTP 요청 또는 응답 메시지에 포함되는 데이터의 종류를 정의하는 미디어 타입을 나타내는 역할을 합니다. 해당 헤더는 클라이언트에서 서버로 요청을 보낼 때 요청 헤더에 포함될 수 있으며, 서버에서 클라이언트로 응답을 보낼 때 응답 헤더에 포함될 수 있습니다

  * Postman에서 POST 요청을 보내는 여러 가지 방법(`form-data`, `x-www-form-urlencoded`, `raw`, `binary`) 각각은 어떤 용도를 가지고 있나요?
  - form-data: 파일 업로드와 같은 binary 데이터를 전송할 때 사용합니다.
x-www-form-urlencoded: 폼 데이터를 전송할 때 사용합니다. 키-값 쌍으로 인코딩되며, 여러 개의 키-값 쌍을 전송할 수 있습니다.
raw: JSON 데이터나 XML 데이터와 같이 일반 텍스트 데이터를 전송할 때 사용합니다.
binary: 바이너리 데이터를 직접 전송할 때 사용합니다.

* node.js의 `http` 모듈을 통해 HTTP 요청을 처리할 때,
  * `req`와 `res` 객체에는 어떤 정보가 담겨있을까요?
  - req 객체는 클라이언트에서 서버로 전송된 HTTP 요청 정보가 담겨있고, res 객체는 서버에서 클라이언트로 전송할 HTTP 응답 정보가 담겨 있습니다. req 객체에는 요청 URL, 요청 메소드, 헤더, 요청 본문 등이, res 객체에는 상태 코드, 헤더, 응답 본문 등이 담겨 있습니다.

  * GET과 POST에 대한 처리 형태가 달라지는 이유는 무엇인가요?
  - GET은 주로 데이터를 가져오는 용도로 사용되며 URL에 파라미터를 포함하여 요청, 반면에 POST는 데이터를 전송하는 용도로 사용되며 요청 본문에 데이터를 담아 전송하기 때문

* 만약 API 엔드포인트(URL)가 아주 많다고 한다면, HTTP POST 요청의 `Content-Type` 헤더에 따라 다른 방식으로 동작하는 서버를 어떻게 정리하면 좋을까요?
- 라우팅(Routing)을 이용하여 URL 패턴에 따라 적절한 요청 핸들러 함수를 연결해주면 됩니다

  * 그 밖에 서버가 요청들에 따라 공통적으로 처리하는 일에는 무엇이 있을까요? 이를 어떻게 정리하면 좋을까요?
     - 
인증 및 권한 부여
로깅(loggin) 및 모니터링
오류 처리(error handling)
캐싱(caching)
데이터 검증(validation)
요청 제한 제어(rate limiting)
보안(security)

## Quest
* 다음의 동작을 하는 서버를 만들어 보세요.
  * 브라우저의 주소창에 `http://localhost:8080`을 치면 `Hello World!`를 응답하여 브라우저에 출력합니다.
  * 서버의 `/foo` URL에 `bar` 변수로 임의의 문자열을 GET 메소드로 보내면, `Hello, [문자열]`을 출력합니다.
  * 서버의 `/foo` URL에 `bar` 키에 임의의 문자열 값을 갖는 JSON 객체를 POST 메소드로 보내면, `Hello, [문자열]`을 출력합니다.
  * 서버의 `/pic/upload` URL에 그림 파일을 POST 하면 서버에 보안상 적절한 방법으로 파일이 업로드 됩니다.
  * 서버의 `/pic/show` URL을 GET 하면 브라우저에 위에 업로드한 그림이 뜹니다.
  * 서버의 `/pic/download` URL을 GET 하면 브라우저에 위에 업로드한 그림이 `pic.jpg`라는 이름으로 다운로드 됩니다.
* expressJS와 같은 외부 프레임워크를 사용하지 않고, node.js의 기본 모듈만을 사용해서 만들어 보세요.
* 처리하는 요청의 종류에 따라 공통적으로 나타나는 코드를 정리해 보세요.

## Advanced
* 서버가 파일 업로드를 지원할 때 보안상 주의할 점에는 무엇이 있을까요?
