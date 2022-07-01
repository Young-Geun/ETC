### JDK 설치
> sudo yum install java-1.8.0-openjdk-devel   



### 대상 서버 포트 확인
> telnet [IP] [port]   
> Ex) telnet 192.0.0.1 8084       



### 도메인명으로 IP확인
> ping [Domain]   
> Ex) ping google.com    



### 포트 개방
> sudo iptables -I INPUT 1 -p tcp --dport [포트번호] -j ACCEPT   
> Ex) sudo iptables -I INPUT 1 -p tcp --dport 80 -j ACCEPT   
> Ex) sudo iptables -I INPUT 1 -p tcp --dport 443 -j ACCEPT   



### 방화벽
> - **시작**   
>   \- systemctl start firewalld   
> - **중지**   
>   \- systemctl stop firewalld    
> - **재시작**   
>   \- firewall-cmd --reload   
> - **구동 확인**   
>   \- systemctl status firewalld   
> - **서비스 추가**   
>   \- firewall-cmd --permanent --zone=public --add-service=http   
>   \- firewall-cmd --permanent --zone=public --add-service=https   
> - **포트 추가**   
>   \- firewall-cmd --permanent --zone=public --add-port=8073/tcp   
> - **확인**   
>   \- firewall-cmd --zone=public --list-all   



### MySQL 설치
> - **설치**   
>   \- yum -y install mysql-server   
> - **실행**   
>   \- systemctl start mysqld   
> - **실행 후 상태 확인**   
>   \- systemctl status mysqld   
> - **접속**   
>   \- mysql -u root -p   
> - **데이터베이스 목록 출력**   
>   \- show databases   
> - **데이터베이스 사용**   
>   \- use database_name   



### Maria DB 설치
> - **설치**   
>   \- yum install mariadb mariadb-server   
> - **설치확인**   
>   \- rpm -qa | grep -i mariadb   
> - **실행**   
>   \- systemctl start mariadb   
> - **실행 후 상태 확인**   
>   \- systemctl status mariadb      
> - **ROOT 비밀번호 설정**   
>   \- mysqladmin -u root password   
> - **부팅시 자동실행 설정**   
>   \- systemctl enable mariadb   
> - **접속**   
>   \- mysql -u root -p   
> - **Database 확인**   
>   \- show databases;   
> - **Database 사용**   
>   \- use 데이터베이스명;
> - **Table 확인**   
>   \- show tables;  



### MacOS 자바 설치 및 환경변수 설정
> - **설치**   
>   \- 생략   
> - **경로 복사**   
>   \- /Library/Java/JavaVirtualMachines/설치된 JDK버전/Contents/Home   
> - **경로 설정**   
>   \- vi ~/.bash_profile 입력 후  
>   \- export JAVA_HOME=/Library/Java/JavaVirtualMachines/설치된 JDK버전/Contents/Home   
> - **변경한 환경변수 적용**   
>   \- source ~/.bash_profile   
> - **확인**   
>   \- java -version   



### MacOS에서 SSH접속
> - **keygen 추가 생성**   
>   \- ssh-keygen -b 2048 -t rsa      
> - **생성된 키젠 추가**   
>   \- 생성된 키젠 중 xxx.pub파일의 내용을 클라우드 서버에 존재하는 .ssh/authorized_keys에 키 추가   
> - **개인키 권한 변경**   
>   \- chmod 600 [키경로]/[키이름]         
>   \- Ex) chmod 600 .ssh/id_rsa   
> - **접속**   
>   \- ssh -i [키경로]/[키이름] [유저명]@IP   
>   \- Ex) ssh -i /Users/choi/.ssh/id_rsa opc@123.123.123.123



### 실행 중인 포트 확인
> lsof -i :포트번호   
> Ex) lsof -i :8084  



### ls(파일 조회) 명령어 옵션   
>   \- l : 상세 조회   
>   \- a : 모든 파일 조회(숨김파일 확인 가능)   
>   \- r : 역순으로 조회   
>   \- R : 하위 디렉토리까지 조회   
>   \- t : 시간순으로 조회   
>   \- ltr : 날짜순으로 상세 조회   



### Alias 설정방법
> - **명령어를 통한 생성**   
>   \- alias 별명='명령어'   
>   \- Ex) alias boot_start='/home/opc/start.sh'   
>   \- * 명령어를 통한 생성은 시스템 재시작을 하게되면 초기화된다.   
>   \- * 'unalias 별명' 명령어를 통하여 삭제 가능하다.   
> - **.bash_profile에 정의하여 생성**   
>   \- ~/.bash_profile에 등록한다.   
>   \- Ex) vi .bash_profile 후에 alias boot_start='/home/opc/start.sh' 작성   
>   \- * 명령어 등록 후, 'source .bash_profile' 또는 '. .bash_profile' 명령어를 통해 적용 완료시킨다.   



### Apache 버전 확인
>   \- httpd -v (단, 설치된 경로에서 유효한 명령어. 설치된 경로를 확인하기 위해서는 'ps -ef | grep -i httpd' 명령어 실행하여 확인가능하다.)   
>   \- rpm -qa httpd   



### vi 편집기 단축키
> - **라인번호 표시**   
>   \- :set number   
> - **문자 검색**   
>   \- :/찾을 문자   
> - **문자 치환**   
>   \- :%s/[변경 대상 문자]/[변경할 문자]   
>   \- Ex) :%s/foo/bar (foo가 bar로 변경된다.)     



### tail
> - **실시간 표시**   
>   \- tail -f [파일명]   
>   \- Ex) tail -f exception.log   
>   \- Ex) tail -100f exception.log   
> - **여러 파일을 동시에 표시**   
>   \- tail -f [첫 번째 파일명] [두 번째 파일명]   
>   \- Ex) tail -f exception_admin.log exception_user.log   



### 문자가 포함된 파일 찾기
>   \- find [대상폴더] -name "[파일명].[확장자]" | xargs grep "[문자열]"   
>   \- Ex) find . -name "\*.\*" | xargs grep "123" (현재 디렉토리에서 문자 '123'이 포함된 파일 검색)   



### 디스크 용량 확인
> - **디렉토리에 속한 파일용량 확인**   
>   \- du -ah   
> - **디스크 사용량 확인**   
>   \- df -h   



### 시스템 종료 및 재부팅
> - **종료**   
>   \- shutdown -h now   
> - **재부팅**   
>   \- shutdown -r now



### 시간변경 
>   \- date -s "시:분:초"   
>   \- Ex) date -s "07:31:00"   
