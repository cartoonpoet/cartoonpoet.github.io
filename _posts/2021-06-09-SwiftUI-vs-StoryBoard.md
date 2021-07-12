---
layout: post
title: SwiftUI vs StoryBoard
subheading: SwiftUI vs StoryBoard
author: JunHo
categories: SwiftUI
banner: https://bit.ly/32PAjtM
tags: IOS AOS iphone ipad mac swift storyboard 아이폰 애플 apple 
comments: true
sitemap :
  changefreq : daily
  priority : 1.0





---



## SwiftUI란?

---

![1_4fDVdzPaeC7IqiW3R1YhAg](https://user-images.githubusercontent.com/38898759/123971440-017b3a00-d9f5-11eb-94ec-36a7e67735d1.png)

- SwiftUI는 모든 Apple 플랫폼에서 사용자 인터페이스를 구축할 수 있는 방법 중에 하나이다.  즉, 하나의 도구 및 API로 모든 애플 기기의 UI(사용자 인터페이스)를 만들 수 있게 해준다. 

- SwiftUI는 선언적 구문을 사용한다. 예를 들어, 텍스트 필드로 구성된 항목의 목록을 작성한 후 각 필드의 정렬, 서체 및 색상을 쓰면 된다.





## SwiftUI vs StoryBoard

---

![1_Xj68-FcLd1vvC1Ck9A9F2Q](https://user-images.githubusercontent.com/38898759/123971722-41dab800-d9f5-11eb-84b8-f2c44c2111cf.png)

SwiftUI는 WWDC 19에서 발표가 되었다.  출시된지 얼마 되지 않아 관련 자료들이 스토리보드에 비해 상당히 부족한 편이다. 그러나 SwiftUI 방식은 코드 자체의 버그와 코드양이 상당히 줄어든다.  현재 나도 SwiftUI를 입문한지 얼마 되지는 않았지만 진짜 이게 맞나 싶을 정도로 UI를 구성하는데 코드양이 짧고 간결하다. 최근 맥쓰사 카페에서 검색을 해본 결과 애니메이션 구현이 정말 쉽다는 [글](https://cafe.naver.com/inmacbook/2417055)을 발견했다.

그리고 아직까지 대세는 스토리보드를 이용한 개발인 것 같다. 왜냐하면 나온지도 오래되었고 드래그앤드랍 만으로도 UI 구현이 가능하다는 것.. 그런데 곧 있으면 SwiftUI로 넘어가는 시기가 올 것 같다. 스토리보드를 이용한 개발 방법은 대형 프로젝트에서는 적합하지 않다. 앱은 웹에 비해서 상당히 많은 뷰를 요구한다. 따라서 뷰가 많으면 많을 수록 스토리보드를 불러오는데 시간이 오래 걸리게 되고 이러한 현상은 생산성이 떨어지는 것을 의미한다. 하지만 SwiftUI는 소형, 대형 프로젝트에도 적합하고 각각의 뷰에 프리뷰 기능을 제공하기 때문에 스토리보드와 같은 현상은 없다고 볼 수 있다.

또 SwiftUI는 IOS 13부터 지원한다.  지금 진행하고 있는 프로젝트는 minimum target을 IOS 14로 지정하여 개발을 하고 있다. IOS 13부터 지원을 하려고 했으나 왜인지 모르겠으나..  IOS 13에서 지원하지 않는 코드라고 오류가 발생한다. 그래서 14로 타겟을 잡았다. 

내가 생각하기엔 소규모 프로젝트이며 빠르게 개발을 해야하는 것이면 StoryBoard 방식이 좋을 것 같다는 생각이다. 만약 대규모 프로젝트이며 추후 유지보수 같은 것을 또 생각하면 SwiftUI 방식이 좋을 것 같다.





## 마무리

---

SwiftUI는 최신버전의 IOS에서만 작동하며 개발이 가능하다. 이미 수많은 앱들은 스토리보드 방식 또는 오브젝티브 C로 개발이 되어있다. 현재 아직은 스토리보드에 비해 SwiftUI 관련 문서가 턱없이 부족하다. (특히 한글 자료는 더욱 더) 훗날 미래에는 스토리보드 방식에서 SwiftUI 방식으로 개발 방식이 대체될 것이라 생각 된다. 물론 시간이 되면 스토리보드 방식과 SwiftUI 방식을 둘다 익히는 것이 좋겠지만 상황에 맞게 잘 선택하여 개발하는 것이 중요하다고 판단된다.

