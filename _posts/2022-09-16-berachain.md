---
title: Berachain
author: bemodest.eth
date: 2022-09-16 00:00:00 +0900
categories: [Crypto, Layer1, DeFi]
tags: [layer1, defi]
image:
  path: posts/0916_1.png
  width: 500
  alt: Bera squads changes DeFi ecosystem
---

### *취미생활방 서포터즈 활동으로 작성된 게시글입니다.
　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　    
## 🔎 개요
- Cosmos SDK를 기반으로 하는, EVM 호환, DeFi 중심 L1 블록체인
- Proof of Liquidity(PoL)이라는 새로운 합의 알고리즘을 사용
- 10~11월 테스트넷 출시 예정

## 💡 Berachain의 3중 토큰 구조
**1. BERA**
- Berachain의 네이티브 토큰
- 스테이킹을 통한 네트워크 유지, 가스비 지불에 사용됨

**2. HONEY**
- Berachain에서 사용되는 스테이블코인
- 초과 담보를 통한, DAI와 비슷한 방식으로 발행
- 네트워크 유지를 위해 스테이킹한 자산을 HONEY 민팅의 담보로 활용

**3. BGT(Bera Governance Token)**
- 스테이킹한 BERA를 락업하면 얻을 수 있는 거래 불가능 NFT
- Berachain의 의사 결정 과정에 참여 가능

## 💡 Proof of Liquidity(PoL)
- PoS를 기반으로 새로운 유동성 메커니즘 추가
- BERA, BGT뿐만 아니라 다른 L1 토큰, 스테이블코인, DeFi 토큰도 스테이킹 가능
- 스테이킹 자산을 여러 DeFi 프로토콜에 활용 가능
- 스테이킹 보상으로 블록 보상(BERA)뿐만 아니라 각종 DeFi 프로토콜에서 나오는 수수료(HONEY)도 획득

## 🔎 활용처 1: Berachain DEX
- 모든 토큰의 페어가 HONEY와 연결되는 탈중앙 거래소

  → 모든 토큰이 USDT와 연결되는 CEX의 현물 거래소와 비슷한 개념

  → HONEY가 거래의 중간자 역할을 함으로써 유동성 문제와 자본 효율성 문제를 해결 가능 + HONEY 사용성 증가

## 🔎 활용처 2: 토큰 대출
- 스테이킹 자산을 담보로 HONEY 대출(민팅)

  → 최대 LTV: 150%

  → 청산 시 스테이킹 자산은 프로토콜 Vault로 이동

- 스테이킹 자산을 담보로 레버리지 포지션 진입

  → 무기한 선물 거래소. 펀딩 피는 HONEY로 지불 또는 획득

## 🔎 정리 & 의견
Berachain은 meme NFT에서 시작했다. 다수의 NFT 컬렉션을 발행했고, 기존 NFT 홀더들에게 다수의 물량이 에어드랍되었다. [작년 8월 민팅한 첫 번째 NFT 컬렉션은 30 ETH가 넘는 가격에 거래되고 있다.](https://opensea.io/collection/bongbears/activity) 추가적으로 NFT 홀더는 Berachain에서 보상을 받을 것으로 예상되지만, 어떤 보상을 지급할지는 밝히지 않았다.

스테이킹된 자산을 DeFi에 활용한다는 개념은 DeFi 생태계에 무한한 가능성과 새로운 가치를 가져다줄 수 있다. [Berachain 출시에 앞서 수많은 신규 프로젝트가 개발되고 있다.](https://twitter.com/OSINTDAO/status/1568025521535209472) [그리고 Redacted Cartel, Synapse를 포함한 여러 기존 프로젝트들도 Berachain 지원을 준비하고 있다.](https://twitter.com/FWCrypto_/status/1562983845388902400)

Cosmos의 Tendermint 합의 알고리즘은 언스테이킹에 21일을 요구한다. Tendermint를 사용하는 Berachain도 동일할 것이다. 테라 붕괴 당시 루나 스테이커들은 긴 언스테이킹 기간으로 인해 자산이 녹아내리는 것을 두 눈으로 지켜볼 수밖에 없었다. Tendermint로 인한 유동성 문제를 해결하기 위해 스테이킹 자산 유동화 토큰인 stLUNA와 비슷한 토큰이 Berachain에 나올 수 있을 것이다.

그리고 HONEY가 네트워크에 중요한 위치를 차지할 수록 보안에도 신경 써야 할 것이다. 특히 체인 코어 레벨에 존재하는 DeFi 프로토콜의 취약점은 체인의 존속에 영향을 미칠 만큼 치명적일 수 있다.