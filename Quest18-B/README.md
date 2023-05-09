# Quest 18-B. 서비스의 운영: 로깅과 모니터링

## Introduction
* 이번 퀘스트에서는 서비스의 운영을 위해 로그를 스트리밍하는 법에 대해 다루겠습니다.

## Topics
* ElasticSearch
* AWS ElasticSearch Service
* Grafana

## Resources
* [ElasticSearch](https://www.elastic.co/kr/what-is/elasticsearch)
* [ElasticSearch 101](https://www.elastic.co/kr/webinars/getting-started-elasticsearch)
* [Grafana Panels](https://grafana.com/docs/grafana/latest/panels/)

## Checklist
* ElasticSearch는 어떤 DB인가요? 기존의 RDB와 어떻게 다르고 어떤 장단점을 가지고 있나요?
- ElasticSearch는 분산 검색 엔진 및 분석 도구로 분산형 NoSQL 데이터베이스입니다. 기존의 RDB와는 다르게 구조가 유연하며, 대용량의 비정형 데이터를 빠르게 검색, 분석할 수 있습니다. ElasticSearch는 대용량 데이터를 저장하고 검색하기 위한 Lucene 라이브러리를 기반으로 하며, 다양한 형태의 쿼리, 필터링, 집계, 분석 등의 기능을 제공합니다. 하지만 ElasticSearch는 RDB처럼 일관성 있는 데이터 저장을 보장하지 않으며, 일부 쿼리의 경우 RDB보다 복잡한 구조와 쿼리문을 필요로 합니다. 또한, 무분별한 데이터 색인 및 검색 사용으로 인한 부하로 인해 성능 저하가 발생할 수 있습니다

* AWS의 ElasticSearch Service는 어떤 서비스인가요? ElasticSearch를 직접 설치하거나 elastic.co에서 직접 제공하는 클라우드 서비스와 비교하여 어떤 장단점이 있을까요?
- AWS의 Elasticsearch Service는 AWS에서 제공하는 완전 관리형 Elasticsearch 서비스입니다. 이 서비스는 Elasticsearch 클러스터를 쉽게 설정, 운영, 확장할 수 있도록 도와줍니다.
AWS ElasticSearch Service의 장점으로는
AWS에서 관리하는 완전 관리형 서비스로, 설치, 구성, 유지 관리 및 업그레이드를 AWS가 처리해줍니다.
클러스터 크기와 인스턴스 유형을 쉽게 조정할 수 있습니다.
클러스터를 보안하고 모니터링할 수 있으며 로깅 및 알림 설정을 구성할 수 있습니다.
AWS VPC와 통합하여 보안 및 네트워크 구성을 쉽게 할 수 있습니다.

* Grafana의 Panel 형식에는 어떤 것이 있을까요? 로그를 보기에 적합한 판넬은 어떤 형태일까요?
- Grafana의 Panel 형식은 크게 6가지로 분류됩니다.
Graph Panel: 선 그래프, 면 그래프, 막대 그래프 등 시계열 데이터를 시각화하는데 적합한 패널입니다.
Singlestat Panel: 하나의 수치 데이터를 표시하는 패널입니다.
Gauge Panel: 게이지 형태로 수치 데이터를 표시하는 패널입니다.
Table Panel: 표 형태로 데이터를 표시하는 패널입니다.
Text Panel: 문장 형태로 데이터를 표시하는 패널입니다.
Heatmap Panel: 열 지도 형태로 데이터를 시각화하는 패널입니다.

로그를 보기에 적합한 패널은 주로 Table Panel이나 Text Panel입니다. Table Panel은 표 형태로 로그를 보여주어 검색이 용이하며, Text Panel은 문장 형태로 로그를 보여주어 빠르게 파악할 수 있습니다


## Quest
* 우리의 웹 서버가 stdout으로 적절한 로그를 남기도록 해 보세요.
* ElasticSearch Service 클러스터를 작은 사양으로 하나 만들고, 도커 컨테이너의 stdout으로 출력된 로그가 ElasticSearch로 스트리밍 되도록 해 보세요.
* Grafana를 이용해 ElasticSearch의 로그를 실시간으로 볼 수 있는 페이지를 만들어 보세요.

## Advanced
* ElasticSearch와 Grafana는 어떤 라이센스로 배포되고 있을까요? AWS와 같은 클라우드 제공자들이 이러한 오픈소스를 서비스화 하는 것을 둘러싼 논란은 어떤 논점일까요?
