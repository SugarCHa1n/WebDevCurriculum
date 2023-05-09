# Quest 12. 보안의 기초

## Introduction
* 이번 퀘스트에서는 가장 기초적인 웹 서비스 보안에 대해 알아보겠습니다.

## Topics
* XSS, CSRF, SQL Injection
* HTTPS, TLS

## Resources
* [The Basics of Web Application Security](https://martinfowler.com/articles/web-security-basics.html)
* [Website Security 101](https://spyrestudios.com/web-security-101/)
* [Web Security Fundamentals](https://www.shopify.com.ng/partners/blog/web-security-2018)
* [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
* [Wikipedia - TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security)

## Checklist
* 입력 데이터의 Validation을 웹 프론트엔드에서 했더라도 서버에서 또 해야 할까요? 그 이유는 무엇일까요?
- Validation을 웹 프론트엔드에서 했더라도 보안과 데이터 정합성을 위해서는 서버에도 반드시 해야합니다.
클라이언트 측에서의 validation은 보안 측면에서 취약합니다. 클라이언트 측에서 validation을 우회하여 악의적인 데이터를 서버로 보낼 수 있기 때문입니다.

  * 서버로부터 받은 HTML 내용을 그대로 검증 없이 프론트엔드에 innerHTML 등을 통해 적용하면 어떤 문제점이 있을까요?
  - 내용을 검증없이 그대로 프론트엔드에 적용하면 크로스 사이트 스크립팅(XSS) 공격이 발생할 수 있습니다. 따라서 서버로부터 받은 HTML 내용을 적용하기 전에도 서버 측에서 검증을 수행하는 것이 중요하겠습니다.

  * XSS(Cross-site scripting)이란 어떤 공격기법일까요?
  - XSS 공격은 악의적인 사용자가 악성 스크립트를 삽입하여 웹 페이지에 접근하는 다른 사용자의 브라우저에서 실행되도록 하는 공격

  * CSRF(Cross-site request forgery)이란 어떤 공격기법일까요?
  - CSRF(Cross-site request forgery)는 사용자가 의도하지 않은 요청을 악용하여 공격하는 기법

  * SQL Injection이란 어떤 공격기법일까요?
  - SQL Injection은 악의적인 사용자가 웹 애플리케이션의 입력란에 SQL 코드를 삽입하여, 데이터베이스에 비정상적인 접근을 시도하는 공격 기법

* 대부분의 최신 브라우저에서는 HTTP 대신 HTTPS가 권장됩니다. 이유가 무엇일까요?
-  HTTP는 암호화되지 않은 텍스트를 사용하기 때문에 중간에 제3자가 네트워크 트래픽을 가로채면 데이터를 볼 수 있음.
반면에 HTTPS를 사용하면 암호화된 통신 채널을 통해 데이터를 전송하므로 중간에 제3자가 가로채서 데이터를 볼 수 없다. 이를 통해 데이터의 안전성을 보장함.

  * HTTPS와 TLS는 어떤 식으로 동작하나요? HTTPS는 어떤 역사를 가지고 있나요?
  - HTTPS는 SSL(Secure Sockets Layer) 또는 TLS(Transport Layer Security) 프로토콜을 이용하여 통신을 암호화합니다 TLS는 SSL의 후속버전으로 HTTPS에서는 클라이언트와 서버가 TLS를 이용하여 통신을 암호화합니다. HTTPS의 등장 배경은 1990년대 말에 인터넷 상에서의 정보 보호와 인증 문제가 대두되었기 때문입니다. 초기에는 SSL을 이용하여 HTTPS가 사용되었으며, 이후에는 SSL의 취약점이 발견되어 TLS가 등장하면서 HTTPS에 적용되었습니다. 현재는 TLS 1.3이 최신 버전으로 사용되고 있습니다.

  * HTTPS의 서비스 과정에서 인증서는 어떤 역할을 할까요? 인증서는 어떤 체계로 되어 있을까요?
  - 인증서는 웹 사이트의 신원을 확인하고, 인증 기관(CA)이 발행한 유효한 인증서인지를 확인하는 역할을 합니다. 인증서는 공개키 인프라(PKI) 체계로 구성되어 있습니다. 인증서는 공개키 암호화 방식을 사용하여 서명됩니다. 인증서의 발급자는 인증 기관(CA)으로, 이 기관은 공개키와 개인키를 가지고 있습니다. 인증서의 발급자(CA)는 웹 사이트의 신원 정보를 확인하고, 인증서를 발급합니다. 이 인증서는 웹 서버에 설치되며, 클라이언트가 웹 사이트에 접속할 때 인증서를 받아 인증서의 정보를 확인합니다. 이를 통해 클라이언트는 웹 사이트가 신뢰할 수 있는지 확인할 수 있습니다.


## Quest
* 메모장의 서버와 클라이언트에 대해, 로컬에서 발행한 인증서를 통해 HTTPS 서비스를 해 보세요.

## Advanced
* TLS의 인증서에 쓰이는 암호화 알고리즘은 어떤 종류가 있을까요?
* HTTP/3은 기존 버전과 어떻게 다를까요? HTTP의 버전 3이 나오게 된 이유는 무엇일까요?
