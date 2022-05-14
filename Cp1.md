#  Chapter 1.
![Network 7 Layers](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcgJ1bs%2FbtruwIivAHg%2Fkh2MVLn1zIFy0oOKdjeOjK%2Fimg.jpg)



소켓이란?
An interface between application and N/W
the application creates a socket
The socket type dictates the style of communication (reliable vs best effort, connection-oriented vs connectionless)

Two essential types of Sockets

Packet switching vs Circuit switching

구성요소로 본 인터넷

host / end system : 네트워크에 연결된 장치
communication link, packet switch 의 네트워크로 연결된다.
각각의 링크들은 다양한 전송률(transmission rate, 링크 대역폭)을 이용하여 데이터를 전송하며 전송률은 초당 비트 수를 의미하는 bps (bit per second) 단위를 사용한다.

한 end system -> another end system으로 보낼 data를 가지고 있을 때, 송신 end system은 그 데이터를 segment로 나누고 각 segment에 header를 붙인다. 이렇게 만들어진 정보 패키지는 컴퓨터 네트워크에서 packet이라고 불린다. packet 은 목적지 end system으로 네트워크를 통해 보내지고 목적직에서 원래의 데이터로 다시 조립된다.

packet switch는 다양한 형태와 특징이 있는데, 가장 널리 사용되는 종류로는 router, link-layer switch가 있다. 
router는 네트워크 코어에서 사용되며, link-layer switch는 보통 액세스 네트워크에서 사용된다.

패킷이 sender end system -> receiving end system에 도달하는 동안 거쳐 온 일련의 통신 링크와 패킷 스위치들을 네트워크상의 경로(route/path)라고 한다.

패킷은 트럭과 유사하고, 통신 링크는 도로, 패킷 스위치는 교차로, end system은 빌딩과 유사하다. 트럭이 운송 네트워크를 통해 경로를 따르는것처럼, 패킷은 컴퓨터 네트워크를 통한 경로를 따른다.

end system은 ISP(Internet Service Provider)를 통해서 인터넷에 접속하는데, ISP의 종류는 다양하고 다양한 네트워크 접속을 제공한다. 또한 웹사이트와 비디오 서버를 인터넷에 직접 연결하도록 CP(Content Provider)에게 인터넷 접속을 제공한다. 인터넷은 enad system을 서로 연결하는 것이므로 ISP들도 서로 연결되어야한다. 이들 하위 계층 ISP는 L3 communications, AT&T, Sprint, NTT와 같은 국가 그리고 국제 상위 계층 ISP를 통해 서로 연결된다. 상위 계층 ISP는 광 링크로 연결된 고속 라우터로 구성된다. 상위 계츠이든 하위 계층이던 각 ISP 네트워크는 따로 관리되고, IP protocol을 수행하며 naming과 주소배정 방식을 따른다.

end system, packet switch, 인터넷의 다른 구성요소는 인터넷에서 정보. 송수신을 제어하는 여러 프로토콜을 수행한다. 특히 TCP(Transmission Control Protocol)와 IP(Internet Protocol)는 인터넷에서 가장 중요한 프로토콜이다. IP 프로토콜은 라우터와 종단 시스템 사이에서 송수신되는 패킷 포맷을 기술한다. 이러한 인터넷의 프로토콜을 통칭하여 TCP/IP라고 한다. 

인터넷 표준(Internet Standard)은 IETF(Internet Engineering Task Force)에서 개발하며, IETF 표준 문서를 RFCs(Requests For Comments)라고 한다.


1.1.3 프로토콜이란 무엇인가?
프로토콜은 컴퓨터 사이에 연결된 선로상의 비트 흐름을 제어한다. 프로토콜은 둘 이상의 통신 개체 간에 교환되는 메시지 포맷과 순서뿐 아니라, 메시지의 송수신과 다른 이벤트에 따른 흐름들을 정의한다.

1.2 네트워크의 가장자리
host = end system.
때로는 client / server로 구분된다. 비공식적으로 클라이언트는 데탑, 모바일, 스마트폰 등을 의미한다.
오늘날 검색결과, 메일, 웹페이지, 비디오를 수신하는 대부분의 서버들은 커다란 데이터 센터 내에 있다.

1.3 네트워크 코어
네트워크 응용에서 종단 시스템들은 서로 메시지를 교환한다. 송신 시스템은 긴 매시지를 packet이라고 하는 작은 데이터 덩어리로 분할한다. 송신 측과 수신 측 사이에서 각 패킷은 통신 링크와 packet switch(router와 link-layer switch)를 거치게 된다. 패킷은 링크의 최대 전송속도와 같은 속도로 각각의 통신 링크상에서 전송된다. 따라서 송신 종단 시스템 혹은 패킷 스위치가 R bit/s의 속도로 링크상에서 L bits의 패킷을 송신한다면,그 패킷을 전송하는 데 걸리는 시간은 L/R초이다.

store-and-forward transmission
대부분의 패킷 스위치는 저장-후-전달 전송 방식을 이용한다. 
라우터는 보통 여러 개의 링크가 있는데 
