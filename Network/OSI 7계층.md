### 7계층으로 나누는 이유
    통신이 일너나는 과정을 단계별로 알 수 있고, 특정한 곳에 문제가 생기게 되면 그 단계만 수정을 하면 되기 때문이다.

###○물리(Physical)
    단지 데이터를 전기적인 신호로 변환해서 주고받는 기능을 진행하는 계층. 즉 데이터를 전송하는 역할만 진행
    
    리피터, 허브, 케이블 등

###○ 데이터 링크(Data Link)
    물리 계층으로 송 수신되는 정보를 관리하여 안전하게 전달되로록 하는 역할

    Mac 주소를 통해 통신하며 프레임에 Mac 주소를 부여하고 에러검출, 재전송, 흐름제어를 진행

    브릿지, 스위치 등

###○ 네트워크(Network)
    데이터를 목적지까지 안전하고 빠르게 전달하는 기능을 담당

    라우터를 통하여 이동할 경로를 선택하여 IP주소를 지정하고 해당 경로에 따라 패킷을 전달해 줌

    라우팅, 오류 제어, 흐름제어, 세그먼테이션 등을 수행

    라우터, IP

###○ 전송(Transport)
    TCP 와 UDP 프로토콜을 통해 통신을 활성화

    포트를 열어두고 프로그램들이 전송을 할 수 있도록 제공해줌

    TCP: 신뢰성, 연결지향적, 느림
    UDP: 비신뢰성, 비연결성, 실시간, 빠름

###○  세션(Session)
    데이터가 통신하기 위한 논리적 연결을 담당
    TCP/IP 세션을 만들고 없애는 책임을 지님

    API, Socket

###○  표현(Presentation)
    데이터 표현에 대한 독립성을 제공하고 이를 암호화 하는 역할을 담당
    
    파일 인코딩, 명령어을 포장, 압축, 암호화

    JPEG, MPEG 등

###○  응용(Application)
    응용 프로세스와 직접 연계하여 일반적인 응용 서비스를 수행
    
    사용자 인터페이스, 전자우편, DB관리 등 서비스를 제공

    HTTP, FTP, DNS등