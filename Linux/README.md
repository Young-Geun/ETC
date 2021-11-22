### JDK 설치
> sudo yum install java-1.8.0-openjdk-devel   



### 포트 개방
> sudo iptables -I INPUT 5 -i ens3 -p tcp --dport [포트번호] -m state --state NEW,ESTABLISHED -j ACCEPT   
> Ex) sudo iptables -I INPUT 5 -i ens3 -p tcp --dport 80 -m state --state NEW,ESTABLISHED -j ACCEPT   
> Ex) sudo iptables -I INPUT 5 -i ens3 -p tcp --dport 433 -m state --state NEW,ESTABLISHED -j ACCEPT   



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
