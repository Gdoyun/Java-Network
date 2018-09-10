# Java Network programming

## ch1 기본 개념
자바는 처음부터 네트워크 어플리케이션을 위해 설계된 언어  
### Network  
  - 네트워크: 실시간으로 서로 데이터 주고받을 수 있는 컴퓨터 및 다른 장치들의 집합  
  - 노드: 컴퓨터, 프린터, 라우터, 브리지, 게이트웨이 등 네트워크 안의 장비  
  - 호스트: 노드 중에서 일반적인 PC  
  - 모든 네트워크 노드는 서로를 식별할 수 있는 바이트 순서(빅엔디안 or 리틀엔디안)인 주소를 가진다.  
  - 주소는 네트워크 종류에 따라 다르게 할당된다. ("->"는 할당한다는 뜻)  
  - 인터넷 주소 할당 과정  
  - ICANN(국제도메인관리기구) -> 지역 인터넷 등록 기관(ex. KISA, ARIN) -> ISP(인터넷 서비스 제공자) -> 주소 기관(제조사)  
### 패킷 교환 <-> 회선교환      
   - 네트워크를 오고가는 데이터는 패킷으로 나뉘고 개별적으로 처리된다.  
   - *pros*  
     + 단일 회선을 통해 지속적으로 많은 패킷 교환 가능(싼 값에 네트워크 구축 & 간섭 없이 같은 선 공유)  
     + checksum 값을 이용해 전송 중에 발생한 데이터 손상 여부 발견  
### 프로토콜  
  - 컴퓨터의 통신 방법을 정의한 정밀한 규칙의 집합, 주소의 형식, 데이터를 패킷으로 나는 방법 등을 정의  
    + ex. HTTP(Hypertext Transfer Protocol): 웹 서버와 웹 브라우저 간의 통신 방법 정의  
    + 프로토콜의 공개로 플랫폼에 상관없이 같은 HTTP 프로토콜로 대화
### Network Layer  
  - IPv4 : 32bit 주소, IPv6 : 128bit 주소 (IPv6 증가추세)  
    + 비트&바이트 빅 엔디안 정렬, 최상위 비트 -> 최하위 비트 순(왼 -> 오)
### Transport Layer  
  - 데이터그램 : 전송 보장 X, 손상 가능 -> 손상만 발견 가능, 손상위치 모름, 순서 보장 X  
  - TCP(Transmission Control Protocol) : 손실 or 손상된 데이터의 재전송, 순서 보강 
  - UDP(User Datagram) : 수신자 손상 감지 but, 순서 보장 X, 속도 빠름
### Application Layer
  - WWW 에 쓰이는 HTTP
  - 이메일 전송
    + SMTP(Simple Mail)
    + POP(Post Office)
    + IMAP(Internet Message Access)
  - 파일 전송  
    + FTP, FSP, TFTP, NFS(Network)
  - 파일 공유
    + Bit Torrent
  - 음성 통신
    + SIP(Session Initiation)
    + Skype  
### IP, TCP & UDP  
 - IP 계층 위에 TCP가 놓여서 수신측에서 보내진 순서로 조립 가능
 - But, TCP는 overhead 유발 -> If 순서 중요하지 않으면 UDP 사용  
### IP 주소와 도메인
 - **IPv4**  
   +  127.0.0.1 (점으로 구분된 4개의 숫자 0~255)
     +  로컬 루프벽 주소로 라우팅 불가 (호스트네임: localhost) 
   +  255.255.255.255 (브로드캐스트 주소: 노드 탐색 용도)
   +  HTTP는 포트 80 사용
     +  1~1023까지 서비스(프로토콜)용 번호: HTTP : 80, SSH(암호화된 원격로그인): 22, FTP : 21
### Internet
  - 세상에서 가장 큰 IP 기반 네트워크
  - IP 사용하여 서로 대화할 수 있는 비결정 네트워크 그룹
  - 서로 대화하도록 약속된 컴퓨터들의 큰 집합
### internet
  - IP 기반 네트워크
  - Internet과 연결되지 않은 높은 보안 수준의 내부 네트워크
  - Intranet과 유사(회사 내부용)
  - *IPv4 -> IPv6*
    +  Firewall(방화벽): 인터넷과 로컬 네트워크 사이에 모든 데이터 검사하는 HW, SW
    +  Proxy server(방화벽에 의해 외부 네트워크로 연결이 금지된 장비가 외부에 직접 요청 X, 로컬 프록시 서버로부터 요청)
    


  
