---
title: Dark Forest
author: bemodest.eth
date: 2022-08-14 00:00:00 +0900
categories: [Crypto, Gaming, Layer2]
tags: [gaming, layer2]
image:
  path: posts/0814_1.png
  width: 500
  alt: Can a fully on-chain game be a thing?
---

### *취미생활방 서포터즈 활동으로 작성된 게시글입니다.
　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　    
## 🔎 개요
- 이더리움 L2인 Gnosis Chain의 블록체인 MMORPG
- zk-SNARK 기술을 활용해 완전 온체안 게임을 구현
- 게임 플레이를 위해서는 Whitelist Key가 필요

## 🔎 게임 진행 방식
- 우주 공간에서 최대한 많은 행성을 내 것으로 만들어 내 영토를 확장
- 시즌마다 다른 방법으로 최대한 많은 포인트를 쌓기
- 로비를 만들어 내가 원하는 설정의 우주 창조 가능
- [게임 설명 유튜브 동영상](https://www.youtube.com/watch?v=sUtIiVUwB5o&list=PLVdl_HSgIhD4joZHXd2i_AJE0gQDbw11P&index=9)

## 💡 Dark Forest가 특별한 이유
- **완전 블록체인 게임**: 기존 게임의 중앙 DB를 블록체인으로 대체
- **오픈 소스**: [유저가 플러그인을 제작 가능(모딩)](https://plugins.zkga.me/)
- **zk-SNARK**: [온체인 전장의 안개](https://dfwiki.net/wiki/Fog_of_war)를 구현
- **간편한 온보딩**: L2의 낮은 가스비 + 계정 생성 시 게임 플레이를 위한 가스비 에어드랍

## 🔎 전장의 안개(Fog of War)
- 전장에 안개 안에 있는 행성과는 상호작용 불가
- 유저의 이동/행동을 암호학적으로 증명하면서 zk 기술을 통해 자세한 정보를 숨김
- CPU 채굴을 통해 전장의 안개를 걷을 수 있음
- 걷은 전장의 안개 상황을 다른 유저와 공유 가능

## 🔎 Artifact
- 특정 행성(foundry) 탐사를 통해 획득할 수 있는 NFT
- [출금 후 마켓플레이스 플러그인에서 거래 가능](https://darksea.market/)
- 기능: 행성 스탯 조정, 다른 행성 파괴, 행성 보호, 일회성 스탯 증가 등

## 🔎 정리 & 의견
Dark Forest는 기존의 블록체인 게임이라고 불리는 P2E 게임과 다르다. [Dark Forest에는 게임 내에서 직접 돈을 버는 요소가  없다고 밝혔다.](https://dfwiki.net/wiki/Making_Money) **즉, 게임 DB로 블록체인을 사용하는, 중앙화 요소를 제거한 100% 온체인 게임이라고 할 수 있다.**

**Dark Forest는 유저들의 상호작용으로 만들어진 게임 경제가 존재하는 블록체인 게임이라는 점에서 특별하다.** [예를 들어, marketplace 플러그인을 통해 다른 유저들과 행성 좌표를 거래할 수 있고](https://blog.zkga.me/nightmarket), 돈을 받고 CPU 리소스를 제공해 다른 유저의 전장의 안개를 걷어줄 수 있다.

Dark Forest는 "블록체인 기술을 이런 방식으로도 적용할 수 있다"는 것을 보여주는 실험적 성격이 강한 게임이다. 그리고 Whitelist Key가 있어야만 게임을 플레이 할 수 있어서 진입 장벽이 존재한다. 그래서인지 zk 기술과 블록체인에 관심이 많은 개발자 위주로 커뮤니티가 형성되어 있고, 커뮤니티 활성화 정도도 낮았다.

**실험적 단계를 넘어 100% 온체인 게임이 성장하려면 '왜 블록체인인가?'에 대한 답을 제공헤야 한다.** Dark Forest 다음의 100% 온체인 게임은 블록체인을 DB로 사용함으로써 얻을 수 있는 추가 가치가 있다는 것을 보여줘야 한다. 이것이 없는 100% 온체인 게임은 호기심 많은 개발자들의 실험에서 벗어나지 못할 것이다.