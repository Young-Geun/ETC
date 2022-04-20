### Oracle Alias의 큰 따옴표 
> \- 공백을 포함할 때 사용할 수 있다.   
> \- 특수문자를 포함할 때 사용할 수 있다.   
> \- 대소문자를 구분할 때 사용할 수 있다.   



### Oracle ESCAPE
> \- LIKE 연산으로 '%' 나 '_' 가 포함된 문자를 검색하고자 할때 사용한다.   
> \- Ex) SELECT * FROM BOARD WHERE TITLE LIKE '%\\%%' ESCAPE '\\'   
> \- Ex) SELECT * FROM BOARD WHERE TITLE LIKE '%\\_%' ESCAPE '\\'   



### Oracle 테이블 및 컬럼 조회
> - **테이블 목록 조회(전체계정)**   
>   \- SELECT * FROM all_all_tables   
>   \- SELECT * FROM dba_tables   
>   \- SELECT * FROM all_objects WHERE object_type = 'TABLE'   
> - **테이블 목록 조회(접속계정)**   
>   \- SELECT * FROM tabs   
>   \- SELECT * FROM user_tables   
>   \- SELECT * FROM user_objects WHERE object_type = 'TABLE'   
> - **테이블 코멘트 조회(전체계정)**   
>   \- SELECT * FROM all_tab_comments   
> - **테이블 코멘트 조회(접속계정)**   
>   \- SELECT * FROM user_tab_comments   
> - **컬럼 목록 조회(전체계정)**   
>   \- SELECT * FROM all_tab_columns   
> - **컬럼 목록 조회(접속계정)**   
>   \- SELECT * FROM user_tab_columns   
> - **컬럼 코멘트 조회(전체계정)**   
>   \- SELECT * FROM all_col_comments   
> - **컬럼 코멘트 조회(접속계정)**   
>   \- SELECT * FROM user_col_comments   



### Oracle 시퀀스 조회
> - **생성된 시퀀스 조회**   
>   \- SELECT * FROM user_sequences   
> - **현재 시퀀스 조회**   
>   \- SELECT 시퀀스명.currval FROM dual   
>   \- (*참고. nextval을 실행 후, 같은 세션동안만 사용 가능하다.)   
> - **다음 시퀀스 확인**   
>   \- SELECT 시퀀스명.nextval FROM dual   



### 중복 데이터조회
> \- SELECT COL1, COUNT(\*) FROM TABLE_NAME GROUP BY COL1 HAVING COUNT(\*) > 1;   
> \- SELECT COL1, COL2, COUNT(\*) FROM TABLE_NAME GROUP BY COL1, COL2 HAVING COUNT(\*) > 1;   



### Oracle 난수 생성
> - **랜덤 숫자**   
>   \- SELECT TRUNC(DBMS_RANDOM.VALUE(1, 1000)) FROM DUAL      
> - **랜덤 문자**   
>   \- SELECT DBMS_RANDOM.STRING('U', 10) FROM DUAL   
>   \- U=(대문자), L=(소문자), A=(대, 소문자 혼용), X=(영어, 숫자 혼용), P=(특수문자 포함 모두 혼용)   
