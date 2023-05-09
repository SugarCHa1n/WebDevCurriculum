# Quest 07. node.js의 기초

## Introduction
* 이번 퀘스트에서는 node.js의 기본적인 구조와 개념에 대해 알아 보겠습니다.

## Topics
* node.js
* npm
* CommonJS와 ES Modules

## Resources
* [About node.js](https://nodejs.org/ko/about/)
* [Node.js의 아키텍쳐](https://edu.goorm.io/learn/lecture/557/%ED%95%9C-%EB%88%88%EC%97%90-%EB%81%9D%EB%82%B4%EB%8A%94-node-js/lesson/174356/node-js%EC%9D%98-%EC%95%84%ED%82%A4%ED%85%8D%EC%B3%90)
* [npm](https://docs.npmjs.com/about-npm)
* [npm CLI commands](https://docs.npmjs.com/cli/v7/commands)
* [npm - package.json](https://docs.npmjs.com/cli/v7/configuring-npm/package-json)
* [How NodeJS Require works!](https://www.thirdrocktechkno.com/blog/how-nodejs-require-works)
* [MDN - JavaScript Modules](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Modules)
* [ES modules: A cartoon deep-dive](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/)
* [require vs import](https://www.geeksforgeeks.org/difference-between-node-js-require-and-es6-import-and-export/)

## Checklist
* node.js는 무엇인가요? node.js의 내부는 어떻게 구성되어 있을까요?
- Node.js는 V8 JavaScript 엔진으로 빌드된 이벤트 기반, 논 블로킹 I/O 모델을 사용하는 서버 사이드 JavaScript 런타임입니다. Node.js는 자바스크립트 코드를 서버 측에서 실행할 수 있게 해주는 것이 주요 목적입니다. Node.js는 V8 JavaScript 엔진, 이벤트 루프, 라이브러리, 바인딩, 자바스크립트 코드로 이루어져있습니다. 

* npm이 무엇인가요? `package.json` 파일은 어떤 필드들로 구성되어 있나요?
- npm(Node Package Manager)은 자바스크립트 패키지 매니저로, Node.js로 작성된 모듈들을 관리하는 도구입니다. npm은 패키지 설치, 업데이트, 의존성 관리, 실행 스크립트 등을 지원합니다.
package.json 파일은 Node.js 프로젝트에서 프로젝트 정보와 의존성 패키지 정보를 담고 있는 파일입니다. 이 파일은 프로젝트의 루트 디렉토리에 위치하며, name, version, dependencies, devDependencies, scripts 등의 필드로 구성됩니다.

* npx는 어떤 명령인가요? npm 패키지를 `-g` 옵션을 통해 글로벌로 저장하는 것과 그렇지 않은 것은 어떻게 다른가요?
- npx는 npm 패키지를 실행하기 위한 도구입니다. 일시적으로 npm 패키지를 설치하고 실행한 뒤 제거합니다.
npm 패키지를 -g 옵션을 통해 글로벌로 저장하면 해당 패키지를 시스템 전역에서 사용할 수 있습니다. 반면 -g 옵션 없이 로컬에 저장하는 경우, 해당 패키지는 프로젝트 내에서만 사용할 수 있습니다. 일반적으로 프로젝트마다 필요한 패키지들이 다를 수 있으므로, 글로벌 옵션보다는 로컬 옵션이 권장됩니다.

* 자바스크립트 코드에서 다른 파일의 코드를 부르는 시도들은 지금까지 어떤 것이 있었을까요? CommonJS 대신 ES Modules가 등장한 이유는 무엇일까요?
- 기존에는 CommonJS와 AMD(Asynchronous Module Definition) 방식이 주로 사용되었습니다. CommonJS는 Node.js에서 사용되었으며 require() 함수와 module.exports 객체를 통해 모듈을 로드하고 내보내는 방식입니다. AMD는 브라우저에서 사용되며 비동기로 모듈을 로드하는 방식입니다.
ES Modules는 ECMAScript 6에서 새롭게 도입된 표준 모듈 시스템입니다. import와 export 문을 사용하여 모듈을 로드하고 내보내는 방식입니다. 이전 방식들에 비해 문법이 간결하고 브라우저에서도 사용할 수 있어 통일성 있는 모듈 시스템을 제공합니다. 또한, 정적으로 모듈을 로드하기 때문에 성능 측면에서 이점을 가지고 있습니다.

* ES Modules는 기존의 `require()`와 동작상에 어떤 차이가 있을까요? CommonJS는 할 수 있으나 ES Modules가 할 수 없는 일에는 어떤 것이 있을까요?
- CommonJS에서는 require()로 파일 경로 외에도 디렉토리를 지정하면 해당 디렉토리 내부의 index.js 파일을 불러올 수 있지만, ES Modules에서는 이 기능을 제공하지 않습니다. 또한 CommonJS에서는 동적으로 모듈을 로드하는 require() 함수를 제공하며, 이러한 동적 로딩은 ES Modules에서 제공되지 않습니다.

* node.js에서 ES Modules를 사용하려면 어떻게 해야 할까요? ES Modules 기반의 코드에서 CommonJS 기반의 패키지를 불러오려면 어떻게 해야 할까요? 그 반대는 어떻게 될까요?
- Node.js에서 ES Modules를 사용하려면 파일 확장자를 .mjs로 지정하거나, package.json 파일의 "type" 필드에 "module"을 설정해야 합니다.
ES Modules 기반의 코드에서 CommonJS 기반의 패키지를 불러오려면 require() 함수를 사용할 수 있습니다. 예를 들어, const express = require('express')와 같은 방법으로 불러올 수 있습니다.
반대로 CommonJS 기반의 코드에서 ES Modules 기반의 패키지를 불러오려면 import 구문을 사용해야 합니다. 예를 들어, import express from 'express'와 같은 방법으로 불러올 수 있습니다. 하지만 이 방법으로는 일부 CommonJS 모듈을 불러올 수 없습니다.


## Quest
* 스켈레톤 코드에는 다음과 같은 네 개의 패키지가 있으며, 용도는 다음과 같습니다:
  * `cjs-package`: CommonJS 기반의 패키지입니다. 다른 코드가 이 패키지의 함수와 내용을 참조하게 됩니다.
  * `esm-package`: ES Modules 기반의 패키지입니다. 다른 코드가 이 패키지의 함수와 내용을 참조하게 됩니다.
  * `cjs-my-project`: `cjs-package`와 `esm-package`에 모두 의존하는, CommonJS 기반의 프로젝트입니다.
  * `esm-my-project`: `cjs-package`와 `esm-package`에 모두 의존하는, ES Modules 기반의 프로젝트입니다.
* 각각의 패키지의 `package.json`과 `index.js` 또는 `index.mjs` 파일을 수정하여, 각각의 `*-my-project`들이 `*-package`에 노출된 함수와 클래스를 활용할 수 있도록 만들어 보세요.

## Advanced
* node.js 외의 자바스크립트 런타임에는 어떤 것이 있을까요?
