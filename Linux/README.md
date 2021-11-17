### JDK 설치
> sudo yum install java-1.8.0-openjdk-devel   



### 포트 개방
> sudo iptables -I INPUT 5 -i ens3 -p tcp --dport [포트번호] -m state --state NEW,ESTABLISHED -j ACCEPT   
> Ex) sudo iptables -I INPUT 5 -i ens3 -p tcp --dport 80 -m state --state NEW,ESTABLISHED -j ACCEPT   
> Ex) sudo iptables -I INPUT 5 -i ens3 -p tcp --dport 433 -m state --state NEW,ESTABLISHED -j ACCEPT   
