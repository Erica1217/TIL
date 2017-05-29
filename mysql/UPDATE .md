# UPDATE
```sql
UPDATE 테이블명, 테이블명 set 필드명 = 값
where 조건문
```

# Example
```sql
UPDATE words, onekill set one_kill=1
where onekill.startLetter = right(words.word,1)
or startLetter = do_eum;
```
실제로 쓴 구문이다. 하고싶었던 일은 words필드의 첫 글자가 onekill테이블의 startLetter필드에 있으면 그 words테이블의 one_kill필드를 1로 바꾸는 것이다.

# select를 이용한 update
```sql
UPDATE words set one_kill=1
where not exists
(select word from onekill, words 
where onekill.startLetter = right(words.word,1)
or startLetter = do_eum);
```

# JOIN을 이용한 update
```sql
SELECT A.name, B.toy
FROM  words A
LEFT OUTER JOIN onekill B
ON A.id = B.id;
```
- 왼쪽 외부 조인
- 왼쪽 테이블의 모든 행을 가지고 오른쪽 테이블 행과 비교
- 조건에 맞는 값이 오른쪽에 없으면 NULL값이 셀에 출력된다.

# INNER JOIN을 이용한 update
```sql
UPDATE Words w INNER JOIN oneKill o
ON right(w.one_kill,1) = o.startLetter
SET one_kill=0;
```