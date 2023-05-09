# Quest 11. RDB의 기초와 ORM

## Introduction
* 이번 퀘스트에서는 데이터베이스를 다루는 방법에 대해 알아보겠습니다.

## Topics
* RDBMS
* MySQL
* ORM
* Hash
  * scrypt

## Resources
* [MySQL 101 – The basics](https://www.globo.tech/learning-center/mysql-101-basics/)
* [Sequelize](https://sequelize.org/)
* [안전한 패스워드 저장](https://d2.naver.com/helloworld/318732)

## Checklist
* RDBMS 테이블의 정규화는 무엇인가요?
- 관계형 데이터베이스에서 테이블을 설계할 때 중복을 최소화하고 데이터를 논리적으로 구조화하는 과정을 정규화(Normalization)라고 합니다. 이를 통해 데이터의 일관성과 무결성을 보장할 수 있으며, 효율적인 쿼리 처리와 데이터 저장 공간의 절약을 이끌어냅니다.

* MySQL 외의 RDB에는 어떤 것들이 있나요?
- Oracle Database
Microsoft SQL Server
PostgreSQL
IBM DB2
SQLite
가 있습니다

  * Relational Database 외에 다른 DB에는 어떤 것들이 있을까요?
  - 
  NoSQL Database
  Graph Database
  Document-oriented Database
  Key-value Database
  Time-series Database
  Object-oriented Database

* RDBMS에서 테이블의 인덱싱은 무엇인가요? 인덱싱을 하면 어떤 점이 다르며, 어떤 식으로 동작하나요?
- RDBMS에서 테이블의 인덱싱은 테이블의 특정 열(column)에 대해 검색을 빠르게 하기 위해 사용되는 기술입니다. 인덱스를 사용하면 RDBMS가 전체 테이블을 검색하는 것이 아니라 인덱싱된 열을 기반으로 빠르게 검색할 수 있습니다.
인덱스는 데이터베이스에 저장된 실제 데이터가 아니라 인덱스 테이블(index table)에 저장됩니다. 인덱스 테이블은 테이블의 각 행(row)에 대한 포인터(pointer)와 해당 행의 값(value)을 저장합니다. 검색 시 RDBMS는 인덱스 테이블을 먼저 검색하고, 인덱스 테이블에서 해당 값(value)이 위치한 행(row)의 포인터(pointer)를 참조하여 해당 행(row)을 가져오는 방식으로 동작합니다.

* ORM을 사용하는 것은 사용하지 않는 것에 비해 어떤 장단점을 가지고 있나요?
- 장점: SQL 쿼리를 직접 작성하는 것보다 ORM을 사용하면 쉽고 빠르게 데이터베이스와 상호작용할 수 있다
 객체와 데이터베이스 간의 매핑을 쉽게 제공하기 때문에, 개발자들이 보다 객체지향적인 코드를 작성할 수 있다
 데이터베이스와의 상호작용을 추상화하고, 특정 데이터베이스에 종속되지 않으므로, 애플리케이션을 다른 데이터베이스로 전환하는 것이 상대적으로 쉽다

 단점:
 ORM을 사용하면 데이터베이스와의 상호작용이 일어날 때마다 오버헤드가 발생합니다. 이는 성능 저하의 원인이 될 수 있다
 개발자가 SQL 쿼리를 작성하지 않기 때문에, 데이터베이스의 성능을 최적화하는 작업이 어려울 수 있다
 개발자가 작성한 객체와 데이터베이스 간의 매핑을 추상화하기 때문에, 데이터베이스의 특정 기능을 사용하기 위해 ORM을 우회하여 SQL 쿼리를 작성해야 하는 경우가 있을 수 있다

  * 자바스크립트 생태계의 ORM에는 어떤 것들이 있나요?
  -  MySQL, PostgreSQL, SQLite, MSSQL과 같은 RDBMS
  TypeORM: TypeScript와 함께 사용할 수 있는 ORM으로, MySQL, PostgreSQL, SQLite, MSSQL과 같은 RDBMS를 지원
  Mongoose: MongoDB를 위한 ODM(Object Data Modeling) 라이브러리로, MongoDB에서 동작
  Waterline: NoSQL, RDBMS 등 다양한 데이터베이스를 위한 ORM
  Objection.js: SQLite, MySQL, Postgres 및 MSSQL과 같은 RDBMS를 지원하는 ORM이며, 트랜잭션, 리버스 엔지니어링 등을 지원

* 모델간의 1:1, 1:N, N:M 관계는 각각 무엇이고 어떨 때 사용하나요?
- 1:1 관계: 한 모델의 인스턴스가 다른 모델의 인스턴스와 하나씩 매칭되는 관계. 보통 대상 모델의 프로필 정보, 설정 정보 등을 저장하는 데 사용
1:N 관계: 한 모델의 인스턴스가 다른 모델의 여러 인스턴스와 매칭되는 관계. 보통 대상 모델의 소유자 역할을 하는 모델에 사용
N:M 관계: 한 모델의 인스턴스가 다른 모델의 여러 인스턴스와 매칭되며, 대상 모델의 여러 인스턴스가 여러 모델의 인스턴스와 매칭될 수 있는 관계. 

* DB에 사용자의 암호를 평문으로 저장하지 않고도 사용자의 암호를 인증하는 것이 가능한 이유는 무엇일까요?
- 대표적으로 해시함수를 사용한 방법이 있는데, 해시 함수는 임의의 길이의 데이터를 고정된 길이의 데이터로 매핑하는 함수입니다. 이때, 같은 입력값은 항상 같은 출력값을 가지며, 출력값에서 입력값을 역추적할 수는 없습니다. 이를 이용하여 사용자의 암호를 DB에 저장하기 전에 암호를 해싱하여 저장하고, 로그인 시에는 입력받은 암호를 같은 방식으로 해싱하여 DB에 저장된 해시값과 비교하는 방식으로 인증할 수 있음

  * 해시 함수에는 어떤 것이 있나요?
  - 여러 종류가 있으나 대표적으로 사용되는 것은 MD5, SHA, bcrypt가 있습니다

  * ?사용자의 암호를 해싱하여 저장할 때 어떤 식으로 저장하는 것이 보안에 좋을까요?
  - 솔트(salt), 안전한 해시함수를 사용하거나, 암호화 반복을 적용시키는 것이 보안에 좋다.


## Quest
* 이번에는 메모장을 파일이 아닌 DB기반으로 만들어 보고자 합니다.
  * 적절한 테이블을 설계해 보세요.
  * Sequelize를 이용하여 데이터의 모델을 만들고 어플리케이션에 적용해 보세요.
  * 사용자의 비밀번호는 해싱을 통해 저장되어야 합니다.

## Advanced
* Object–relational impedance mismatch란 어떤 개념인가요?
* Foreign Key란 무엇인가요? 이것을 사용할 때의 장점과 단점은 무엇일까요?
* 이전에 쓰이던 해시함수들에는 어떤 것이 있을까요? 패스워드 해싱의 추세의 역사는 어떻게 이어져왔나요?
