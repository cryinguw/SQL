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
