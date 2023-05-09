# Quest 17-B. 배포 파이프라인

## Introduction
* 이번 퀘스트에서는 CI/CD 파이프라인이 왜 필요한지, 어떻게 구축할 수 있는지 등에 대해 다룹니다.

## Topics
* Continuous Integration
* Continuous Delivery
* AWS Codebuild

## Resources
* [AWS: Continuous Integration](https://aws.amazon.com/ko/devops/continuous-integration/)
* [AWS: Continuous Delivery](https://aws.amazon.com/ko/devops/continuous-delivery/)
* [AWS Codebuild](https://aws.amazon.com/ko/codebuild/getting-started/)

## Checklist
* CI/CD는 무엇일까요? CI/CD 시스템을 구축하면 어떤 장점이 있을까요?
- CI/CD는 Continuous Integration / Continuous Delivery (지속적인 통합 / 배포)의 준말로, 소프트웨어를 더욱 빠르게 개발, 배포할 수 있도록 자동화된 프로세스입니다.
CI/CD 시스템을 구축하면 개발, 테스트, 배포 등의 과정이 수동으로 이루어지는 경우에 발생할 수 있는 다양한 문제점들을 해결할 수 있습니다
1. 소스 코드 변경사항을 자동으로 통합하고 빌드하여 소프트웨어의 품질을 유지
2. 지속적인 배포를 통해 고객 요구사항에 더욱 신속하게 대응
3. 자동화된 테스트를 통해 버그를 사전에 발견하고 수정할 수 있음
4. 배포과정에서 발생할 수 있는 인간의 실수를 줄일 수 있음

* CI 시스템인 Travis CI, Jenkins, Circle CI, Github Actions, AWS Codebuild 의 차이점과 장단점은 무엇일까요?
- 

Travis CI는 GitHub에서 호스팅되는 무료 CI 도구입니다.
YAML 파일을 사용하여 빌드 및 배포를 구성할 수 있습니다.
무료 계정으로는 병렬 빌드가 제한됩니다.

Jenkins는 오픈소스 CI 도구로 가장 많이 사용되는 도구 중 하나입니다.
플러그인 시스템을 통해 다양한 기능을 추가할 수 있습니다.
병렬 빌드 및 클러스터링을 지원하여 대규모 프로젝트에 적합합니다.
초기 설정 및 관리가 복잡할 수 있습니다.

Circle CI는 클라우드 기반의 CI/CD 도구입니다.
YAML 파일을 사용하여 빌드 및 배포를 구성할 수 있습니다.
쉽게 설정하고 사용할 수 있으며, UI가 사용자 친화적입니다.
비교적 높은 가격 대비 기능이 적을 수 있습니다.

Github Actions는 GitHub에서 제공하는 무료 CI/CD 도구입니다.
YAML 파일을 사용하여 빌드 및 배포를 구성할 수 있습니다.
Github과의 연동이 용이하며, 커스텀 액션을 만들어서 사용할 수 있습니다.

AWS CodeBuild는 Amazon Web Services에서 제공하는 CI 도구입니다.
AWS 기반의 다양한 서비스와의 연동이 가능합니다.
빌드 시간 및 병렬 빌드에 대한 제한이 있습니다.

## Quest
* AWS Codebuild를 이용하여, 특정 브랜치에 푸시를 하면 린트와 테스트를 거쳐 서버 이미지를 빌드한 뒤, 직전 퀘스트의 EC2 인스턴스에 배포되는 시스템을 만들어 보세요.

## Advanced
* 빅테크 회사들이 코드를 빌드하고 배포하는 시스템은 어떻게 설계되고 운영되고 있을까요?
