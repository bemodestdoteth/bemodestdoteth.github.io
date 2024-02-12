---
title: "NAS: My Personal Library"
author: bemodest.eth
date: 2022-10-10 00:00:00 +0900
categories: [Development, NAS]
tags: [development, nas]
image:
  path: posts/1010_1.png
  width: 500
  alt: More efficient second brain
---

# **Introduction**
## **▚ 내 도서관을 만들겠다는 결심을 하다**
　어디서든, 어느 장비서든 내 파일에 접근할 수 있는 클라우드 저장소는 매력적인 상품이다. 그래서인지 Dropbox, Onedrive, Google Drive 같은 솔루션들이 많다. **그러나 기업에서 제공하는 클라우드 솔루션 대신 개인 NAS를 만드려는 생각을 예전부터 하고 있었다.**

　물론 기업 솔루션을 쓰면 편하긴 하다. 그러나 계속 저장소를 운영하면서 저장 용량이 많아지면 NAS를 직접 만드는 것이 더 경제젹이다. 위의 솔루션들은 달마다 구독료를 바쳐야 하고 용량 상한도 있기 때문이다.

　프라이버시 문제도 있다. 작년 8월 애플이 ICloud에 업로드되는 사진을 스캔해 아동 성 착취와 관련된 사진을 잡아내겠다는 발표가 큰 논란이 된 적이 있다. 다른 클라우드 솔루션이라고 다를까? 자기들은 절대로 하지 않겠다고 말하겠지만 유저들의 데이터를 몰래 바라보지 않을 이유는 없다고 본다.

![Desktop View](posts/1010_5.png){: width="500"}
_취지는 공감하지만 프라이버시 논란이 생길 수밖에 없다_

　최근 무언가 기록을 해도 내 것이 되지 않고 밑 빠진 독처럼 다 빠져나가는 느낌이 들었다. 과거에 배운 것, 누군가에게 들은 것을 토대로 앞으로 나아가지 못한다는 느낌이 들었다. 그래서 내 모든 기록이 저장되는 도서관을 기반부터 다시 만들기로 했다. 마침 집에 굴러다니는 여분 컴퓨터도 있었다. **그렇게 내 생각 속 조각들이 기폭제가 되면서 10월 초 NAS 제작을 행동으로 옮겼다.**

## **▚ NAS 스펙**
- CPU: AMD Ryzen 2200G (Raven Ridge)
- RAM: 16GB (2x 8GB)
- SSD(Boot Drive): 1x SK Hynix P31 500gb
- SSD(Storage): 1x Samsung 870 QVO 4tb
- Case: Asrock Deskmini A300
- OS: TrueNAS Core 13

　4tb SSD를 빼면 전부 집에 있던 물건이다. 드문 케이스겠지만 저장 장치로 하드가 아닌 SSD를 사용했다. 그 이유는:

1. 케이스가 2.5인치 드라이브만 지원한다
2. 드라이브 고정 나사가 헐렁해 하드가 부서질 위험이 컸다
3. 당장은 그렇게 큰 용량이 필요하지 않다

　OS로 TrueNAS를 선택한 이유는 다른 이유는 없고, 찾아보니까 가장 많이 나와서 선택했다.

## **▚ Step 1. NAS 설치 및 드라이브 추가**
　NAS 첫 설정 자체는 어렵지 않았다. 윈도우 까는 것처럼 NAS의 서버 역할을 할 컴퓨터에 TrueNAS OS를 설치하면 됐다.

- TrueNAS 홈페이지에 들어가서 OS 설치 파일을 받기
- Rufus로 USB에 설치 파일 굽기
- USB를 서버 컴퓨터에 꼽고 부팅
- 시키는 대로 TrueNAS OS 설치
- OS 깔고 랜선 꼽고 재부팅

　재부팅하면 NAS 서버가 할당받은 내부 IP 주소가 나온다. 이를 주소창에 입력하면 공유기 설정하는 것처럼 TrueNAS를 설정할 수 있는 화면이 나온다.

![Desktop View](posts/1010_2.png){: width="500"}
_192.168.0.x로 접속하면 반겨주는 화면_

　OS 설치 단계에서 부팅 드라이브와 저장용 드라이브 관련 설정도 자동으로 진행된다. 저장용 드라이브가 더 필요하다면 설정 페이지에서 쉽게 추가할 수 있다.

## **▚ Step 2. 로컬 네트워크에서 파일 접근**
> https://www.truenas.com/community/threads/how-to-set-up-windows-smb-shares-on-freenas.83376/
>
> NAS 서버를 올렸으니, 클라이언트에서 서버의 파일에 접근해야 한다

![Desktop View](posts/1010_1.png){: width="500"}
_윈도우에서의 결과물_

![Desktop View](posts/1010_3.png){: width="500"}
_아이폰은 connect to server, 갤럭시는 network storage_

　SMB를 이용하면 윈도우, 아이폰, 안드로이드에서 NAS 파일 접근이 가능했다. 다만 갤럭시에서는 포트를 입력해야 했다. 다행히 구글링 하니까 답이 나왔다. 445 적으면 된다.

　(맥이 없어서 맥에서의 연결 방법은 확인하지 못했다. 나중에 돈 많이 벌어서 맥북 사면 그때 수정 예정...)

　여기까지만 설정해도 NAS 사용에는 큰 문제가 없다. 단 NAS와 같은 네트워크에 있을 때만 파일에 접근할 수 있다는 제약이 있다. 외부에서도 내 파일에 접근하려면 훨씬 더 복잡한 과정이 필요했다.

## **▚ Step 3. OpenVPN을 통한 인터넷에서 파일 접근**

　사실 NAS 외부 연결 구축 자체는 어렵지 않다. 그러나 "보안을 갖춘" 연결 구축이라면 이야기가 달라진다.

　내가 외부에서 내 NAS에 접근할 수 있다는 뜻은 인터넷의 누구든 내 NAS에 접근할 수 있다는 뜻이기도 하다. 누군가 내 NAS에 몰래 접근해서 내 서버를 비트코인 채굴기로 활용하거나, 랜섬웨어를 씌우거나, 아동 포르노 유통 서버로 만들 수도 있다. **보안 없는 외부 연결은 상어가 득실거리는 바다에 맨몸으로 다이빙하는 꼴이다.**

![Desktop View](posts/1010_4.png){: width="500"}
_대충 NAS 서버를 인터넷에 열면 대충 안 좋은 일이 많이 생긴다는 글_

　찾아보니까 암호키 매칭을 통한 보안 접속이 주로 활용됐다. **자물쇠로 서버 입구를 잠그고 접속할 기기에 자물쇠와 맞는 열쇠를 준비하는 것으로 이해하면 편하다.** SSH, OpenVPN 등의 방법이 있는데 모바일에서도 쓸 수 있는 OpenVPN 방법을 시도하기로 했다.

　OpenVPN을 설정하는 방법은 크게 두 가지가 있다. OpenVPN Server를 지원하는 공유기를 이용하거나, NAS Server가 OpenVPN Server 역할도 하게 하거나. 내 공유기는 OpenVPN Server를 지원하지 않아서 어쩔 수 없이 후자로 갔다.

> [https://www.youtube.com/watch?v=AibYAOA7DqE](https://www.youtube.com/watch?v=AibYAOA7DqE)
> 
> [https://www.youtube.com/watch?v=S8I-IiQYVas](https://www.youtube.com/watch?v=S8I-IiQYVas)
> 
> [https://www.youtube.com/watch?v=it0HdDiutIE](https://www.youtube.com/watch?v=it0HdDiutIE)
>
> OpenVPN 설정 관련 유튜브 영상

　**NAS Server에 OpenVPN Server를 설치하는 큰 줄기:**
1. DDNS 만들고 공유기 외부 IP 주소와 연결
2. Root Certificate 만들기
3. Server Certificate 만들기
4. OpenVPN Server Service 설정하기
5. Client Certificate 만들기
6. Client 접속을 위한 OpenVPN 파일 다운로드 후 포맷에 맞게 수정
7. 외부 접속을 위한 포드포워딩
8. 테스트

　인터넷에 적힌 튜토리얼을 이해하기 어려워서 이 과정에서 ㅁ낳이 막혔다. 다행히 유튜브에는 잘 설명된 튜토리얼이 많았다. 글로 읽는 것보다 훨씬 따라하기 쉬웠다. 약 이틀간의 시행착오 끝에 VPN을 통한 외부 연결에 성공했을 때의 뿌듯함은 아직도 잊히지 않는다. 모든 세팅을 마치고 지금은 글을 쓰면서 컴퓨터의 데이터를 NAS에 올리고 있다.

## **▚ 개선점**
- **추가 SSD 주문**

　NAS를 찾아보면서 알게 된 사실인데 2bay NAS에 4tb 하드 2개를 넣으면 반드시 8tb를 사용하는 것이 아니었다. 0번 하드와 1번 하드를 같은 풀로 묶어 4tb로 사용한다고 한다. 이러면 0번 하드가 박살나도 1번 하드에 백업된 데이터가 있기 때문에 데이터 손실을 막을 수 있다고 한다.

　거의 모든 NAS가 2bay로 시작하는 이유가 이 때문일 것이다. 나는 이를 모르고 SSD를 1개만 주문했는데.. 가까운 시일 내에 하나 더 주문할 예정이다

- **느리다**

　파일 옮기는데 최대 속도가 10mb/s 언저리다. 집 인터넷이 100메가라서 그런 것 같은데 지금은 인터넷 속도를 바꿀 수 없어서 아쉽다. 나중에 이사가서 기가비트 인터넷으로 바꾸면 괜찮아질듯.