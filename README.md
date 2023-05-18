# SQL

유데미 사이트에서 SQL강의를 듣고 공부한 내용을 정리했다.

`MySQL` 기준으로 작성했다.


 목차
- 데이터베이스, 테이블 만들기
  1. 데이터베이스 생성
  2. 데이터베이스 제거
  3. 데이터베이스 이용
  4. 테이블 작성
  5. 테이블 제거


- 데이터 삽입하기
  1. 데이터 삽입
* * *

## 데이터베이스, 테이블 만들기
### 1. 데이터베이스 생성

CLI를 시작

```sql
mysql-ctl cli; 
```

사용 가능한 데이터베이스를 나열.
```sql
show databases; 
```

데이터베이스 생성

```sql
CREATE DATABASE database_name; 
```

### 2. 데이터베이스 제거

```sql
DROP DATABASE database_name;
```

### 3. 데이터베이스 이용

```sql
USE database_name;
```

### 4. 테이블 작성

```sql
CREATE TABLE tablename
  (
    column_name data_type,
    column_name data_type
  );
```

ex)

```sql
CREATE TABLE cats
  (
    name VARCHAR(100),
    age INT
  );
```  
#### 데이터형 지정

##### INTEGER
정수를 넣는 데이터형 이다.

##### CHAR
문자열을 넣기 위한 데이터형이다. CHAR(10)이면 최대 길이가 10칸이다.

##### VARCHAR
가변문자열 형식으로 문자 수가 최대 길이보다 작아도 공백으로 채우지 않는다.

### 5. 테이블 제거

```sql
DROP TABLE tablename;
```

## 데이터 삽입하기
### 1. 데이터 삽입

```sql
INSERT INTO cats (name, age)
VALUES 
  ('Blue', 5);
  ('Jenkins', 7);
```

### 2. SELECT 확인

```sql
SELECT * FROM cats;
```
### 3. NOT NULL 생성

```sql
CREATE TABLE cats2 (
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL
);
```

### 4. 기본값(DEFAULT) 생성

```sql
CREATE TABLE cats3  (    
    name VARCHAR(20) DEFAULT 'no name provided',    
    age INT DEFAULT 99  
);

CREATE TABLE cats4  (
        name VARCHAR(20) NOT NULL DEFAULT 'unnamed',
        age INT NOT NULL DEFAULT 99
 );
 ```
 
 ### 5. 기본키 생성
 
 ```sql
 CREATE TABLE unique_cats2 (
	cat_id INT,
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL,
    PRIMARY KEY (cat_id)
);
```

## CRUD 명령
### 1. 데이터 준비

새로운 데이터를 만들기 위해 기존 테이블 정보를 삭제한다.

```sql
 DROP TABLE cats;
 
 CREATE TABLE cats (
    cat_id INT AUTO_INCREMENT,
    name VARCHAR(100),
    breed VARCHAR(100),
    age INT,
    PRIMARY KEY (cat_id)
  ); 
  
INSERT INTO cats(name, breed, age) 
VALUES ('Ringo', 'Tabby', 4),
       ('Cindy', 'Maine Coon', 10),
       ('Dumbledore', 'Maine Coon', 11),
       ('Egg', 'Persian', 4),
       ('Misty', 'Tabby', 13),
       ('George Michael', 'Ragdoll', 9),
       ('Jackson', 'Sphynx', 7);
 ```
 
 ### 2. SELECT 공식
 
 ```sql
 
 모든 열 :
 SELECT * FROM cats;
 
 age 열 :
 SELECT age FROM cats;
 
 age, breed 열 :
 SELECT name, breed FROM cats;
 ```
 
 ### 3. WHERE 기본
 
 ```sql
 SELECT * FROM cats WHERE age = 4;
 
 SELECT * FROM cats WHERE name ='Egg';
 ```
 
 ### 4. Alias 소개
 
 ```sql
  cat_id를 id로 출력 :
 SELECT cat_id AS id, name FROM cats;
 ```
 
 ### 5. UPDATE 명령
 ```sql
 
 Tabby -> Shothair :
 UPDATE cats SET breed='Shorthair' WHERE breed='Tabby';
 
 age 13 -> 14 :
 UPDATE cats SET age=14 WHERE name='Misty';
 
 ```
 
 ### 6. DELETE 소개
 ```sql
 DELETE FROM cats WHERE name='Egg';
 ```
 
 
