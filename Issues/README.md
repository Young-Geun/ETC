### Mybatis Cache 이슈
>   \- 이슈내용 : 반복문 내에서 Sequence를 채번하여 Insert하려고 하였으나, 동일한 Sequence가 생성되는 이슈 발생   
>   \- 수정사항 : MyBatis XML에서 캐싱되지 않도록 옵션(useCache="false" flushCache="true") 추가   
>    ```java
>    <select id="QueryId" useCache="false" flushCache="true">
>       SELECT ...
>    </select>
