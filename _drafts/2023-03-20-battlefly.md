---
title: BattleFly
author: bemodest.eth
date: 2023-03-20 00:00:00 +0900
categories:
  - Gaming
tags:
  - gaming
image:
  path: posts/230320_1.png
  width: 500\
  alt: BattleFly Research Documentation
---
> ## **▚ TL;DR** 
> - 초기 진입 장벽 해소를 위해 디스코드에 자세한 온보딩 과정을 설명하고 블록체인 관련 지식 없이 게임 참여 가능하도록 지원
> - TresaureDAO의 생태계 토큰인 MAGIC 자체 인게임 재화인 Nectar를 사용해 게임의 핵심 아이템인 BattleFly NFT를 강화
> - 배틀 게임 특성상 많은 유저가 모여야 하지만 그렇지 못해 문제가 발생하고 있음

---

## **▚ Table of Contents**
1. Introduction
2. Gameplay
3. Token
4. Revenue
5. Conclusion

---

## **▚ 1. Introduction**
- BattleFly는 2023년 2월 초 Treasure DAO 플랫폼에서 출시된 웹 대전 게임이다. 화려함은 없지만 NFT를 활용한 베팅과 대전을 
- Treasure DAO는?

## **▚ 2. Gameplay**

### **게임 온보딩**

#### **1. 디스코드 온보딩 투어**
![Desktop View](posts/230320_3.png)
{: width="100%"}
- 게임 웹페이지를 맨 처음 접속하면 위와 같이 패스워드를 입력하라는 창이 뜬다. 해당 패스워드는 디스코드 채널에서 게임 관련 3개의 퀴즈를 풀면 확인할 수 있다.

#### **2.BattleFly NFT 구매 및 예치**
![Desktop View](posts/230320_4.png)
{: width="100%"}
- [Trove 마켓플레이스](https://market.treasure.lol/)에서 다른 유저들이 판매 중인 BattleFly 구매 후 스테이킹
- (로드맵) Flight Pass를 통해 직접 1차 거래로 BattleFly 구매 가능 예정
- 스테이킹 시 가스비 필요
- 스테이킹한 BattleFly는 Trove 마켓플레이스에 등록 불가

#### **3. 게임에 필요한 MAGIC 토큰 입금**
![Desktop View](posts/230320_5.png)
{: width="100%"}
- MAGIC 구매 후 게임 컨트랙트에 입금
- 배틀에 사용하는 MAGIC은 입금된 MAGIC에서 차감됨
- Buy MAGIC 버튼 클릭 시 스시스왑으로 연결됨
- 현재 Fiat 결제는 지원하지 않음
- (로드맵) Flight Pass를 통해 Fiat으로 BattleFly NFT 및 배틀에 필요한 MAGIC 구매 가능 예정

### **기본 게임플레이**

#### **배틀 준비**
![Desktop View](posts/230320_6.png)
{: width="100%"}
1. BattleFly 스테이킹 (가스비 필요)
2. BattleFly의 일일 배틀 횟수를 미리 정하고 배틀 상태로 변경
3. 2에서 정한 일일 배틀 횟수 만큼 자동으로 배틀 진행
4. 입금한 MAGIC이 떨어지거나 BattleFly의 배틀 상태를 변경하거나 BattleFly를 언스테이킹하면 배틀이 중단됨

#### **진행 과정**
![Desktop View](posts/230320_7.png)
{: width="100%"}
_배틀 시뮬레이션 화면_
- 매치매이킹된 유저들은 각각 입금한 0.1 MAGIC을 걸고 배틀 진행
- 승자는 패자에게 0.095 MAGIC을 얻음. 0.005 MAGIC은 DAO Treasury로 이동 (5% rake)
- 패자는 Nectar 획득
- 배틀 시뮬레이션을 통해 이미 진행된 배틀의 결과를 볼 수 있음 (실시간 확인을 불가)
- Nectar는 장비 구매 및 업그레이드를 통한 BattleFly 능력치 강화에 사용됨

## **▚ 3. Economy**

![Desktop View](posts/230320_2.png)
{: width="100%"}
_BattleFly 게임 경제 도식. 왼쪽이 게임플레이 루프, 오른쪽이 거버넌스 루프_
- **매출:** Treasury로 넘어간 수수료의 50%(0.0025 MAGIC) + 장비(Mods) 구매 비용
- **gFLY:** BattleFly DAO의 거버넌스 토큰
- **Bridgeworld:** TreasureDAO의 핵심 GameFi 생태계로, MAGIC을 스테이킹해 발행되는 MAGIC을 보상으로 얻는 시스템 존재
- **Founders NFT:** BattleFly DAO Treasury 일부의 소유권을 나타내는 NFT

### **MAGIC 토큰**
> Treasure DAO 생태계의 핵심 토큰으로, Treasure DAO 플랫폼에 온보딩한 게임들이 게임 내 재화로 사용하는 경우가 많음

#### **획득**
- 배틀 승리로 획득
- 각 랭크당 일일 최다승 top 5 유저에게 MAGIC 보상 지급한다. 티어가 존재하고 티어에 따라 MAGIC 보상량이 다르다.
	- Pupa (가장 낮은 티어): 6 ~ 8 MAGIC
	- Apex (가장 높은 티어): 71 ~ 98 MAGIC
	- 최상위 티어 Champion 티어는 랭크 리더보드 Top 10 유저로 매일 별도의 MAGIC 보상 획득한다 (미출시)

#### **소모**
![Desktop View](posts/230320_10.png)
{: width="100%"}

### **Neactar**

> 인게임 재화로, 블록체인 토큰은 아님. BattleFly NFT의 강화에 필요한 핵심 재화

#### **획득**
1. 배틀 패배 (Proving Ground: 3개 지급, Hyperdome: 1개 지급)
	- 하루에 최대 300개 or 100개 획득 가능 (BattleFly는 하루에 100번 배틀 가능)
2. 구매한 장비 팩 재활용 (20개 지급)
3. [Racer 미니게임](https://www.youtube.com/watch?v=du_HB-BXvgI) 플레이

#### **소모**
1. Mark 구매: 특정 종류의 장비 획득 확률을 높이거나 높은 레어리티의 장비 획득 확률을 높일 수 있음
2. 1개의 장비 팩 개봉 시
	- 최대 5번 리롤 가능 (1번 당 50 Nectar)
	- 최대 1번 장비 레어리티 업그레이드 가능 (35 Nectar)

### **BattleFly NFT**
> 게임 플레이를 위해 반드시 필요한 핵심 토큰

![Desktop View](posts/230320_9.png)
{: width="100%"}

- 레어리티에 따라 추가 Trait 부여
- Tokenbound Item: BattleFly가 장착/보유하고 있는 모든 장비 정보와 인벤토리 슬롯 개수가 NFT에 저장됨
- 마켓플레이스의 NFT 설명 페이지에서 해당 BattleFly NFT가 장착한 장비 및 인벤토리에 보유하고 있는 모든 장비를 확인 가능하다.

![Desktop View](posts/230320_8.png)
{: width="100%"}

### **기타 토큰 및 NFT**
- gFLY(토큰): 


## **▚ 4. Revenue**

## **▚ 5. Conclusion**
> 
> **오프체인 온보딩**
> 
> - Web3 지갑을 만들지 않고 버로 게임에 온보딩할 수 있은 기능이 로드맵에 존재
> 
>   **1.** Fiat으로 바로 게임을 플레이할 수 있는 장비들을 제공하는 패스 구매
> 
>   **2.** 오프체인 온보딩 상태에서 벌어들인 토큰은 DAO가 대신 보관
> 
>   **3.** 나중에 Web3 지갑을 만들 때 DAO가 보관하던 토큰 전달
> 
>   
> 
> **추후 비슷한 게임 온보딩 시 참고 가능 사항**
> 
>   **1.** 유저의 지속적인 게임플레이 유도를 위한 방법으로 NFT 설계 필요
> 
>   **2.** 배틀류 게임에서 희소성 있는 NFT를 활용하려면 이벤트 티켓 등의 요소가 적절
> 
>   **3.** 유저 풀이 적은 경우 상금 별로 방을 나누는 것 대신 매치메이킹을 통합하는 것이 좋아보임. 티어 제도가 있지만 유저 풀 때문에 티어가 제대로 작동하지 않음.