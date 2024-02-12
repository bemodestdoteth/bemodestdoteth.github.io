---
title: StarkWare
author: bemodest.eth
date: 2022-08-06 00:00:00 +0900
categories: [Crypto, Layer2]
tags: [layer2]
image:
  path: posts/0806_1.png
  width: 500
  alt: Ethereum Layer 2 with Layer 3
---

### *취미생활방 서포터즈 활동으로 작성된 게시글입니다.
　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　    
## 🔎 개요
- zk 기법의 하나인 STARK를 기반으로 확장성 솔루션을 제공하는 회사
- [STARK 구현을 위해 Cairo라는 독자적인 언어를 사용](https://starkware.co/cairo/#:~:text=Cairo%20is%20a%20language%20for,a%20permissionless%20decentralized%20Validity-Rollup.)
- StarkNet: StarkWare에서 만든 L2 퍼블릭 블록체인
- StarkEx: StarkWare에서 만든 L2 앱 체인 솔루션
- StarkEx를 사용하는 앱: [Immutable X](https://www.immutable.com/), [dYdX](https://dydx.exchange/)(코스모스로 마이그레이션 예정)
- [zk에 대한 설명 + SNARK와 STARK의 차이점](https://academy.binance.com/ko/articles/zk-snarks-and-zk-starks-explained)

## 🔎 StarkNet Token
-  StarkNet의 네이티브 토큰
-  9월 메인넷 출시 예정

## 💡 StarkNet Token 유틸리티
-  ETH와 StarkNet Token 둘 다 tx 비용으로 사용 가능
-  스테이킹을 통해 Sequencer 역할 수행 + 거버넌스 기능
>  위의 유틸리티들은 2023년 도입 예정

## 💡 StarkNet Token 배분
> **총 100억 개의 토큰 배분**
- 32.9%(32억 9천 개): 핵심 기여자 | 1년 락업 | 3년 베스팅
- 17.0%(17억 개): 투자자 | 1년 락업 | 3년 베스팅
- 18.0%(18억 개): 커뮤니티 물량 (생태계 기여 보상 + 온보딩 유도 물량)
- 12.0%(12억 개): 그랜트
- 10.0%(10억 개): 재단 물량 (reserve)
- 나머지: 기부(2%) + 미할당(8%)

## 🔎 Sequencer
- [MEV와 비슷한 개념](https://ko.bitcoinethereumnews.com/technology/what-is-mev-ethereums-invisible-tax-explained/)
- 채굴된 블록 내에서 거래의 순서를 조정해 최대의 수수료를 뽑아내는 작업
- Sequencing을 통한 수수료 추출은 블록체인의 가장 큰 수입원 
- 현재 StarkNet은 중앙화된 Sequencer를 사용하지만, 토큰 스테이킹 등을 통해 이 역할을 유저들에게 넘길 예정

## 🔎 Layer 3
- L2의 거래를 이더리움 L1이 검증하는 것처럼 L3의 거래를 StarkNet L2가 검증
- L3에서는 StarkNet의 요소들을 커스텀 가능
- StarkEx는 장기적으로 Layer 3에 합류할 예정

## 🔎 정리 & 의견
**StarkWare는 StarkNet Token이 개발자 우선이 되도록 설계했다고 언급했다.** StarkNet Token으로 tx 비용을 지불할 수 있는 기능도 그중 하나다. 개발자들이 스마트 컨트랙트를 만들고 거래 수수료로 네이티브 토큰을 얻으면 이를 통해 거버넌스나 스테이킹에 참여할 수 있기 때문이다.

zk Rollup 솔루션을 제공하는 회사들 중 StarkWare는 조금 다른 행보를 걷고 있다. StarkWare는 zkEVM 싸움에 진입할 생각이 없다고 밝혔다. 대신 유저들이 StarkNet 위의 Layer 3에서 EVM 에뮬레이터를 만들 수 있다고 언급했다.

L1의 이더리움이 보안을 제공하고, L2의 StarkNet이 확장성과 속도를 제공한다. L3는 이를 모두 누릴 수 있다. **그리고 L3 체인은 StarkNet L2를 하나의 생태계로 만들 것이다. StarkWare가 zkEVM보다 큰 그림을 그리고 있다고 볼 수 있다.**

그러나 EVM을 네이티브로 지원하지 않는 점은 StarkWare의 초기 생태계 확장에 걸림돌이 될 수 있다. [Solidity에서 Cairo로의 트랜스파일 도구와](https://github.com/NethermindEth/warp) L3의 EVM 에뮬레이션 지원이 대책이 될 수 있다. **이들이 개발자를 끌어들이기 위한 충분한 인센티브가 될지는 지켜봐야 할 것이다.**