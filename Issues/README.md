### Mybatis Cache 이슈
>   \- 이슈내용 : 반복문 내에서 Sequence를 채번하여 Insert하려고 하였으나, 동일한 Sequence가 생성되는 이슈 발생   
>   \- 수정사항 : MyBatis XML에서 캐싱되지 않도록 옵션(useCache="false" flushCache="true") 추가   
>    ```java
>    <select id="QueryId" useCache="false" flushCache="true">
>       SELECT ...
>    </select>



### Mybatis 0 비교
>   \- 이슈내용 : 실수형 column1, column2의 값이 0일 때, column1 != ''와 column2 != '' 조건을 만족하여 0으로 업데이트 불가   
>    ```java
>    <update id="update">
>       update table
>       <set>
>           <if test="column1 != null and column1 != ''">
>               column1 = #{column1},
>           </if>
>           <if test="column2 != null and column2 != ''">
>               column2 = #{column2},
>           </if>
>       </set>
>       where column0 = #{column0}
>   </update>
>    ```
>   \- 수정사항 :  column1 != '' 대신에 column1.equals("") 사용 



### Mybatis - Invalid bound statement (not found)
>   \- 오류메시지 : org.apache.ibatis.binding.BindingException: Invalid bound statement (not found)   
>   \- 원인 1.  Repository의 메서드명과 Mapper.xml의 id가 일치하지 않는 경우  
>   \- 원인 2.  Mapper.xml의 경로가 잘못된 경우   



### POST 방식 데이터 소실 이슈   
>   \- 현상 : 다수의 데이터를 POST 방식으로 전달하여 처리하는 과정에서 일부 데이터가 처리되지 않는 현상 발생   
>   \- 오류메시지 : More than the maximum number of request parameters (GET plus POST) for a single request ([10,000]) were detected. Any parameters beyond this limit have been ignored.   
>   \- 원인 : 파라미터 갯수 또는 사이즈를 초과한 경우 발생   
>   \- 해결방안 : 톰캣 설정 중 maxPostSize와 maxParameterCount를 변경한다.   
