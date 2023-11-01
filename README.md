# 네트워크 기초
- Internet 기반 네트워크 입문
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
    ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/de646024-dc42-4b3a-8a97-32c3d3ce80ce)
  
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
          
  - Switch가 하는일
    ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/630f4f74-12f3-44aa-bbc9-8530b252831c)
    - 네트워크는 고속도로망과 비슷하다.
    - 교차로를 만나면 경로를 선택해야된다.
    - 교차로가 스위치다.
    - 경로를 선택하는것 : Interface를 선택하는것 = 스위칭(switching)
    - IP 주소를 근거로 스위칭을 했다 -> L3 계층에서의 스위칭 -> L3 스위치 -> 라우터라고 부른다.
    - 라우터에는 이정표가 들어있는데 이것을 라우팅 테이블이라 부른다.
    - 단위(자동차)는 패킷이다.
    - Mac 주소를 근거로 스위칭을 했다 -> L2 스위치
    - 포트 번호를 근거로 스위칭을 했다 -> L4 스위치
    - HTTP -> L7 스위치
    ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/24782836-cc2d-4406-867e-3feb8164c1da)
  
    - 네트웍에서 이동시 항상 고민해야하는 주제는 비용이다.
    - 어느 길로 가느냐에 따라 비용이 다를수 있음.
    - 비용이 적은 길로 가야된다. -> 비용을 matric 값이라 부른다.
---
- L2 수준에서 외울 것
  - NIC, L2, Frame, Lan카드 그리고 MAC 주소
    ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/0b60993e-a3b4-41ee-a314-30f8f264dbae)

    - NIC은 흔히 LAN카드이다.
      
      ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/5a106f97-bc04-4105-a7e5-84045ae933a2)
      
      - 보통 그림그릴때 HOST는 네모로, 네트워크 인터페이스는 진한 점으로 표기
      - 점2개면 네트웍 인터페이스가 두개라는 이야기
      - 2개의 NIC을 가지는 경우가 종종 있다 -> 무선랜, 유선랜 등
      
      ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/396d2c0e-58e9-4481-a8e7-4e1aa507541d)
      - 네트워크의 규모를 말할때가 있다.
      - WAN : wide area
      - MAN : metropoli -> 도시
      - LAN : local area
      - 가장 작은 규모가 LAN이다.
      - 공유기에 PC, 스마트폰, IPTV수신기같은거 붙고 하는 모든것들이 홈 네트워크 -> LAN
    - MAC 주소는 NIC의 식별자

    ![image](https://github.com/muzzaiwork/Study_Network/assets/31703020/94656e00-737a-49cd-9d79-573ce192b37e)
    - 기기 하나하나가 NIC
    - Packet : L2에서 언급하는 인터넷에서의 단위
    - L2수준에서의 단위 : Frame -> 유통되는 단위(데이터 단위) -> 1514 byte정도 10kb 안돼, 속도: 1Gbps(bit)

---
- L2 스위치에 대해서
  - NIC 하나당 케이블 하나라 생각하면된다.
  - 
