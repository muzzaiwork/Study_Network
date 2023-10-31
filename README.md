# Study_Network
- User Mode와 Kernal Mode
  ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/c1e09fe4-b747-4876-8090-52a3d44cf615)
  - S/W는 User Mode 소프트웨어와 Kernal Mode 소프트웨어로 나뉜다
    - User Mode : Application
    - Kernal Mode : System Software

  - NIC(Network interface card, 랜카드)와 같이 어떤 하드웨어를 제어하기 위한 소프트웨어가 존재하는데, 이것을 driver라고 한다.
  - driver가 설치되어야 NIC가 작동한다.
  - 커널을 이루고 있는 구성요소 중 프로토콜(TCP/IP)이 구현된 소프트웨어가 있다.
  - User Mode의 어플리케이션이 Kernal의 구성요소에 접근할수 있도록 커널에서 길을 열어준다.
    - 어떤 인터페이스를 통해서 접근 가능하다.
    - 이 인터페이스의 형태가 File이다.
    - 특별하게 TCP/IP를 추상화 시킨 File은 Socket이라고 부른다.
  - Socket은 file이다.
  - socket을 여는 주체는 Process다.
  - "socket을 열였네 닫았네" 는 "file을 열었네 닫았네" 와 같은 말이다.
  - TCP : L4의 전송을 담당하는 프로토콜
  - IP : L3의 네트워크를 담당하는 프로토콜
 
- OSI 7 Layer와 식별자
  ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/def80c74-033d-435b-a91e-23dcf955e4b5)

  - 식별자
     - L2: MAC Address가 있다. LAN카드에 붙는게 Mac Address
     - L3: IP 주소 ipv4 ipv6 (호스트)
     - L4: PORT
       - 일하는 사람에 따라 포트에 대한 이해가 다르다.
         - 인터페이스(공유기 뒤에 인터넷선 꼽는 단자), 프로세스, 서비스
        
- Host
  - Host: 컴퓨터인데 네트워크와 연결된 컴퓨터를 호스트라한다.
    - Switch
      - 네트워크 그 자체를 이루는 host (Infra의 영역)
      - IP주소가 들러붙는 뭔가들
      - Host가 목적 자체가 네트워크를 확장하거나 네트워크의 기능요소
      - Router(L3 스위치), IPS(보안 스위치), TAB(관리 목적의 스위치) 등 
    - End Point
      - 네트워크의 이용 주체
      - network 인프라 스트럭쳐를 써먹는거
      - 단말
      - client, server, p2p
