### JDK 설치
> sudo yum install java-1.8.0-openjdk-devel   



### 대상 서버 포트 확인
> telnet [IP] [port]   
> Ex) telnet 192.0.0.1 8084       



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


