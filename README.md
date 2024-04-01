# RealMySQL
RealMySQL 공부

## VSCode MySQL 설치
https://dev.mysql.com/doc/mysql-shell-gui/en/mysql-shell-for-vscode-setup.html

## 테스트 데이터
https://dev.mysql.com/doc/airportdb/en/airportdb-introduction.html

큰 데이터 파일, booking 테이블 5000만건 -> 
https://github.com/stefanproell/flughafendb


### 데이터 설치
``` bash
# 1. mysql shell 접속
 MySQL  Py > \connect {username}@{IPAddressOfMySQLDBSystemEndpoint}
 
# 2. 서버가 클라이언트의 로컬 파일 시스템에 있는 파일을 읽을 수 있도록
 MySQL  localhost:3306 ssl  Py > \sql
 MySQL  localhost:3306 ssl  SQL > set global local_infile=1
 Query OK, 0 rows affected (0.0003 sec)
 
# 3. load dump
 MySQL  localhost:3306 ssl  SQL > \py
 util.load_dump(r"{file path}\flughafendb_large", threads=16, deferTableIndexes="all", ignoreVersion=True)
```
