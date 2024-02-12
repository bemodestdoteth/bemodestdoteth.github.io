---
title: NFT Lending Platforms
author: bemodest.eth
date: 2022-08-19 00:00:00 +0900
categories: [Crypto, NFT, DeFi]
tags: [nft, defi]
image:
  path: posts/0819_1.png
  width: 500
  alt: A cascade of liquidation looming on NFT
---

### *취미생활방 서포터즈 활동으로 작성된 게시글입니다.
　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　    
## 🔎 개요
• NFT를 담보로 맡기고 돈을 빌리는 프로토콜
• 주요 프로토콜: [NFTfi](https://www.nftfi.com/)(P2P), [NFTX](https://nftx.io/)/[BendDAO](https://www.benddao.xyz/)(Pool)

## 🔎 P2P 대출 방식
1. Lender가 대출 금액과 이자율을 정해 Borrower에 Offer 제시
2. Borrower가 Offer를 승인하면 대출 진행
3. Borrower가 돈을 갚을 수 없는 상황이라면(디폴트) Lender는 대출금 대신 담보로 잡힌 NFT 획득

## 🔎 [지표](https://dune.com/rchen8/NFTfi)
- NFTfi 총 대출 금액: 약 1840만 달러
- Lender 평균 APY: 58%
- 평균 대출 지속 기간: 32일
- 대출 디폴트 비율: 약 10%

## 🔎 Pool 대출 방식
1. Lender: 풀에 유동성을 공급하고 이자를 받음
2. Borrower: NFT를 담보 FP의 40%까지 풀의 유동성에서 대출
3. 담보 NFT FP가 대출금의 111% 이하로 떨어지면 청산(90% LTV)
4. 48시간의 청산 유예: [유예 기간 동안 청산 경매가 진행됨](https://www.benddao.xyz/app/auction/available-to-auction)
5. 유예 기간 내에 Borrower가 대출을 갚으면 청산을 피할 수 있음
6. 48시간이 지나면 경매 최고 입찰자가 대출을 갚고 NFT를 가져감
7. **48시간 내에 입찰자가 없다면 프로토콜이 해당 NFT를 직접 소유**

## 🔎 [지표](https://dune.com/cgq0123/Bend-DAO)
- BendDAO 총 대출 금액: 16,110 ETH (약 2800만 달러)
- Lender 평균 APY: 6%
- Borrower 평균 APY: 16%

## 💡 NFT의 연쇄 청산?
최근 블루칩 NFT의 FP가 지속해서 감소했다. **P2P 방식 대출은 FP 하락에 큰 영향을 받지 않는다.** 바뀐 FP에 따라 Borrower와 Lender의 대출 조건도 바뀌기 때문이다. 부실 대출이 발생하더라도 FP가 감소한 NFT를 각 Lender들이 떠안으므로 리스크가 분산된다.

**하지만 Pool 방식 대출은 프로토콜이 모든 리스크와 FP 감소분을 떠안게 된다.** FP 감소세가 지속된다고 생각하면 청산 경매에 올라오는 NFT에 아무도 입찰하려고 하지 않을 것이기 때문이다. **그리고 NFT를 떠안은 BendDAO가 빚을 갚으려고 NFT를 팔아 FP를 더 낮춘다면 더 많은 청산이 발생하게 된다.**

## 🔎 정리 & 의견
**[19일 자정 즈음 BAYC가 BendDAO 청산 경매에 처음으로 등장했다.](https://twitter.com/CirrusNFT/status/1560291009145102336)** 그리고 BAYC FP가 72 ETH에서 1 ETH만 떨어져도 6개의 BAYC가 추가로 경매에 올라오게 된다. [BendDAO 사이트에서 청산 경매가 임박한 NFT 리스트를 확인할 수 있다.](https://www.benddao.xyz/app/auction/health-factor-alert-list)

연쇄 청산뿐만 아니라 BendDAO의 지속 가능성도 문제가 될 수 있다. 청산 경매 입찰자가 없으면 프로토콜이 빚을 떠안는데, NFT의 FP가 지속해서 감소하면 NFT의 가치가 대출금보다 낮아지는 순간이 찾아오기 때문이다. **아직 BendDAO의 LTV는 200% 정도지만. BendDAO 담보 가치의 2/3를 차지하는 BAYC가 경매에 올라간 지금부터가 중요한 시점이다.**

이다음이 어떻게 진행될지는 시장 참여자들의 행동에 달려 있다. BAYC 경매가 활발하게 진행된다면 연쇄 청산 문제는 아무 일 없이 넘어갈 것이다. 그러나 연쇄 청산을 기대하고 경매에 참여하지 않는 사람들이 많아진다면...