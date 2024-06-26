---
title: Giving Birth to a NFT
author: bemodest.eth
date: 2022-03-03 00:00:00 +0900
categories: [Crypto, NFT, Development]
tags: [nft, development]
image:
  path: posts/0303_1.png
  width: 500
  alt: Building a NFT Collection from the scratch
---

# **들어가기 앞서**

최근 학교에서 팀원들과 블록체인 스터디를 하고 있습니다. 학기 초에 블록체인 학회원을 모집하고 그들을 위한 NFT를 발행하는 프로젝트를 진행 중에 있습니다. 저는 블록체인 쪽은 아니지만 개발 경험이 조금이나마 있어 팀원 한 분과 함께 NFT 개발 쪽을 맡기로 했습니다.

개발에 주어진 시간은 일주일 정도였습니다. 호기롭게 시작했지만, 생각대로 흘러가지 않았습니다. 마감 시한을 맞추기 위해 밤을 새우기도 했습니다. 노력한 결과 완벽하지는 않지만, 어느 정도 짜임새 있는 컨트랙을 완성했습니다. 아무것도 모르는 상태에서 시작한 제가 어떻게 컨트랙을 만들었는지, 어떤 점을 느꼈는지 간략하게 정리하고자 합니다.

## **● 짤막한 개발 경력**

본문에 앞서 간략하게 제 개발 경력을 소개해 드리고자 합니다. 문과생이라 처음 대학 2년 동안은 개발과 등을 지고 지냈습니다. 경제학과다 보니 `R`이나 `stata`같은 통계 프로그램은 접한 기억이 있긴 했지만, 크게 관심을 가지지는 않았습니다. 그러다가 군대에서 개발에 본격적인 관심을 갖게되었고, 10월에 전역하고 복학까지 남은 시간 동안 "뭐라도 만들어보자"라는 마음가짐으로 개발을 시작했습니다.

그렇게 시작해서 처음 접한 언어는 C#이었습니다. 많고 많은 언어 중 굳이 C#을 고른 이유는 메이플 매크로를 만들고 싶다는 생각 때문이었습니다. 그 생각 하나로 개발 배경지식 없이 무작정 부딪히면서 개발을 이어나갔습니다. 3개월 동안 붙잡았음에도 완성된 프로그램을 만들지는 못했지만, 개발에 재미를 붙일 수 있는 계기가 되었습니다.

직접 부딪힌 경험 이후로 제대로 된 교육의 필요성을 느꼈습니다. 그래서 2021년에는 학교 수업으로 파이썬과 C++을 배웠습니다. 파이썬 수업에서는 웹 크롤링을 통해 텔레그램 알림을 쏴 주는 완성된 프로그램까지 하나 만들어 지금까지 잘 써먹고 있습니다.

보시는 것처럼 작은 개인 프로젝트 경험은 조금이나마 있지만, 팀 단위로 굵직한 개발 경험은 없었습니다. 거기다가 솔리디티는 거의 처음 접하는 상황이었습니다. 말 그대로 맨땅의 헤딩이었습니다.



## **● Flowchart**

원래는 실제 코딩 전에 어떻게 프로그램을 구현해야 할지 간단하게 플로우차트를 그려봅니다. 플로우차트를 그리다 보면 생각 정리도 되고 각 단계에 어떤 라이브러리가 필요한지도 알 수 있거든요. 그러나 이번 NFT dApp은 배경지식이 거의 없어서 개발을 마치고 나서 플로우차트를 그렸습니다. 다 그리고 나서 보니 과정 자체는 많지 않았는데 처음 가는 길을 헤매느라 소비한 시간이 꽤 많았던 것 같습니다.

원래 계획은 `web3 integration`까지 진행해 카이카스 지갑을 연동하는 웹사이트를 만드는 것까지였습니다. 그러나, 시간 관계상 컨트랙 배포까지만 진행하고 실제 NFT 전달은 web3를 통하지 않고 지갑 주소를 받아서 직접 진행하는 것으로 팀원과 결론을 냈네요.

> #### **혹시나 제가 본문에 잘못 적은 정보가 있다면 트위터 덧글로 알려주세요!! <br> 피드백에 언제나 열려 있는 사람입니다!!**

## **● Generate NFT Arts & Metadata**

> ### **카카오톡: 숨겨진 복병**

NFT 프로젝트의 시작은 PFP part를 합쳐 하나의 완성된 그림을 만드는 코드를 작성하는 것입니다. 파이썬으로 코드를 작성하고 그림 샘플을 받아서 테스트하는데, 각각의 part가 합쳐지지 않고 덮어 씌워지는 문제가 발생했습니다. 처음에는 그림을 합치는 라이브러리 문제인가 싶어 라이브러리를 `Images` 대신 `cv2` 로 교체했습니다. 그 결과 합쳐지기는 했지만 부자연스러운 흰색 윤곽선이 남는 또 다른 문제가 생겼습니다.

그렇게 오류의 원인을 찾다가 파일 형식 자체를 의심하게 됐습니다. 그림을 합치려면 기본적으로 배경이 투명해야 할 것 같은데, 흰색 배경이 있었거든요. 결국 원인을 찾았는데, **카카오톡 단톡방에 올라간 PFP part 그림을 받아서 생긴 문제였습니다...** 그림 자체에는 문제가 없었는데, 카카오톡에 올라가면서 투명성이 손실된 jpg 파일로 자동 변환이 되었습니다. 디자이너님한테 원본 파일을 받아서 해결했습니다.

기본적인 문제였지만 협업 중에 종종 생길 수 있는 문제 같다는 생각도 들었습니다. 그리고 **오류의 원인이 아무도 예상 못 한 곳에서 나오는 사례 중 하나**가 될 수도 있겠네요.

> ### **NFT Metadata**

PFP part를 조합해 NFT를 만들 때, 해당 그림의 메타데이터가 담긴 `json` 파일도 같이 만들어집니다. `"image":` 부분에 메타데이터의 Id에 해당하는 그림 이미지 링크를 지정합니다. NFT가 민팅될 때, 그 NFT의 Id에 해당하는 메타데이터의 `URI`가 `return`됩니다. **즉, 메타데이터는 NFT와 그림을 연결하는 파일이라고 볼 수 있습니다.**

```(json)
{
    "name": "Sample NFT",
    "description": "Sample NFT Description.",
    "tokenId": 1,
    "image": "https://ipfs.io/ipfs/****/1.png",
    "attributes":
    [
        {
            "trait_type": "key",
            "value": "value"
        }
    ]
}
```

그림과 메타데이터가 클라우드 상에 저장되어 있어야 민팅 때 토큰이 메타데이터를 잘 참조할 수 있을 것입니다. 이를 위해 보통 `ipfs`와 `pinata`가 많이 쓰였습니다. 쓰기 쉽고 무료 서비스이고 탈중앙 서비스라 서버가 다운될 걱정도 없다는 장점이 있지만, 한번 올라간 파일을 수정할 수 없다는 단점도 존재합니다.

다른 방법으로 `Amazon s3`도 있었습니다. 메타데이터의 수정이 가능하다는 장점이 있지만, 중앙화된 서비스라 서버 다운의 위험성이 있고 `ipfs`보다 쓰기 어려웠습니다. 유료라는 가장 큰 단점도 있죠. **대부분의 NFT 프로젝트가 `ipfs`를 사용하는 것에는 쓰기 쉽고 무료라는 것이 매우 크게 작용하는 것 같습니다.**

> ### **How to Reveal NFT**

플로우차트에 나와 있듯이, **NFT를 전달할 때 리빌 방식을 사용하기로 결정했습니다.** 개발이 늦어져 web3 사이트를 만들지 못하면 지갑으로 직접 NFT를 보내야 합니다. 그런데 보내는 NFT의 trait이 공개된 상태라면 공정성 문제가 일어날 수 있으니까요. 그래서 처음 NFT를 보낼 때는 리빌 전 이미지를 보내고 특정 블록 높이에서 리빌을 통해 trait을 공개하기로 팀원분과 의견을 모았습니다.

NFT 리빌 방법은 크게 두 가지가 있었습니다.

#### 　　**1. 메타데이터 업데이트 <br> 　　 2. 소각 후 다시 민팅 (이주)**

**NFT를 '이주'하는 2번 방법은 많은 가스를 요구하지만 한번 올라간 메타데이터의 수정이 불가능한 `ipfs`에서 쓸 수 있는 거의 유일한 리빌 방법이었습니다.** 시행착오 끝에 `ipfs`에 파일을 올리고 2번 방법으로 리빌하기로 결정했습니다. 클레이튼의 매우 낮은 가스비와 민팅 수량이 많지 않다는 것도 이 결정에 한 몫 했죠.

_(현재 클레이튼 테스트넷에 적용된 가스비 30배 인상이 메인넷에 적용되면 대규모 NFT 이주는 힘들어지긴 할 것 같습니다.)_

## **● 컨트랙 작성, 컴파일, 배포**

> ### **스마트 컨트랙과 인공위성**

대부분의 인터넷 튜토리얼이 NFT 민팅 컨트랙 작성에 초점이 맞춰져 있어서 컨트랙 작성 자체는 아주 어렵지 않았습니다. `ERC-721`과 `KIP-17`같이 관련 표준도 잘 정립되어 있기도 했습니다. 당장은 시간 문제로 `KIP-17`를 사용했는데, 시간이 되면 `ERC-721`도 써 보고 싶네요.

제게는 컨트랙 작성보다 컨트랙을 컴파일하고 배포하는 환경을 구성하는 것이 더 어려웠습니다. 스마트 컨트랙을 작성하고, 컴파일하고, 배포까지 마치면서 느꼈던 점이 하나 있는데, **dApp 하나를 만드는 과정이 마치 인공위성 하나를 쏘아 올리는 과정 같았습니다.**

인공위성이 궤도에 올라가는 것처럼 컨트랙도 블록체인에 올라갑니다. 그리고 블록체인에 올라간 컨트랙은 이미 쏘아 올린 인공위성처럼 수정이 불가능합니다. 인공위성을 최대한 가볍게 만드는 것처럼 컨트랙도 불필요한 코드를 빼고 최대한 가볍게 만들어야 했습니다. 컨트랙이 커질수록(코드의 양이 많아질수록) 블록체인에 올리는 비용이 크게 증가했습니다.

> ### **트러플? 하드햇? IDE?**

그리고 인공위성을 쏘아 올리기 위해 로켓과 발사대가 필요한 것처럼, 컨트랙을 가상 머신이 읽을 수 있도록 컴파일하고 블록체인에 배포하는 도구가 필요했습니다. 개인적으로 이 과정에서 많이 헤맸고, 확실하게 정리해야겠다는 생각이 들었습니다.

처음에는 트러플을 사용했습니다. config 파일을 만들고, migration 파일도 만들고 어찌어찌 컴파일과 배포까지 했습니다. 그런데 배포한 컨트랙을 테스트하기 위해서는 또 추가로 코드를 작성해야 했습니다. 결국 이 부분에서 막혀 다른 방법을 찾던 중, 잊고 있었던 IDE를 팀원분이 알려주셔서 IDE를 사용했습니다.

**입문자 입장에서 컴파일, 배포, 테스트의 편의성은 IDE가 압도적이었습니다.**

`remixd`를 이용해 로컬 컴퓨터와 IDE를 연결하니 컴파일과 배포가 빛의 속도로 진행됐습니다. 트러플를 써보겠다고 며칠간 헤맸던 것을 2시간 만에 모두 해결했습니다. 트러플과 하드햇은 컴파일, 배포, 테스트를 위한 별개의 자바스크립트 코드가 필요합니다. **반면 IDE는 컨트랙 작성만 하면 추가 코드 없이 컴파일, 배포, 그리고 컨트랙 콜 테스트까지 가능하니 편의성이 차원이 달랐습니다.**

한 가지 번거로운 점은, 클레이튼 IDE에서는 테스트용 지갑을 직접 만들어서 import해야 했습니다. 이더리움에서 썼던 `remix`는 100이더가 담긴 지갑 여러 개를 기본으로 지원했는데 이 점은 조금 아쉬웠습니다. 다만 이것도 트러플은 테스트를 위해 `ganache`로 수동으로 지갑을 지정해야 했던 것을 생각하면 훨씬 편하다고 생각합니다.

그리고 IDE가 웹상에 있어 완한 로컬 환경은 아닌데, 여기서 IDE에 개인 키를 올려 지갑을 import하는 부분도 문제가 될 수 있다는 생각이 들었습니다. 완전한 로컬 테스트을 위해 결국 트러플이나 하드햇이 필요할 것 같습니다. **인공위성 사례를 다시 빌려 요약하자면, IDE는 이미 완성된 발사대를 빌리는 것이라면, 트러플과 하드햇은 발사대를 만든다고 보면 될 것 같습니다.**

> ### **web3 Integration**

처음에는 민팅 컨트랙을 호출하는 web3 페이지 제작까지 계획에 있었습니다. 그러나, 컨트랙 테스트에 시간이 지체되면서 결국 web3 페이지를 따로 만들지 않기로 결정했습니다. 덕분에 web3 부분은 아직 제게 미지의 영역으로 남아있습니다... 이제는 시간에 얽매이지 않기 때문에 프론트 공부를 하면서 천천히 web3 공부도 진행할 예정입니다.

# **글을 마치며**

일주일 동안 개발에 집중하면서 다른 일은 다 제쳐두고 정말로 개발만 한 것 같네요. 시간이 잘 간다는 것이 개발의 장점이자 단점 같습니다. 블록체인 dApp 개발을 이번에 처음 맡으면서 배운 점도 많았고 아쉬운 점도 많았지만, 아쉬운 점이 더 많았던 것 같습니다.

### **블록체인 개발이라고 해서 완전히 새로운 것이 아니다. 스마트 컨트랙은 dApp의 한 부분일 뿐이다.**

특히 dApp 개발에 솔리디티보다 결국 기존의 프로그래밍 지식이 더 중요하다는 것을 뼈저리게 느꼈습니다. **솔리디티로 만든 컨트랙은 dApp에 올라가는 인공위성 뿐이지 dApp을 올리는 발사대는 기존의 프로그래밍 언어로 만드니까요.** 솔리디티에도 막히고 프론트에도 막혀 민팅 페이지를 시간 내에 만들지 못하고 마무리한 것이 많이 아쉬움이 남았습니다.

dApp 개발을 진행하면서 솔리디티 공부가 아닌 프론트 공부의 필요성을 느꼈습니다. 일주일 동안 맨땅의 헤딩을 통해 블록체인 개발 환경을 익혔으니 이제는 체계적으로 프론트 쪽을 등을 공부하려고 합니다. 부트캠프도 생각하고 있고요. 프론트 쪽에 눈을 트이고 난 다음에 블록체인 개발 공부의 다음 페이지를 시작하는 게 더 효율적일 것 같습니다.

### **블록체인 개발을 원하신다면**

블록체인 개발에 생각이 있으시다면, 당장은 솔리디티 컨트랙 공부보다 자바스크립트, 리액트 등을 공부하는 것이 더 효율적일 것 같습니다. 컨트랙 부분은 레퍼런스가 많고 작동 원리도 크게 어렵지 않았습니다. 그러나, 그 컨트랙을 블록체인에 올리기 위한 발사대 부분은 프론트 지식이 부족한 상태에서는 레퍼런스만 보고서 작동 원리를 알기가 어려웠습니다. web3 부분도 크게 다르지 않을 것으로 생각합니다.

**컨트랙을 만드는 것은 솔리디티와 IDE면 충분하지만, 완성된 dApp을 만들기 위해서는 프론트 지식이 필수라는 생각이 들었습니다.** 발사대를 계속 빌려서 인공위성을 쏘아 올릴 수는 없으니까요. 시간이 급해 발사대를 빌리더라도 적어도 작동 원리는 알고 직접 발사대를 만들 수 있는 상태여야 할 것입니다.

이번에는 아는 것이 별로 없어서 블록체인 개발을 접하고 반쪽짜리 dApp을 만든 소감 정도로 마무리되었습니다. 더 공부해 저처럼 블록체인 개발에 입문하는 분들을 위한 더 자세한 글을 적고 싶네요. 그리고 시간 때문에 타협했던 부분들도 천천히 수정하고 싶네요.
