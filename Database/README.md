### Oracle Alias의 큰 따옴표 
> \- 공백을 포함할 때 사용할 수 있다.   
> \- 특수문자를 포함할 때 사용할 수 있다.   
> \- 대소문자를 구분할 때 사용할 수 있다.   


### Oracle ESCAPE
> \- LIKE 연산으로 '%' 나 '_' 가 포함된 문자를 검색하고자 할때 사용한다.   
> \- Ex) SELECT * FROM BOARD WHERE TITLE LIKE '%\\%%' ESCAPE '\\'   
> \- Ex) SELECT * FROM BOARD WHERE TITLE LIKE '%\\_%' ESCAPE '\\'   
