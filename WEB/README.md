### Gradle 빌드
> ./gradlew clean build   



### 서비스 실행 및 프로필 선택 방법
> java -jar -Dspring.profiles.active=[프로필명] [jar명]   
> Ex) java -jar -Dspring.profiles.active=dev web-0.0.1-SNAPSHOT.jar   
> Ex) nohup java -jar -Dspring.profiles.active=dev web-0.0.1-SNAPSHOT.jar & (사용자가 로그아웃해도 백그라운드로 실행)  



### <script> 태그의 defer 속성   
> \- <script> 태그의 defer 속성은 페이지가 모두 로드된 후에 해당 외부 스크립트가 실행됨을 명시   
> \- 브라우저가 페이지의 파싱을 모두 끝내면 스크립트가 실행   
> Ex) <script src="/examples/common.js" defer></script>      
