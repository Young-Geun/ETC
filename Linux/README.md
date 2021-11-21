### JDK 설치
> sudo yum install java-1.8.0-openjdk-devel   



### 포트 개방
> sudo iptables -I INPUT 5 -i ens3 -p tcp --dport [포트번호] -m state --state NEW,ESTABLISHED -j ACCEPT   
> Ex) sudo iptables -I INPUT 5 -i ens3 -p tcp --dport 80 -m state --state NEW,ESTABLISHED -j ACCEPT   
> Ex) sudo iptables -I INPUT 5 -i ens3 -p tcp --dport 433 -m state --state NEW,ESTABLISHED -j ACCEPT   



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
