# 파일 데이터 insert 하기
```
  LOAD DATA INFILE '파일 경로'
  
  INTO TABLE 테이블명

  FIELDS TERMINATED BY '구분자' //컬럼간 구분자

  LINES TERMINATED BY '구분자' //라인간 구분자

  IGNORE 1 LINES // 첫번째 행은 무시한다

  (word) //추가할 컬럼명을 차례대로

  SET category=2; // category 컬럼에는 모두 2를 넣음
  ```
  윈도우에서는 줄바꿈이 '\r\n', 리눅스에서는 '\n'임을 기억할 것.

# category
adverb 부사 : 1 <br>
interjection 감탄사 : 2<br>
pronoun 대명사 : 3<br>
root 어근 : 4 <br>
special 특수어 :  5 <br>
substantive 체언 : 6 <br>

# 부사
```
LOAD DATA INFILE 'D:/DB/adverb_detail.txt' REPLACE INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=1;
```

```
LOAD DATA INFILE 'D:/DB/interjection_basic.txt' REPLACE INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=2;
```

LOAD DATA INFILE 'D:/DB/test.txt' INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=2;

# 감탄사 
```
LOAD DATA INFILE 'D:/DB/interjection_detail.txt' REPLACE INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=2;
```

# 대명사
```
LOAD DATA INFILE 'D:/DB/pronoun_detail.txt' REPLACE INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=3;
```

# 어근
```
LOAD DATA INFILE 'D:/DB/root_detail.txt' REPLACE INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=4;
```

# 특수어
```
LOAD DATA INFILE 'D:/DB/special_detail.txt' REPLACE INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=5;
```

# 체언
```
LOAD DATA INFILE 'D:/DB/substantive_detail.txt' REPLACE INTO TABLE words
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\r\n\r\n'
IGNORE 1 LINES
(word)
SET 
category=6;
```

# 특정 글자수보다 작으면 삭제
```
delete from 테이블명
WHERE CHAR_LENGTH(컬럼이름)<=특정 컬럼 수;
```

