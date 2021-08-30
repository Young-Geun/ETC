# Linux

### 소유권 관련 명령어
> - **chown**   
>   \- 파일과 디렉토리의 사용자 소유권과 그룹소유권을 변경   
>   \- chown [옵션] 소유자[:그룹명] 파일명   
>   \- 옵션 -R : 하위 디렉토리를 포함하여 모든 파일의 소유권 변경   
> - **chgrp**   
>   \- 파일과 디렉토리의 그룹 소유권을 변경   
>   \- chgrp [옵션] 그룹명 파일명   
>   \- 옵션 -R : 하위 디렉토리를 포함하여 모든 파일의 소유권 변경   

### 디스크 쿼터
> - **quota**   
>   \- 사용자 할당량 사용   
> - **edquota**   
>   \- 편집기를 이용하여 사용자나 그룹에 디스크 사용량을 할당
> - **setquota**   
>   \- 편집기 기반이 아닌 명령행에서 직접 사용자나 그룹에 디스크 사용량을 할당
> - **quotacheck**   
>   \- 파일 시스템의 디스크 사용 상태를 검색
> - **repquota**   
>   \- 특정 파일 시스템 내의 각 사용자별 디스크 사용량에 대한 내용 확인   
> - **실행순서**   
>   \- quotacheck > edquota > quotaon > repquota

### 네트워크 파일 시스템
> - **SMB**   
>   \- 삼바 파일 시스템을 마운트 지정   
>   \- 리눅스, 유닉스 OS와 윈도우 OS와의 자료 및 하드웨어 공유   
> - **CIFS**   
>   \- SMB를 확장한 파일 시스템   
>   \- SMB를 기초로 응용하여 라우터를 뛰어넘어 연결할 수 있는 프로토콜
> - **NFS**   
>   \- 네트워크 파일 시스템   
>   \- 썬마이크로시스템이 개발한 네트워크 공유 프로토콜   

### 파일 시스템 관련 명령어
> - **mount**   
>   \- 특정 디바이스를 특정 디렉토리처럼 사용하기 위해 장치와 디렉토리를 연결    
>   \- mount -t [파일 시스템 타입] [장치 파일] [마운트 포인트]   
>   [파일 시스템 타입] 시디롬 : iso9660   
>   [파일 시스템 타입] ms-dos : msdos   
>   [파일 시스템 타입] windowsXP : ntfs   
>   [파일 시스템 타입] ISO파일 : loop   
>   [파일 시스템 타입] NFS파일 : nfs   
>   [파일 시스템 타입] 삼바 : smbfs   
> - **umount**   
>   \- 마운트 해제 명령어    
> - **eject**   
>   \- 이동식 보조기억장치(DVD 또는 CD-ROM)를 해제하고 장치를 제거   
> - **fdisk**   
>   \- 새로운 파티션 생성, 기존 파티션 삭제, 파티션 타입 결정   
>   \- l : 현재 디스크 및 파티션 보기   
>   \- n : 신규파티션 추가   
>   \- t : 파티션 종류 변경 (82=스왑 파티션 / 83=리눅스 파티션 / 8e=논리 볼륨 관리자 파티션 / fd=Linux RAID)   
>   \- p : 파티션 설정 보기   
>   \- m : 메뉴보기   
>   \- a : 부트가능 플래그로 변경   
>   \- d : 파티션 삭제   
>   \- w : 파티션 설정 저장   
> - **mkfs**   
>   \- 리눅스 파일 시스템 생성
>   \- fdisk로 하드디스크의 파티션을 나눈 후, 해당 파티션에 맞는 파일 시스템을 생성
> - **fsck**   
>   \- 파일 시스템의 무결성 체크, 대화식으로 복구   
> - **e2fsck**   
>   \- ext2, ext3, ext4 타입의 파일 시스템을 점검 및 복구
> - **df**   
>   \- 마운트된 하드 디스크의 용량을 파티션 단위로 사용량 확인   
>   \- df -i 또는 df inode : 파티션에 사용가능한 아이노드(I-node)의 수를 확인   
> - **du**   
>   \- 디렉토리별 디스크 사용량 확인

### /etc/fstab
> - **파일 시스템 장치명**   
>   \- 장치명, 볼륨라벨, UUID
> - **마운트 포인트**   
>   \- 파일 시스템이 마운트될 위치
> - **파일 시스템 종류**   
>   \- 파일 시스템 종류 설정
> - **옵션**   
>   \- defaults : auto, exec, suid, ro, rw 등 모두 가지는 속성   
>   \- auto : 부팅 시 자동 마운트    
>   \- exec : 실행 파일이 실행되는 것을 허용   
>   \- suid : SetUID, SetGID 사용을 허용   
>   \- ro : 읽기 전용   
>   \- rw : 읽고 쓰기   
> - **dump 관련 설정**   
>   \- 백업 시 덤프 레벨을 결정
> - **파일 점검 옵션**   
>   \- 부팅 시 파일 시스템을 점검하는 fsck 순서

### Shell
> - **Bourne Shell(sh)**   
>   \- 스티브 본이 개발   
>   \- 유닉스에서 기본 셸로 사용   
> - **Korn Shell(ksh)**   
>   \- 데이비드 콘이 개발   
>   \- 벨 연구소에서 본셸을 확장해서 만듦   
>   \- 명령어 완성 기능, 히스토리 기능 지원   
> - **Bourne Again Shell(bash)**   
>   \- 브라이언 폭스가 개발   
>   \- 리눅스 표준 셸로 채택   
>   \- POSIX와 호환      
>   \- 명령어 완성 기능, 히스토리, 명령어 치환, 편집 등 기능 지원      
> - **C Shell(csh)**   
>   \- 빌 조이가 개발   
>   \- C언어의 특징을 많이 포함   
>   \- 히스토리, 별명, 작업 제어 등의 기능 지원    
> - **TC Shell(tcsh)**   
>   \- Ken Greer가 개발   
>   \- 확장 C셸로 BSD계열에서 가장 많이 사용   
>   \- 자동 완성 기능, 자동 로그아웃, 로그인 상태, 사용자, 터미널 모니터링 등 지원   
> - **Shell 확인**   
>   \- /etc/shells 확인(Ex. cat /etc/shells)   
>   \- /etc/passwd 파일 확인   
>   \- echo $SHELL   
>   \- chsh -l(-s 옵션은 셸 변경)   

### 환경 변수
> - **PATH**   
>   \- 실행할 명령어 경로 검색
> - **HOME**   
>   \- 사용자의 홈 디렉토리 절대 경로
> - **HOSTNAME**   
>   \- 호스트명
> - **USER**   
>   \- 사용자명
> - **DISPLAY**   
>   \- X 응용 프로그램이 화면 출력을 위해 접속할 X 서버의 주소를 지정
> - **PS1**   
>   \- 셸 프롬프트를 선언 시 사용하는 변수
> - **PS2**   
>   \- 2차 셸 프롬프트를 선언 시 사용하는 변수
> - **PWD**   
>   \- 현재 디렉토리의 절대 경로명
> - **SHELL**   
>   \- 로그인 셸의 절대 경로명
> - **TERM**   
>   \- 터미널 종류의 이름
> - **TMOUT**   
>   \- 로그아웃 관련 시간
> - **LANG**   
>   \- 프로그램 기본 언어
> - **PRINT**   
>   \- 기본 프린터
> - **MAIL**   
>   \- 메일 저장 경로

### bash 관련 설정 파일
> - **/etc/profile**   
>   \- 전체 사용자의 셸 환경을 제어하는 전역 설정 파일
> - **/etc/bashrc**   
>   \- 별칭과 bash수행 시 실행되는 함수를 전역적으로 제어
> - **~/.bash_profile**   
>   \- 개인 사용자의 셸 환경을 제어하는 지역 설정 파일
> - **~/.bash_history**   
>   \- 입력한 명령어 기록
> - **~/.bashrc**   
>   \- 별칭과 bash수행 시 실행되는 함수를 지역적으로 제어
> - **~/.bash_logout**   
>   \- 로그아웃하기 직전에 실행되는 시스템 설정

### alias
>   \- 자주 사용하는 명령어를 특정 문자로 저장하여 간편하게 사용   
>   \- 설정 : alias 별명='명령어'   
>   \- 해제 : unalias 별명   

### 프로세스
> - **유형**   
>   \- 포그라운드 : 사용자와 상호작용하는 프로세스   
>   \- 백그라운드 : 사용자와 직접적인 대화를 하지 않고 뒤에서 실행되는 프로세스      
> - **fork()와 exec()**   
>   \- fork() : 새로운 프로세스를 위해 메모리를 할당받아 복사본 형태의 프로세스를 실행   
>   \- exec() : 새로운 프로세스를 위해 메모리를 할당하지 않고 호출한 프로세스의 메모리에 새로운 프로세스를 덮어씌움   
> - **데몬**   
>   \- 메모리 상주하며 사용자의 요청이 오면 즉시 실행되는 대기 중인 서버 프로세스      
>   \- 주기적이고지속적인 서비스 요청을 처리하기 위해 실행   
>   \- standalone : 항상 메모리에 상주. 빠른 응답속도를 요하는 경우에 사용. 서버 부하가 큼   
>   \- inetd : 호출 시점에 메모리에 상주      

### 시그널
> - **SIGHUP(1)**   
>   \- 터미널과 연결이 끊어졌을 때
> - **SIGINT(2)**   
>   \- Ctrl + C
> - **SIGQUIT(3)**   
>   \- Ctrl + \
> - **SIGKILL(9)**   
>   \- 프로세스 강제 종료
> - **SIGTERM(15)**   
>   \- KILL 시스템 호출
> - **SIGTSTP(20)**   
>   \- Ctrl + Z

### 프로세스 관련 명령어
> - **ps**   
>   \- 현재 실행 중인 프로세스 상태 확인
> - **ps aux**   
>   \- USER : 프로세스 소유자명   
>   \- PID : 프로세스 식별번호   
>   \- %CPU : CPU 사용 비율(추정치)   
>   \- %MEM : 메모리 사용 비율(추정치)   
>   \- VSZ : 가상메모리 사용량   
>   \- RSS : 실제 사용된 메모리량   
>   \- TTY : 프로세스와 연결된 터미널 번호   
>   \- STAT : 현재 프로세스 상태   
>   \- START : 프로세스 시작 시간   
>   \- TIME : 총 CPU 사용 시간   
>   \- COMMAND : 실행 명령   
> - **pstree**   
>   \- 실행 중인 프로세스들을 트리구조로 표현   
> - **jobs**   
>   \- 작업 중지, 백그라운드 진행, 변경되었지만 보고되지 않은 상태 등을 표시
> - **bg**   
>   \- 포그라운드에서 백그라운드로 전환   
>   \- bg %작업번호 또는 bg 작업번호   
> - **fg**   
>   \- 백그라운드에서 포그라운드로 전환   
>   \- fg %작업번호 또는 fg 작업번호   
> - **kill**   
>   \- 프로세스 종료   
>   \- kill [옵션] [시그널 번호 또는 시그널 이름] [PID 또는 %작업번호]
> - **killall**   
>   \- 같은 데몬의 여러 프로세스 종료   
>   \- killall [옵션] 프로세스명
> - **nice**   
>   \- 프로세스 우선 순위 변경(프로세스명 입력)   
>   \- 범위 : -20(높은 우선권) ~ 19(낮은 우선권)
> - **renice**   
>   \- 실행 중인 프로세스 우선 순위 변경(PID값 입력)   
> - **top**   
>   \- 운영 상태를 실시간으로 모니터링
> - **nohup**   
>   \- 사용자가 로그아웃하거나 터미널 창을 닫아도 실행 중인 프로세스를 백그라운드로 실행(단, 명령어 뒤에 &로 명시)   

### 스케줄링
> - **at**   
>   \- 지정된 명령어나 스크립트를 한 번만 자동 예약 후 실행   
> - **crontab**   
>   \- 정해진 시간에 주기적으로 실행   
>   \- 포맷 : * * * * * ./etc/observe.sh   
>   \- 의미 : 분 / 시간 / 일 / 월 / 요일
>   \- 옵션   
>      l : crontab에 설정된 내용 출력   
>      e : crontab을 작성하거나 수정   
>      r : crontab 내용 삭제   
>      u : 특정 사용자의 일정 수정   

### 에디터
> - **vi**   
>   \- 빌조이 개발   
>   \- 리눅스 배포판과 유닉스에 기본적으로 포함   
>   \- 모드형 편집기      
>   \- 입력모드 : a, i, o, s         
>   \- 명령모드 : 삭제, 복사, 붙여넣기 가능         
>   \- EX 명령모드 : 저장, 종료, 환경설정         
> - **vim**   
>   \- 브람 무레나르 개발   
>   \- 편집 시 다양한 색상을 이용하여 가시성을 높일 수 있음   
>   \- 패턴 검색시 하이라이트 기능 제공  
>   \- 다중 되돌리기 기능     
>   \- 문법 검사 기능   
> - **pico**   
>   \- Aboil Kasar 개발   
>   \- 초기 리눅스에서 사용      
>   \- 기능이 부족하고 업데이트가 지원 부족   
> - **emacs**   
>   \- 리차드 스톨만이 최초의 개발자이며 제임스 고슬링이 다양한 기능 추가   
>   \- 비모드형 편집기로 여러 가지 명령 수행을 위하여 Ctrl 또는 Alt 키와 조합하여 사용      

### rpm
>   \- rpm -i : 새로운 패키지를 설치할 때 사용   
>   \- rpm -U : 기존의 패키지를 새로운 버전의 패키지로 업그레이드할 때 사용(설치된 패키지가 없을 경우 패키지를 설치)   
>   \- rpm -v : 메시지를 자세하게 출력   
>   \- rpm -h : '#'기호로 표시   
>   \- rpm -e(--erase) : 지정한 패키지 제거   
>   \- rpm --nodeps : 의존성이 있는 패키지가 존재할 경우에도 제거   
>   \- rpm -qa : 설치된 패키지에서 지정한 문자열이 포함된 패키지 출력   
>   \- rpm -qi : 패키지 이름과 버전만 표시/설치된 패키지 정보를 출력   
>   \- rpm -qd: vsftpd 관련 문서 및 man 페이지 파일 정보를 출력   
>   \- rpm -qa : 설치된 패키지에서 지정한 문자열이 포함된 패키지 출력   

### yum
>   \- yum list : 전체 패키지에 대한 정보를 출력   
>   \- yum install 패키지명 : 패키지 설치   
>   \- yum remove 패키지명 : 지정한 패키지 제거   
>   \- yum history 패키지명 : 패키지 설치, 삭제 등 작업 이력 확인   
>   \- yum info 그룹 또는 패키지 : 패키지 또는 그룹의 패키지를 자세하게 확인   

### 패키지별 삭제 옵션
>   \- rpm : -e   
>   \- apt-get : remove   
>   \- dpkg : r(시스템에서 삭제), p(패키지기반 모두 삭제), --purge(완전 제거)   
>   \- yum : remove   

### tar
>   \- c : 아카이브 생성   
>   \- r : 아카이브의 마지막에 파일들 추가   
>   \- x : 아카이브 풀기   
>   \- t : 아카이브에 포함된 내용 확인   
>   \- v : 처리 과정 출력   
>   \- f : 대상 아카이브 지정   
>   \- z : gzip으로 압축하거나 해제   
>   \- j : bzip2로 압축하거나 해제   
>   \- J : xz로 압축하거나 해제   

### 소스파일 설치 순서
>   \- configure > make > make install   
>   \- cmake > make install   

### 압축률
>   \- 압축률 낮은 순 : compress(.Z) -> gzip(.gz) -> bzip2(.bz2) -> xz(.xz)

### 프린터
> - **LPRng**   
>   \- 버클리 프린팅 시스템   
>   \- 프린터 스풀링과 네트워크 프린터 서비스 지원       
> - **CUPS**   
>   \- 애플이 개발한 오픈소스 프린팅 시스템   
>   \- HTTP 기반의 IPP를 사용    
>   \- /etc/cups/cupsd.conf : 프린터 데몬의 환경 설정 파일   
>   \- /etc/cups/printers.conf : 프린터 큐 관련 환경 설정 파일   
>   \- /etc/cups/classes.conf : 프린터 데몬의 클래스 설정 파일   
>   \- cupsd : 프린터 데몬     

### 프린터 명령어
> - **BSD**   
>   \- lpr : 프린터 작업 요청       
>   \- lpq : 프린터 큐에 있는 작업 목록 출력      
>   \- lprm : 큐에 대기 중인 작업 삭제   
>   \- lpc : 프린터나 프린터 큐 제어     
> - **System V**   
>   \- lp : 프린터 작업 요청      
>   \- lpstat : 프린터 큐 상태 확인      
>   \- cancle : 프린트 작업 취소      

### X-WINDOW
> - **윈도우 매니저**   
>   \- X Window 상에서 창의 배치와 표현을 담당   
>   \- 창 열기와 닫기, 창의 생성 위치, 창 크기 조정, 창의 외양과 테두리를 변경 가능  
> - **데스크톱 환경**   
>   \- GUI 사용자에게 제공하는 인터페이스 스타일로 데스크톱 관리자라고도 불림   
>   \- 윈도우 매니저,파일관리자,도움말, 제어판 등 다양한 도구를 제공하는 패키지 형태의 프로그램    
> - **디스플레이 매니저**   
>   \- 로컬 또는 리모트 컴퓨터의 X Server의 접속과 세션 시작을 담당   
>   \- 사용자에게 그래픽 로그인 화면을 띄워주고 아이디와 패스워드를 입력받아 인증을 진행하고, 인증이 완료되면 세션을 시작      

### 네트워크 타입
> - **LAN**   
>   \- 근접한 거리의 건물에 설치된 정보 기기들 사이의 고속 통신을 제공하는 통신망   
> - **MAN**   
>   \- 도시나 지역 사회와 같은 도시권 통신망  
> - **WAN**   
>   \- 국가, 대륙 등과 같이 넓은 지역을 연결하는 통신망   

### LAN 구성 방식
> - **성형(스타형)**   
>   \- 중앙 컴퓨터에 여러 대의 컴퓨터가 연결된 형태   
>   \- 확장 용이   
>   \- 중앙 컴퓨터 고장 시 전체 네트워크 사용 불가    
> - **망형**   
>   \- 모든 노드가 서로 일대일로 연결된 형태   
>   \- 대량의 데이터를 송수신할 경우 적합   
>   \- 장애 발생 시 다른 시스템에 영향이 적음   
>   \- 회선 구축 비용이 많이 듦   
> - **버스형**   
>   \- 하나의 통신회선에 여러 컴퓨터가 연결된 형태   
>   \- 연결된 컴퓨터 수에 따라 네트워크 성능이 변동   
>   \- 단말기 추가 및 제거가 용이하며 설치 비용이 저렴   
>   \- 노드 수 증가 시 트래픽 증가로 병목현상 발생, 성능 저하 초래   
>   \- 문제가 발생한 노드의 위치를 파악하기 어려움   
> - **링형**   
>   \- 각 노드가 좌우의 인접한 노드와 연결되어 원형을 이룬 형태   
>   \- 앞의 컴퓨터로부터 수신한 내용을 다음 컴퓨터로 재전송하는 방식   
>   \- 노드 숫자가 증가하더라도 망 성능의 저하가 적음   
>   \- 논리적인 순환형 토폴로지로 하나의 노드장애가 전체 토폴로지에 영향   
>   \- 노드의 추가 및 삭제가 용이하지 않음   
> - **트리형**   
>   \- 버스형과 성형토폴로지의 확장 형태   
>   \- 트래픽 양 증가 시 병목 현상의 가능성 증대   

### OSI 7 모델
>   \- 순서 : 물리 > 데이터링크 > 네트워크 > 전송 > 세션 > 표현 > 응용
> - **물리 계층**   
>   \- 물리적인 연결   
>   \- 전기적, 기계적, 기능적 절차적인 수단 제공   
>   \- 데이터 전송 단위 : bits   
> - **데이터링크 계층**   
>   \- 데이터 전송을 위한 형식 결정   
>   \- 오류 검출 기능 제공   
>   \- 데이터 전송 단위 : frames   
> - **네트워크 계층**   
>   \- 논리적인 주소를 사용   
>   \- 경로 관리, 최적 경로 결정   
>   \- 데이터 전송 단위 : packets   
> - **전송 계층**   
>   \- 종단 간 연결   
>   \- 응용 계층 사이에 논리적인 통로 제공   
>   \- 데이터 전송 단위 : segments   
> - **세션 계층**   
>   \- 종단 간 애플리케이션의 연결 설정, 유지, 해제
>   \- 응용 프로그램 간의 통신을 관리하기 위한 방법과 동기화를 유지하는 서비스 제공   
> - **표현 계층**   
>   \- 부호화, 압축, 암호화   
> - **응용 계층**   
>   \- 네트워크 서비스를 제공하기 위해 UI 제공

### TCP/IP
>   \- 순서 : Network Access > Internet > Transport > Application
> - **인터넷/네트워크 계층 프로토콜**   
>   \- IP : 송수신 호스트가 패킷 교환 네트워크에서 정보를 주고받는 데 사용하는 규약      
>   \- ICMP : 송신 시스템에게 IP전달에 대한 메시지를 전달하기 위한 프로토콜      
>   \- IGMP : 로컬 네트워크상의 멀티캐스팅, 그룹 제어 수행   
>   \- ARP : IP주소를 물리적 하드웨어 주소(IP -> MAC)로 대응시키기 위해 사용   
>   \- PARP : 네트워크 인터페이스의 하드웨어 주소를 기반으로 IP주소(MAC -> IP)로 변환   
> - **전송 계층 프로토콜**   
>   \- TCP : 순차적, 안정적이며 신뢰할 수 있는 프로토콜. 3-Way Handshaking 연결 방식, 4-Way Handshaking 연결해제 방식   
>   \- UDP : 비연결, 비신뢰성이라 전송 속도가 빠름   
> - **응용 계층 프로토콜**   
>   \- SMTP(포트번호 25) : 전자우편을 송신할 때 사용   
>   \- POP(110) : 전자우편을 수신하기 위해 사용   
>   \- Telnet(23) : CUI기반의 원격지 컴퓨터 접속 지원   
>   \- SSH(22) : Telnet의 보안 기능 강화   
>   \- FTP(20-일반 데이터 전송용, 21-제어 데이터 전송용) : 대량의 데이터를 고속으로 전송하는 서버/클라이언트 프로토콜. 익명으로 접속할 수 있음   
>   \- HTTP(80) : WWW를 이용 시 서버와 클라이언트 간의 정보교환 담당   
>   \- SNMP(161, 162) : 네트워크 장비들을 관리 감시하여 특정 망의 상태 파악   
>   \- TFTP(69) : FTP보다 단순화된 파일 전송 프로토콜   
>   \- DHCP(67, 68) : 유동 주소 체계를 사용하는 호스트들에게 통신에 필요한 환경설정. 정보(IP 주소, 게이트웨이 주소, DNS 주소 등)를 할당   

### UTP 케이블
>   \- T568A : 흰녹, 녹, 흰주, 파, 흰파, 주, 흰갈, 갈   
>   \- T568B : 흰주, 주, 흰녹, 파, 흰파, 녹, 흰갈, 갈   
>   \- 실제 사용 : 1, 2, 3, 5번에 해당하는 선   

### 3-Way Handshaking
> - **패킷 교환 순서**   
>   \- SYN > ACK/SYN > ACK
> - **상태**   
>   \- LISTEN : 서버에서 클라이언트로부터 들어오는 패킷을 위해 소켓을 열고 기다리는 상태   
>   \- SYN_SENT : 로컬에서 원격으로 연결 요청을 시도한 상태    
>   \- SYN_RECEIVED : 서버가 클라이언트로부터 접속을 요구 받아 클라이언트에게 응답했지만, 클라이언트에게 확인 메시지를 받지 않은 상태   
>   \- ESTABLISHED : 클라이언트로부터 확인 메시지를 받은 상태   

### IPv4 사설 IP 주소
>   \- A 클래스 : 10.0.0.0 ~ 10.255.255.255   
>   \- B 클래스 : 172.16.0.0 ~ 172.31.255.255   
>   \- C 클래스 : 192.168.0.0 ~ 192.168.255.255   
 
### 인터넷 서비스 종류
> - **WWW**   
>   \- HTTP를 기반으로 한 멀티미디어와 하이퍼텍스를 통한한 정보 검색 시스템   
> - **Gopher**   
>   \- 인터넷 기반의 문서 검색 시스템
> - **메일**   
>   \- 컴퓨터 사용자끼리 편지를 주고받는 서비스   
> - **FTP**   
>   \- TCP/IP에 의해 제공되는 호스트 간의 파일 복사를 위한 프로토콜   
>   \- open : 호스트 이름이나 IP 주소를 사용하여 접속   
>   \- close : 현재 접속 중인 연결된 끊고 FTP 명령어 모드로 돌아감   
>   \- (m)get : FTP 서버로부터 (복수 개의)파일을 전송받음   
>   \- (m)put : 로컬의 (복수 개의)데이터를 FTP 서버로 전송   
>   \- hash : 파일 전송 상태를 # 문자를 통해서 확인   
>   \- delete : FTP 서버의 파일을 삭제   
> - **DNS**   
>   \- 호스트 이름을 기반으로 IP주소로 변환하거나 IP주소를 기반으로 호스트 이름을 변환시켜 주는 프로토콜
> - **Telnet/SSH**   
>   \- 네트워크상에 있는 다른 컴퓨터에 로그인하거나 원격 시스템에서 명령 실행, 파일 복사 등을 제공   
>   \- SSH는 암호화 기법을 사용하여 전송   
> - **NFS**   
>   \- 네트워크 기반에 다른 시스템과 파일 시스템을 공유하기 위한 클라이언트/서버 프로그램   
> - **RPC**   
>   \- 동적으로 서비스와 포트를 연결할 떄 사용하는 방법   

### 네트워크 설정 파일
> - **/etc/sysconfig/network**   
>   \- 네트워크의 기본 정보가 설정되어 있는 파일   
>   \- 시스템 전체의 게이트웨이 주소, 호스트명, 네트워크 연결 허용 여부를 설정   
> - **/etc/sysconfig/network-scripts/ifcfg-ethX**   
>   \- 지정된 네트워크 인터페이스의 네트워크 환경 설정 정보가 저장됨   
> - **/etc/resolv.conf**   
>   \- DNS서버 주소 설정   
> - **/etc/hosts**   
>   \- IP 주소와 도메인 주소를 1:1로 등록하여 도메인에 대한 IP주소를 조회   
> - **/etc/host.conf**   
>   \- DNS 서비스를 제공할 때 먼저 이 파일을 검색하여 파일의 설정에 따라 서비스   

### 기관
> - **IANA(Internet Assigned Numbers Authority, 인터넷 할당 번호 관리기관)**   
>   \- IP 주소, 최상위 도메인 등을 관리하는 단체   
> - **IETF(Internet Engineering Task Force, 국제 인터넷 표준화 기구)**   
>   \- 인터넷의 운영, 관리, 개발에 대해 협의하고 프로토콜과 구조적인 사안들을 분석하는 인터넷 표준화 작업기구   
> - **ICANN(Internet Corporation for Assigned Names and Numbers, 국제 인터넷 주소 관리기구)**   
>   \- 인터넷 DNS의 기술적 관리, IP 주소공간 할당, 프로토콜 파라미터 지정, 루트 서버 시스템 관리 등의 업무를 조정하는 역할   
> - **ITU(International Telecommunication Union, 국제 전기 통신 연합)**   
>   \- 유엔의 산하 기구로 전기 통신의 개선과 효율적인 사용을 위해 국제 협력을 증진   
> - **ISO**   
>   \- OSI 7계층과 관련 프로토콜 제정   
> - **IEEE**   
>   \- LAN 및 MAN 관련 표준 제정   
> - **ANSI**   
>   \- 미국내 규격. ASCII 코드 제정   

### 네트워크 관련 명령어
> - **ifconfig**   
>   \- 네트워크 인터페이스 구성을 위한 설정 또는 확인하는 시스템 관리 유틸리티   
>   \- ifconfig 인터페이스명 [IP addr] netmask [addr] [broadcast <addr>] [up|down]   
> - **ping**   
>   \- 특정 호스트 또는 네트워크 장비까지의 통신가능 여부를 점검   
> - **traceroute**   
>   \- 특정 호스트 또는 네트워크 장비까지의 어떤 통신경로를 걸쳐 패킷이 전달되는지 확인(통신 장애 구간을 확인 가능)         
> - **route**   
>   \- 라우팅 테이블 확인   
>   \- 시스템에 설정된 게이트웨이 주소값을 확인할 때 사용   
>   \- 라우팅을 확인하거나 변경할 때 사용 
> - **nslookup**   
>   \- 인터넷 도메인 네임서버에게 특정 호스트에 대한 정보를 질의하는 대화식 명령어   
> - **netstat**   
>   \- 전송 제어 프로토콜, 라우팅 테이블, 네트워크 프로토콜 통계 및 네트워크 연결 상태를 확인   
> - **mii-tool**   
>   \- 네트워크 인터페이스의 속도와 전송모드 등을 확인
> - **ethtool**   
>   \- 네트워크 인터페이스의 물리적 연결 여부를 확인
> - **arp**   
>   \- 시스템이 가지고 있는 arp 테이블을 확인, 추가, 삭제
> - **system-config-network**   
>   \- CentOS 6 버전에서 텍스트 기반으로 네트워크 주소를 설정할 때 사용   
> - **nm-connection-editor**   
>   \- GUI 기반 네트워크를 설정할 때 사용   

### 최상위 도메인
>   \- 영리기관 : com   
>   \- 비영리기관 : org   
>   \- 네트워크기관 : net   
>   \- 교육기관 : edu   
>   \- 정부기관 : gov   
>   \- 군사기관 : mil   
>   \- 국제기관 : int   
>   \- 국가기관 : kr, jp, fr   

### 리눅스 관련 기술
> - **고계산용 클러스터(HPC)**   
>   \- 고성능의 계산 능력을 제공하기 위한 목적으로 제작   
>   \- 베어울프 클러스터라고도 지칭    
> - **부하 분산 클러스터(LVS)**   
>   \- 대규모 서비스를 제공하기 위한 목적으로 제작되었으며 주로 웹 서비스 등에 활용   
>   \- 다수 개의 서버가 로드밸런서에 연결되어 서비스를 제공      
> - **고가용성 클러스터(HA)**   
>   \- 지속적인 서비스 제공을 목적으로 제작되었으며 금융권, 데이터센터 등에서 사용   
>   \- 로드밸런서 시스템을 이용   
>   \- 로드밸런서와 백업서버 사이에서 주기적으로 통신을 하여 이상 유무를 점검      
> - **임베디드 시스템**   
>   \- 특정 기능을 수행하는 프로그램이 내장되어 있는 시스템   
>   \- 장점 : 기능성과 확장성이 우수. 로열티가 없어서 가격 경쟁력이 우수. 사용자층이 넓어 오류 수정이 빠르고 안전성 우수. 기존 데스크탑 개발 환경과 동일하여 개발 용이   
>   \- 단점 : 많은 메모리 요구. GUI 환경을 개발하기 어려움. 사용자모드와 커널모드 메모리 접근이 복잡하여 제품화하기 위한 솔루션 구성이 어려움. 업체와 개인이 독자적으로 개발하여 표준화 어려움   

### 클라우드 서비스 종류
> - **IaaS(Infrastructure as a Service)**   
>   \- 서버나 스토리지 같은 하드웨어 자원만을 임대해 주는 클라우드 서비스
> - **PaaS(Platform as a Service)**   
>   \- 소프트웨어 서비스를 개발하기 위한 플랫폼을 제공하는 클라우드 서비스
> - **SaaS(Software as a Service)**   
>   \- 응용 프로그램을 서비스 형태로 제공

### 브라우저
>   \- 크롬 : 구글   
>   \- 사파리 : 애플   
>   \- 오페라 : 노르웨이   
>   \- 파이어폭스 : 모질라재단   

 
 
