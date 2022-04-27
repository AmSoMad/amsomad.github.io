---
title: "[디자인]Web개발 필요한 사이트 모음 - 22.04.27"
excerpt: "디자인부터 기능 라이브러리까지 모아보자"

categories:
  - 유틸리티
  
tags:
  - [디자인, Web, 유틸리티]

permalink: 

toc: true
toc_sticky: true
 
date: 2022-03-09
last_modified_at: 2022-04-11
---

# 🐐 Web개발 필요한 사이트 모음

> 계속해서 추가해보자.

# 1️⃣ Color 색상

## Adobe Color

> [https://color.adobe.com/ko/trends](https://color.adobe.com/ko/trends)
> 
> 색의 조합이나 기본적으로 내눈은 막눈이다 싶으면 여기서 보자 <br>
>  - Adobe Color -> 트랜드 부분에서 내가 원하는 색조합을 쓰자.

## Converter.App

> [https://converter.app/ko/rgb-to-hex/](https://converter.app/ko/rgb-to-hex/)
> 
> 해당 앱은 Hex 컬러값을 RGB값을 혹은 그반대로 변경이 된다.<br>
>  - CSS조절할때 진짜 더럽게 구찮을때 많다. 자주쓴다.

## 2 Colors Combinations

> [https://2colors.colorion.co/](https://2colors.colorion.co/)
> 
> 2가지 색상으로 PPT 발표때나 쓰기 좋은 색의 조합을 공유해준다.<br>
> 첫페이지의 색상조합을 쓰기 아주좋은 조합의 색상을 공유해준다.
>  - CSS조절할때 진짜 더럽게 구찮을때 많다. 자주쓴다.

## material.colorion

> [https://material.colorion.co/](https://material.colorion.co/)
> 
> 5가지 색의 조합을 알려준다.<br>
> adobe Color의 트랜드와 비슷해보이나 카테고리화는 안되어있다.
>  - CSS조절할때 진짜 더럽게 구찮을때 많다. 자주쓴다.

## Gradientbuttons.Colorion

> [https://gradientbuttons.colorion.co/](https://gradientbuttons.colorion.co/)
> 
> 그라데이션효과가 들어간 버튼을 보여준다. 심지어<br>


```css
  .btn-grad {background-image: linear-gradient(to right, #E8CBC0 0%, #636FA4  51%, #E8CBC0  100%)}
  .btn-grad {
    margin: 10px;
    padding: 15px 45px;
    text-align: center;
    text-transform: uppercase;
    transition: 0.5s;
    background-size: 200% auto;
    color: white;            
    box-shadow: 0 0 20px #eee;
    border-radius: 10px;
    display: block;
  }

  .btn-grad:hover {
    background-position: right center; /* change the direction of the change here */
    color: #fff;
    text-decoration: none;
  }
```  

> 이렇게 소스를 깔끔하게주니 편리하다.
>  - 이또한 특별한 버튼에 주면좋을거 같다.

        

# 2️⃣ Icon 아이콘

## Emoji

> [https://www.emojiall.com/ko](https://www.emojiall.com/ko)
> 
> 이모지이 모티콘를 추가하여 딱딱한 문구를 해소하자 <br>
>  - 잘 찾아봐야한다. 버전마다 그림이조금씩 다르다.

## XEICon

> [https://xpressengine.github.io/XEIcon/index.html](https://xpressengine.github.io/XEIcon/index.html)
> 
> 17년도가 마지막 업데이트이긴 하나 아직 깔끔하다. <br>
> github : [https://github.com/xpressengine/XEIcon](https://github.com/xpressengine/XEIcon)

## ionicons

> [https://ionic.io/ionicons](https://ionic.io/ionicons)
> 
> 아직 업데이트가 되고있다 <br>
> github : [https://github.com/ionic-team/ionicons](https://github.com/ionic-team/ionicons)

## flaticon

> [https://www.flaticon.com/free-icons/library](https://www.flaticon.com/free-icons/library)
> 
> 여러종류의 아이콘들이많다. 상황에따른 특수한 버튼은 여기서찾자.<br>

## fontawesome

> [https://fontawesome.com/](https://fontawesome.com/)
> 
> fontawesome 너무 유명하니 설명은 필요없지 싶다..<br>
> 심지어 글을쓰는 지금도 깃허브에 커밋됬다. <br>
> github : [https://github.com/FortAwesome/Font-Awesome](https://github.com/FortAwesome/Font-Awesome)

## Google fonts - icons

> [https://fonts.google.com/icons](https://fonts.google.com/icons)
> 
> fontawesome 너무 유명하니 설명은 필요없지 싶다..<br>
> 심지어 글을쓰는 지금도 깃허브에 커밋됬다. <br>
> github : [https://github.com/FortAwesome/Font-Awesome](https://github.com/FortAwesome/Font-Awesome)

## boxicons

> [https://boxicons.com/](https://boxicons.com/)
> 
> boxicons 아이콘은 버튼의 움직이는 효과도 넣을 수 있다.<br>
> 상하좌우 반전 혹은 360도 회전 등등 가능하다. <br>
> github : [https://github.com/atisawd/boxicons](https://github.com/atisawd/boxicons)

## freeicons

> [https://freeicons.io/](https://freeicons.io/)
> 
> 우료아이콘도 있다 허나 가격이 크게 비싸지는않다. <br>
> 사이트의 컨셉에따라 혹은 산업별 전문아이콘들이 많다.<br>
> 만약 전문적인걸 표현할 아이콘이라면 여기서찾자. <br>
> github : [https://github.com/atisawd/boxicons](https://github.com/atisawd/boxicons)

## icomoon

> [https://icomoon.io/](https://icomoon.io/)
> 
> 총 3가지형태의 아이콘중 무료, 유료 2가지씩 공개되어있다. <br>
> 무료버전이래도 특수한 용도로 쓰기 좋은 아이콘이 많다.<br>

#


# 3️⃣ 디자인 & Template

## 웹쟁이

> [https://www.webjangi.com/](https://www.webjangi.com/)
> 
> 여럿 사이트의 디자인을 모아서 보여준다.<br>
>  - 디자인시안을 찾거나 하면 볼만하다 국내에서 유일하지 싶다.

## dribbble

> [https://dribbble.com/](https://dribbble.com/)
> 
> 진짜 첫페이지부터 디자인경합장 같다는 말만 나온다.<br>
>  - 해외 디자이너에게 일감을 줄 수도 있다. 영어를 잘하자.

## codepen

> [https://codepen.io/](https://codepen.io/)
> 
> 코드를 치고 그즉시 볼수 있는 사이트이다.<br>
> javascript도 가능하기에 기능의 일부를 여기서 해결하기도 한다.
>  - 여기도 좀 경합장느낌이다. 다 이뻐보인다.

## creative-tim

> [https://www.creative-tim.com/](https://www.creative-tim.com/)
> 
> UI 키트를 판매하거나 템플릿을 판매하기도한다. 물론 무료공개도 있다.<br>
> 커스텀된 템플릿들이 언어마다 있다 모두가 좋아할 것같다..
>  - 돈을 주더라도 가지고싶은 쓸만한 디자인들이 많았다.

#

# 4️⃣ 배경이미지

## Pixabay

> [https://pixabay.com/ko/](https://pixabay.com/ko/)
>
> 무료 <br>
> 원하는 분위기의 느낌을 검색하면 사진들이 많이들 올라온다.<br>
> 자주 들어가보게 된다.

## WallpapersCraft

> [https://wallpaperscraft.com/](https://wallpaperscraft.com/)
>
> 무료 <br>
> 정말 많이있고 이미지크기를 다양하게 제공해주고 있다.<br>
> 여기도 자주 들어가보게 된다.

## wallpaperhub

> [https://wallpaperhub.app/](https://wallpaperhub.app/)
>
> 무료 <br>
> MS사 윈도우 배경화면으로 나온이미지를 다운받을 수 있다.<br>
> 상당히 고퀄리티다.


#

# 5️⃣ 라이브러리

## mo.js

> [https://mojs.github.io/](https://mojs.github.io/)
>
> Mo.js 이건 Canvas를 이용해서 로고를 만들거나 차트를 그리는 등 <br>
> 모션그래픽에 특화된 라이브러리이다. 이건 들어가보면 맘에 들것이다.<br>
> 독단적으로 동작을 하니 기존 프레임에 깨지는 현상을 없을것 같다. <br>
> 계속해서 업데이트는 되고있다. 출범한지 얼마안된 라이브러리이니 <br>
> 발전 가능성이 무궁무진하다. 
>  - 난 이 라이브러리의 관심이 아주 많다.
> 
> github : [https://github.com/mojs](https://github.com/mojs)

## anime.js

> [https://animejs.com/](https://animejs.com/)
>
> mo.js 를쓰냐 anime.js를쓰냐 비교대상의 라이브러리<br>
> 애니메이션 처리를 위한 라이브러리이다.<br>
> codepen에서 자주볼수있는 애니메이션처리 라이브러리 이니 현재 자주쓰이는듯 하다
> github : [https://github.com/juliangarnier/anime](https://github.com/juliangarnier/anime)

## Lottie.js

> [https://airbnb.io/lottie/#/](https://airbnb.io/lottie/#/)
> 
> 요즘 디자이너분들이 많이쓰는 라이브러리다.<br>
> Adobe After Effects를 사용하여 그린 이미지를 Json 타입으로 저장하고 <br>
> 해당 Json을 읽는 라이브러리이다. 고퀄리티 홈페이지에 사용될 요소들이 많다.<br>
> [LottieFiles](https://lottiefiles.com/) 에서 사람들이 올린 것들을 사거나 무료로 공개한걸 볼수있다.[예시](https://lottiefiles.com/101573-search-file)<br>
> 많은사이트에서 쓰이고 있다.<br>
> github : [https://github.com/airbnb/lottie](https://github.com/airbnb/lottie)

## TypeIt.js

> [https://www.typeitjs.com/](https://www.typeitjs.com/)
> 
> 타이핑하듯 입력동작보여주는 라이브러리<br>
> 해당라이브러리는 상용으로 쓰기에는 US. 44달러 약 5만원정도 지불을해야한다. <br>
> 하나하나 입력해나가는 모션이 너무 이쁘고 그럴싸해보인다. <br>
> 문서도 정리가 잘되어있어서 영어를 잘모르더라도 보기편하다 딱쉽다 쓰기 <br>
> 또한 미리 키보드타이핑한것을 자동으로 함수까지 만들어준다. <br>

```js
new TypeIt("#element", { 
    lifeLike: false, 
    speed: 0 
})
	.move(1, {speed: 0})
	.delete(1)
	.type("a")
	.pause(680)
	.type("m")
	.pause(121)
	.type("s")
	.pause(112)
	.type("o")
	.pause(254)
	.type("m")
	.pause(72)
	.type("a")
	.pause(97)
	.type("d")
	.go();
```
>[https://www.typeitjs.com/build-your-own](https://www.typeitjs.com/build-your-own) <br>
>여기서 내가 입력한 레코딩을 그대로보여준다.

## scroll-out.js

> [https://scroll-out.github.io/](https://scroll-out.github.io/)
>
> 스크롤바 혹은 마우스휠로 스크롤이동시 보여줄 효과를 꾸며준다.<br>
> Codepen에서 [scrollout](https://codepen.io/search/pens?q=scrollout) 이라 검색하니 딱 뭔지 알겠다<br>
> 스크롤 내리면서이미지나 텍스트가 사라지거나 보여지는 효과들 <br>
> github : [https://github.com/scroll-out/scroll-out](https://github.com/scroll-out/scroll-out)


#



1️⃣2️⃣3️⃣4️⃣5️⃣6️⃣7️⃣8️⃣9️⃣🔟




**Note:** `만들고나니 내것이 아니었다.` 