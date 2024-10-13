# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹과 모바일 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines)과 모바일 접근성 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 모바일 앱 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 모바일 앱을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 앱의 사용성을 크게 향상시킵니다.    

### 자막, 수화 등의 제공
**관련 지침 : 영상이나 음성 콘텐츠에는 동등한 내용의 자막, 원고 또는 수화가 제공되어야 한다.**   
자막과 수화는 청각 장애인을 포함한 다양한 사용자들이 동영상, 강의, 프레젠테이션과 같은 멀티미디어 콘텐츠의 모든 정보를 얻을 수 있도록 하는 필수적인 접근성 요소입니다. 자막은 청각 장애인에게 음성 정보를 텍스트로 전달하고, 수화는 청각 장애인에게 시각적 의사소통 수단을 제공합니다.   
[WCAG 2.2 Quick Reference - Non-text Content](https://www.w3.org/WAI/WCAG22/quickref/#non-text-content){: target="_blank"}
[W3C - 자막 및 수화 관련 지침](https://www.w3.org/WAI/media/av/){: target="_blank"}
[Microsoft Support - 비디오에 대한 선택 자막 만들기](https://support.microsoft.com/ko-kr/office/%EB%B9%84%EB%94%94%EC%98%A4%EC%97%90-%EB%8C%80%ED%95%9C-%EC%84%A0%ED%83%9D-%EC%9E%90%EB%A7%89-%EB%A7%8C%EB%93%A4%EA%B8%B0-b1cfb30f-5b00-4435-beeb-2a25e115024b){: target="_blank"}
[WebVTT란?](https://support.wecandeo.com/docs/videopack-guide-caption-convert#webvtt%EB%9E%80){: target="_blank"}

1. 영상이나 음성 콘텐츠 내 제공되는 모든 음성정보는 동등한 내용의 자막, 원고, 수화 중 적어도 하나 이상을 제공해야 한다.     
2. 영상이나 음성 콘텐츠에서 화면에 문자정보가 의미를 가지고 있는 경우 이를 설명하는 별도의 음성 콘텐츠나 원고를 제공해야 한다.    
3. 자막, 원고 또는 수화는 재생되고 있는 영상이나 음성 콘텐츠와 동기화하여 제공한다. 단, 실시간으로 제공되는 영상이나 음성 콘텐츠의 경우는 실시간 자막 또는 수화로 제공할 수 있다.    
4. 음성이나 문자정보 없이 제공되는 영상이나 음성 콘텐츠는 이를 설명하는 화면해설을 제공하는 것이 바람직하다.    

**키워드**   
#모바일 앱 접근성, #모바일 앱 접근성 콘텐츠 제작 기법, #WCAG2.2, #자막, #수화, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #VoiceOver, #TalkBack, #네이티브 #하이브리드, 청각 장애인, 고령자, 언어 비숙련자

#### 1. 필요성        
- **소리를 듣지 못하는 사용자** : 멀티미디어 콘텐츠의 음성 정보(내레이션 등)를 인식할 수 없기 때문에 이와 동등한 대체 콘텐츠(자막, 대본 또는 수화 등)를 함께 제공하지 않으면 멀티미디어 콘텐츠에서 정보를 인식할 수 없어서 멀티미디어 콘텐츠의 음성 정보의 문맥과 동등한 수준의 자막, 대본 및 수화를 함께 제공해야 합니다.
- **영상을 보지 못하는 사용자** : 멀티미디어 콘텐츠의 영상 정보(텍스트 등)를 인식할 수 없기 때문에 이와 동등한 대체 (콘텐츠 원고 또는 내레이션 등)를 함께 제공하지 않으면 멀티미디어 콘텐츠에서 정보를 인식할 수 없다. 그러므로 멀티미디어 콘텐츠의 영상 정보의 문맥과 동등한 수준의 대체 콘텐츠 (콘텐츠 원고 또는 내레이션 등)를 함께 제공해야 합니다.
- **소리를 들을 수 없는 환경** : 해당 언어를 모국어로 사용하지 않은 비장애인에게도 도움을 줄 수 있으며 자막 및 대본은 동영상 검색 시에도 도움을 줄 수 있습니다. 

#### 2. 대상       
- **청각 장애인**: 음성 콘텐츠를 접근할 수 없는 사용자.   
- **난청 사용자**: 음성 콘텐츠를 충분히 이해하기 어려운 사용자.   
- **언어 비숙련자**: 자막을 통해 콘텐츠를 더 쉽게 이해하는 사용자.   
- **고령자**: 청력 저하로 인해 음성 콘텐츠 접근에 어려움을 겪는 사용자.     
- **다양한 언어를 사용하는 사용자**: 자막은 여러 언어로 제공될 수 있어 언어 장벽을 극복할 수 있습니다.     

#### 3. 체크리스트       
**자막 관련 항목**    
- **대사와 일치하는가**: 자막이 음성 대사와 정확하게 일치하는지 확인합니다.    
- **동작, 소리 설명**: 대사 외에도 중요한 배경 소리(문 두드리는 소리, 음악 등)나 동작에 대한 설명을 포함하는지 확인합니다.    
- **적절한 동기화**: 자막이 화면에 표시되는 시간이 음성 콘텐츠와 일치하는지 확인합니다.    
- 자막이 음성 콘텐츠와 정확하게 일치하는가?    
- 자막에 중요한 배경 소리나 소리 효과가 포함되어 있는가?    
- 자막이 음성과 동기화되어 적절한 타이밍에 표시되는가?    
- 자막의 폰트 크기와 색상 대비가 적절한가?    

**수화 관련 항목**    
- **화면에서 잘 보이는 위치 제공**: 수화 영상이 화면에서 가려지지 않고 명확하게 표시되는지 확인합니다.    
- **콘텐츠 전체 제공 여부**: 수화가 콘텐츠 전체를 충분히 설명하는지 확인합니다.     
- 수화 영상이 화면에서 명확하게 보이는가?   
- 수화가 음성 콘텐츠와 동기화되어 있는가?   
- 수화가 중요한 정보를 빠뜨리지 않고 제공하는가?     


#### 4. 기기별 테스트 방법      
**iOS**     
- **VoiceOver 활성화**: 설정 > 접근성 > VoiceOver를 활성화하여 자막 및 수화가 올바르게 제공되는지 확인.   
- **자막 및 SDH 설정**: 설정 > 접근성 > 자막 및 SDH 설정을 통해 자막이 제대로 활성화되는지 테스트.   
- **비디오 재생**: 비디오 재생 시 자막이 적절하게 표시되고 동기화되는지 확인.    
- [iPhone 사용 설명서 - VoiceOver](https://help.apple.com/iphone/11/?lang=ko#/iph3e2e415f){: target="_blank"}
   
**Android**   
- **TalkBack 활성화:** 설정 > 접근성 > TalkBack을 활성화한 후, 콘텐츠에서 자막이 정확하게 동기화되고 있는지 확인.    
- **Accessibility Scanner 사용**: Google Play의 'Accessibility Scanner' 앱을 사용하여 자막과 수화가 적절히 제공되는지 자동으로 테스트.   
- **자막 활성화**: 설정 > 접근성 > 자막 옵션을 사용해 자막이 정상적으로 작동하는지 확인.      
- [Android 접근성 고객센터 - TalkBack 및 Android](https://support.google.com/accessibility/android/topic/10601571?hl=ko&ref_topic=3529932&sjid=14261166623289476037-AP){: target="_blank"}

#### 5. QA 지표       
- **자막 정확성**: 자막이 음성과 일치하는지 확인하는 비율.   
- **수화 정확성**: 수화가 음성 콘텐츠와 일치하는지 확인하는 비율.   
- **동기화 정확성**: 자막과 수화가 음성과 적절하게 동기화되어 있는지 여부.   
- **사용자 피드백**: 실제 사용자 테스트 후 자막 및 수화 기능에 대한 만족도를 피드백으로 수집.   


#### 6. 개발방법     

**네이티브 (iOS) - 자막 적용**  

```sh
let videoPlayer = AVPlayer(url: videoURL)
let captions = AVMediaSelectionGroup()
videoPlayer.add(captions)
```   

**네이티브 (Android) - 자막 파일과 함께 비디오 재생**    

```sh
videoView.addSubtitleSource(new FileInputStream(subtitleFile), MediaFormat.createSubtitleFormat("text/vtt", Locale.getDefault().getLanguage()));
```   

**하이브리드(html)**    

```sh
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track kind="captions" src="subtitles_en.vtt" srclang="en" label="English">
</video>
```

**하이브리드(Vue)**    

```sh
<template>
  <video controls>
    <source src="video.mp4" type="video/mp4" />
    <track kind="captions" src="subtitles_en.vtt" srclang="en" label="English" />
  </video>
</template>
```

**하이브리드(React)**    

```sh
function VideoComponent() {
  return (
    <video controls>
      <source src="video.mp4" type="video/mp4" />
      <track kind="captions" src="subtitles_en.vtt" srclang="en" label="English" />
    </video>
  );
}
```



#### 7. 점검 기준     
멀티미디어 콘텐츠를 동등하게 인식할 수 있도록 자막이나 원고, 수화 등 대체정보를 제공한다.     

**자막 점검 기준**    
- 자막이 정확하게 음성과 일치하는가?    
- 중요한 배경 소리나 음악 설명이 포함되어 있는가?    
- 자막의 폰트 크기와 색상 대비가 적절한가?       

**수화 점검 기준**    
- 수화가 모든 중요한 음성 정보를 전달하는가?    
- 수화가 명확하게 표시되고 콘텐츠에 방해가 되지 않는가?       
   
**오류유형**     
- 음성정보에 대체수단을 제공하지 않는 경우    
- 음성정보 전체가 아닌 일부정보나 요약정보만을 제공하는 경우    
- 음성 정보 없는 동영상에 대체수단을 제공하지 않는 경우      
   
**주의사항**     
- 파일로 제공되는 영상,음성 콘텐츠도 평가대상에 포함.     
- 유의미한 음성정보 없이 화면에 텍스트로만 정보를 제공하거나, 영상스케치 등의 동영상의 경우 화면에 제공되는 정보를 화면밖에 시각장애인이 확인할 수 있도록 대체정보를 제공하여야 함(스케치의 경우 대략적인 요약정보 제공 인정).    
- 동영상과 대체정보를 한 화면에서 볼 수 있도록 구현 권장     

#### 8. 점검 방법     
멀티미디어 콘텐츠 등에 음성정보를 대체할 수 있는 수단(자막, 원고, 수화 등)을 제공하고 있는 지, 유의미한 음성정보 없이 화면으로만 정보를 제공하는 경우 화면정보를 인지할 수 있도록 대체정보를 제공하는 지를 점검한다.    

- 동영상 실행 후 Caption 기능이 있는지 확인한다.   
- 콘텐츠 내 원고, 수화 기능을 제공하는지 확인한다.   

 

**주의사항**    
- 개발방법에 따라 연관된 타 UI 객체에 대체텍스트를 적용하고 있는경우가 있다. 이런경우엔 오류항목으로 볼 수 없다.     
- UIAutoMatorViewe 를 활용한 대체텍스트 확인은 다른 점검기법과 병행되어 사용하는 것이 바람직하다.     
    

#### 9. 준수 사례       

**사례1**   
음성정보에 대체수단(자막)을 제공한 경우    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_ex_caption_do01.png" alt="">
  <figcaption>출처 : AOA11Y</figcaption>
</figure>

**사례2**   
음성정보에 대체수단(수화)를 제공한 경우    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_ex_caption_do02.png" alt="">
  <figcaption>출처 : 디지털 접근성 컨퍼런스 2024</figcaption>
</figure>
  

**사례3**   
문자정보에 대체수단(원고)를 제공한 경우    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_ex_caption_do03.png" alt="">
  <figcaption>출처 : 라이나생명</figcaption>
</figure>

**사례4**   
비디오 관리자의 자막 설정에서 적절한 내용으로 자막을 수정한 경우    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_ex_caption_do04.png" alt="">
  <figcaption>출처 : https://brunch.co.kr/@snclab/23</figcaption>
</figure>
유튜브 크리에이터 스튜디오의 '동영상 관리자 메뉴'에서 자막을 수정하거나 삽입하고 싶은 동영상을 선택하고 '자막' 탭을 살펴보면 새 자막을 추가하거나 이미 삽입된 자막을 수정할 수 있습니다. 


#### 10. 미준수 사례       

**사례1**   
이미지 요소가 제공하는 정보와 동일한 정보가 음성으로 출력되지 않는 경우    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_ex_caption_donot01.png" alt="">
  <figcaption>출처 : 모바일애플리케이션콘텐츠접근성지침2.0</figcaption>
</figure>

**사례2**   
음성정보 전체가 아닌 일부정보나 요약정보만을 제공하는 경우    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_ex_caption_donot02.png" alt="">
  <figcaption>출처 : 모바일애플리케이션콘텐츠접근성지침2.0</figcaption>
</figure>



#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/vtKmpY28IRs?si=Am4mOxcWA-kW0p1j" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 모바일 앱 접근성 (2. 자막, 수어 등의 제공)](https://youtu.be/vtKmpY28IRs?si=xOZjf7NVF1ctJUBd){: target="_blank"}    
   
---
<details>
<summary><strong style="font-size:20px;cursor:pointer;">접근성 테스트 도구 활용 점검방법</strong></summary>
<div markdown="1">

**Lighthouse**   
Lighthouse is an open-source, automated tool for improving the quality of web pages.    
Lighthouse는 구글에서 제공하는 웹 페이지 품질 개선을 위한 오픈 소스로 자동화 도구입니다. Lighthouse는 사이트의 성능, 접근성, SEO 등에 대한 전반적인 진단을 해줍니다.    
상세 설명 [Lighthouse Overview 공식 문서 참조](https://developer.chrome.com/docs/lighthouse/overview/){: target="_blank"}  


- **참고** 
  - Lighthouse 모바일의 경우 네트워크 속도를 최대 4배정도 느리게 측정하기 때문에 모바일 Performance가 비교적 낮게 나옵니다.    
  - Metric 별로 어떤 성능 점수가 나는지 Lighthouse 계산기를 통해서 자세히 확인할 수 있습니다.    
- **카테고리가 측정하는 내용**    
  - **Performance** : 웹 페이지의 로딩 속도 등 실제 성능을 측정. 성능의 측정항목은 6가지 Metric으로 정의되며, 각 Metric들은 페이지가 로드되는 속도를 다양한 측면에서 측정합니다.  자세한 설명은 [Lighthouse Performance Audits 문서](https://developer.chrome.com/docs/lighthouse/performance/){: target="_blank"}에서 확인.     
  - **Best practices** : Best practices를 따라 개발되었는지 확인   
  - **Accessibility** : 접근성 확인. 폰트 사이즈, 메뉴간 간격 등을 측정   
  - **Progressive Web App (PWA)** : 웹과 네이티브 앱의 기능 모두의 이점을 가지도록 만들어진 서비스인지 체크   
  - **SEO** : Search Engine Optimization의 약자로 검색 엔진 수집 최적화 측정    
- **사용법**    
    1. Google Chrome에서 웹 페이지를 엽니다.    
    2. DevTools (F12)를 열고 'Lighthouse' 탭을 선택합니다. (단축키 맥:Cmd⌘+Option⌥+I / 윈도우:Ctrl+Shift+I)     
    3. 'Accessibility' 항목을 선택하고 우측 상단의 'Analyze page load'를 클릭하여 보고서를 생성합니다.    
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool01-01.png" alt="">
      <figcaption>Lighthouse를 활용한 검사</figcaption>
    </figure>
    4. Lighthouse는 접근성 점수와 함께 개선이 필요한 부분을 제시합니다.    
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool01-02.png" alt="">
      <figcaption>Lighthouse를 활용한 검사</figcaption>
    </figure>
   
**WAVE**    
WAVE는 WebAIM에서 만든 확장 프로그램으로 현재 화면의 각 요소가 접근성을 준수하는지 평가합니다. 각 요소가 위반한 내용에 대한 이유와 해결 방법을 제시하여 접근성을 준수하는 개발을 쉽게 할 수 있도록 돕습니다.    

- **사용법**        
    1. Chrome 브라우저에서 WAVE 확장 프로그램을 설치합니다.   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool02-01.png" alt="">
      <figcaption>WAVE를 활용한 검사</figcaption>
    </figure>
    2. 페이지를 열고 WAVE 확장 프로그램을 실행하여 분석을 시작합니다.   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool02-02.png" alt="">
      <figcaption>WAVE를 활용한 검사</figcaption>
    </figure>
    3. WAVE 페이지에서 발견된 접근성 문제를 제시합니다.   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool02-03.png" alt="">
      <figcaption>WAVE를 활용한 검사</figcaption>
    </figure>
   
**Accessibility Scanner (Android)**    
Accessibility Scanner는 Android 기기에서 접근성 문제를 탐지하는 Google Play의 앱입니다.    

- **사용법**    
    1. Android 기기에 Accessibility Scanner 앱을 설치합니다.   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool05-01.png" alt="">
      <figcaption>Accessibility Tree 활용한 검사</figcaption>
    </figure>
    2. 앱을 실행하고 분석하려는 화면에서 스캔을 시작합니다.   
    3. 앱은 화면에서 발견된 접근성 문제를 보고하고 개선 방법을 제시합니다.   
 
   
**접근성 트리 뷰(Accessibility Tree)**    
스크린 리더와 같은 보조 기술은 크로미움의 접근성 API를 사용해 웹콘텐츠와 상호 작용합니다. 접근성 API의 기본 모델은 접근성 트리입니다. 접근성 객체의 트리를 통해 보조 기술은 각 속성과 실제 속성값을 탐색하고 필요한 작업을 수행할 수 있습니다. 웹 개발자는 주로 HTML에서 ARIA 속성과 같은 DOM 속성값을 통해 접근성 트리를 만들고 이를 다룹니다.    
크롬 개발자 도구에서는 개발자에게 콘텐츠가 보조 기술에 어떤 식으로 전달되는지 이해할 수 있게 접근성 창을 제공하고 있습니다. DOM 트리 뷰어에서 노드를 선택하면 해당하는 접근성 노드의 속성 정보가 상위 노드, 직계 자식 노드와 함께 창에 표시됩니다.    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_tool05-01.png" alt="">
    <figcaption>Accessibility Tree 활용한 검사</figcaption>
</figure>

- **사용법**        
    1. 개발자 도구에서 Elements 항목을 선택하고 오른쪽 창에서 Accessibility를 선택하면 "Enable full-page accessibility tree" 항목을 체크   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool05-02.png" alt="">
      <figcaption>Accessibility Tree 활용한 검사</figcaption>
    </figure>
    2. 해당 노드 선택 후 검사   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool05-03.png" alt="">
      <figcaption>Accessibility Tree 활용한 검사</figcaption>
    </figure>    
     
**Accessibility Scanner (Android)**    
Accessibility Scanner는 Android 기기에서 접근성 문제를 탐지하는 Google Play의 앱입니다.    

- **사용법**    
    1. Android 기기에 Accessibility Scanner 앱을 설치합니다.   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool03-01.png" alt="">
      <figcaption>Accessibility Tree 활용한 검사</figcaption>
    </figure>

    2. 앱을 실행하고 분석하려는 화면에서 스캔을 시작합니다.   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool03-02.png" alt="">
      <figcaption>Accessibility Tree 활용한 검사</figcaption>
    </figure>

    3. 앱은 화면에서 발견된 접근성 문제를 보고하고 개선 방법을 제시합니다.   
    <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool03-03.png" alt="">
      <img src="./../images/a11y-mobile/img_a11yMobile_tool03-04.png" alt="">
      <figcaption>Accessibility Tree 활용한 검사</figcaption>
    </figure>
 
   
**VSCode 확장 접근성 검사(axe Accessibility Linter)**    
VSCode 사용 시 별도 확장 설치 후 소스 코드에서 잘못 작성된 부분을 사전에 감지하여 수정할 수 있습니다.    
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_tool04-01.png" alt="">
  <figcaption>VS Code extensions axe Accessibility Linter</figcaption>
</figure>
 
   
**eslint-plugin-jsx-a11y(ReactJS + ESLint)**    
접근성 오류 부분이 있는지 분석해 주는 플러그인이며 서비스 개발 환경이 React라면 실시간으로 JSX 요소에 대한 접근성 규칙을 확인하고 준수할 수 있도록 돕는 패키지를 설치해 개발할 수 있습니다. 기본적으로 추천되는 규칙 외에 예외로 사용하고 싶은 부분이 있다면 같이 서비스를 개발하는 개발자들과 협의하면서 lint 규칙을 만들어가다 보면 접근성을 준수하는 서비스 개발에 도움이 될 것입니다.    
[규칙 상세 설명 : jsx-eslint/eslint-plugin-jsx-a11y](https://github.com/jsx-eslint/eslint-plugin-jsx-a11y){: target="_blank"}  

**사용법**   
eslint를 전역 설치했다면, eslint-plugin-jsx-a11y 플러그인도 전역으로 설치.  
```sh
npm install eslint-plugin-jsx-a11y
// 또는
yarn add eslint-plugin-jsx-a11y
``` 
.eslintrc.json 파일에 다음과 같이 추가한다.   
```sh
{
  "extends": "plugin:jsx-a11y/recommended",
  "plugins": "jsx-a11y",
  "rules": {
    "jsx-a11y/aria-role": [
      "error",
      {
        "allowedInvalidRoles": ["text"],
        "ignoreNonDOM": true
      }
    ]
  }
}
```
   
**iOS : Accessibility Inspector**    
iOS 앱 개발도구인 xcode에는 Accessibility Inspector 툴을 통해 접근성을 수동 검사할 수 있습니다.    
   
- Xcode에서 Accessibility Inspector 툴을 실행합니다. (Xcode > Open Developer Tool > Accessibility Inspector)   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/ef764147-3952-46ec-948e-9c54e319af16_xcode_tool_accessibility_inspector.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- 테스트할 장치를 선택합니다. 저는 진단하고 싶은 앱을 실행 후 아이폰을 노트북에 연결하여 장치 선택을 했어요. 개발 중인 앱을 Simulator로 빌드 하셨다면 Simulator를 선택하여 진단하실 수 있습니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/1590bb9b-98eb-4302-8946-9a5dcc76b522_%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%8E%E1%85%B5%E1%84%89%E1%85%A5%E1%86%AB%E1%84%90%E1%85%A2%E1%86%A8.jpg" alt="">
    <img src="https://nuli.navercorp.com/upload/2023/48870f35-9a4e-4d8c-844a-fad3a870c76a_%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%8E%E1%85%B5%E1%84%89%E1%85%A5%E1%86%AB%E1%84%90%E1%85%A2%E1%86%A8_%E1%84%89%E1%85%A6%E1%84%87%E1%85%AE.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- Accessibility Inspector 툴 오른쪽 상단에서 audit 버튼을 선택합니다. Run Audit 버튼을 선택합니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/ac06562c-681f-4abf-8900-b8ebef40dd60_audit%E1%84%89%E1%85%B5%E1%86%AF%E1%84%92%E1%85%A2%E1%86%BC.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- 결과 이슈 목록을 선택하거나 눈 버튼을 선택하시면 해당 항목을 보여줍니다. 장치를 보시면 노란색으로 표시되고, 물음표 버튼를 선택하시면 해당 이슈를 해결할 수 있는 방법을 알려줍니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/d1d742a4-0487-449b-acac-fa494262bad5_audit%E1%84%80%E1%85%A7%E1%86%AF%E1%84%80%E1%85%AA.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- 물음표 버튼를 선택하시면 해당 이슈를 해결할 수 있는 방법을 알려줍니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/6543e5af-479a-4d55-8431-774e49278f26_%E1%84%8B%E1%85%B5%E1%84%89%E1%85%B2%E1%84%92%E1%85%A2%E1%84%80%E1%85%A7%E1%86%AF%E1%84%87%E1%85%A1%E1%86%BC%E1%84%87%E1%85%A5%E1%86%B8.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- 목록에서 주의 깊게 봐야 할 이슈는 바로 description에 대한 이슈입니다. 대체 텍스트 이슈는 접근성 사용자에게 매우 크리티컬한 이슈이면서 해결 방법이 매우 수월한 이슈입니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/3de8b5aa-6124-45e3-8048-b37edbad65c9_%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5%E1%84%83%E1%85%A2%E1%84%8E%E1%85%A6%E1%84%90%E1%85%A6%E1%86%A8%E1%84%89%E1%85%B3%E1%84%90%E1%85%B3%E1%84%8B%E1%85%A9%E1%84%85%E1%85%B2.jpg" alt="">
    <img src="https://nuli.navercorp.com/upload/2023/608699d9-c72b-45b0-b126-8b60c029773b_%E1%84%87%E1%85%A5%E1%84%90%E1%85%B3%E1%86%AB%E1%84%83%E1%85%A2%E1%84%8E%E1%85%A6%E1%84%90%E1%85%A6%E1%86%A8%E1%84%89%E1%85%B3%E1%84%90%E1%85%B3%E1%84%8B%E1%85%A9%E1%84%85%E1%85%B2.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- Xcode의 Identity Inspector 탭의 Accessibility 패널에 **대체 텍스트**를 넣어주세요.   
- 대체 텍스트 외에도 명도대비, 작은 터치영역등 다양한 접근성 이슈를 체크해주고 있습니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/34d0933e-dab9-4cbd-8aa6-5b563025935c_accessibilityLabel.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  

- **Inspection**   
  각 요소별 접근성 항목을 확인할 수 있고, iOS 스크린리더인 VoiceOver 음성으로 들어볼 수 있습니다.    
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/90a6c179-4017-46f9-b47e-2bfe9b6f8231_inspection.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  

  1. 스피커      
    현재 초점이 위치한 요소의 정보를 VoiceOver 음성으로 들려줍니다.   
  2. 이전 요소 탐색   
    현재 초점이 위치한 곳에서 이전 요소의 정보를 VoiceOver 음성으로 들려줍니다.   
  3. 자동 탐색   
    현재 초점이 위치한 곳에서 모든 요소를 자동으로 탐색하며 요소의 정보를 VoiceOver 음성으로 들려줍니다.   
  4. 다음 요소 탐색    
    현재 초점이 위치한 곳에서 다음 요소의 정보를 VoiceOver 음성으로 들려줍니다.   
  5. 직접 탐색   
    마우스로 요소를 직접 선택하여 탐색합니다.   
  6. 현재 초점이 위치한 요소의 접근성 항목을 나타냅니다.   
    항목은 Label(대체 텍스트), Value(값), Traits(유형 정보), Identifier(식별자), Hint(힌트 정보), User Input Labels(사용자 입력 텍스트 정보)입니다.      

**Android : Lint**    
Android 앱 개발도구인 Android Studio 의 Lint를 통해 개발과정에서 접근성을 수동 검사할 수 있습니다.   
- Analyze > Inspect Code를 실행합니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/f596269f-ffcd-49af-bc69-42e725bc226a_analyze_inspect_code.png" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- Android Studio 4.1.1. 버전을 사용. Android Studio Electric Eel 2022.1.1 Patch 2버전이면 Code 메뉴에 inspect Code가 보임.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/f91dbb78-00ab-4fb8-bf01-bc92815001dd_code_inspect_code.png" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- Inspection profile에서 더보기 버튼을 실행합니다.   
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/ef698256-3642-4e80-84a5-014957df07b4_insection_profile_%E1%84%83%E1%85%A5%E1%84%87%E1%85%A9%E1%84%80%E1%85%B5.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- Inspections 창에서 Lint > Accessibility 항목 중 “Image without contentDescription” 항목과 "Missing accessibility label"을 체크합니다.   
- Android에서 Accessibility 항목 중 주의 깊게 봐야 할 이슈는 바로 이미지 대체 텍스트와 입력 서식 라벨에 대한 이슈입니다.    
- Severity를 Error로 체크해 주세요. Error 이슈를 해결하기 전까지는 빌드 성공을 할 수 없음.     
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/30028858-e6ae-4acb-a8c2-0028397dd24e_lint_accessibility.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- 진단 범위도 설정. 모든 범위 In All Sccopes     
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/b2fc68a3-81c2-42f3-9861-3e3d7193be0f_lint_accessibility_%E1%84%87%E1%85%A5%E1%86%B7%E1%84%8B%E1%85%B1.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- OK를 누르고 코드를 확인. contentDescription 이 없는 ImageView 또는 ImageButton에 빨간색으로 표시된 것을 확인할 수가 있습니다. labelFor 또는 hint가 없는 EditText 역시 빨간색으로 표시된 것을 볼 수 있습니다.        
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/eca0a298-7f02-42a0-be07-bb6d75cff10b_imagebutton_%E1%84%8B%E1%85%A9%E1%84%85%E1%85%B2.jpg" alt="">
    <img src="https://nuli.navercorp.com/upload/2023/86d98d79-68a5-42d9-9d60-db57025d560a_edittext_%E1%84%8B%E1%85%A9%E1%84%85%E1%85%B2.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- 이슈 해결 - ImageView 클래스에 contentDescription을 코드에서 추가. 빨간색으로 표시되었던 코드가 노란색 코드로 변경.        
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/940b3ba0-192e-4459-8cbb-8ce944d3cea3_imagebutton_%E1%84%92%E1%85%A2%E1%84%80%E1%85%A7%E1%86%AF.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  
- 이슈 해결 : EditText 역시 hint 코드를 추가. 빨간색으로 표시되었던 코드가 노란색 코드로 변경.        
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="https://nuli.navercorp.com/upload/2023/24ba5208-1b5f-4b52-8df6-8d6fffd189f0_edittext_%E1%84%92%E1%85%A2%E1%84%80%E1%85%A7%E1%86%AF.jpg" alt="">
    <figcaption>출처 : NULI</figcaption>
  </figure>  

</div>
</details>




 
#### 결론     
**접근성은 시작은 있지만 끝이 없는 작업입니다.**    
오류 항목을 정기적으로 점검하여 접근성 개선을 한다면 점차 검사를 할 항목이 줄어들게 될 것입니다. 모두가 차별 없이 서비스를 이용할 수 있도록 접근성 유지를 위한 모두의 노력이 필요합니다. 무엇보다 접근성 작업은 서비스를 제공한다면 **선택이 아닌 필수**로 지켜야하는 항목임을 잊지 말아야 합니다.     

**접근성 작업 시 점검 필수사항**    
- 접근성 가이드(WCAG, KWCAG, WAI-ARIA) 내용 숙지    
- 접근성 체크리스트 작성    
- 접근성 자동 및 수동 검사(스크린리더) 진행       
- 접근성 검사 툴(Lighthouse Accessibility 등) 활용 오류 항목 개선 및 내용 정리     
- 접근성 사용자 테스트    
- 접근성 정기적인 모니터링    




### 참조    
- [W3C Mobile Accessibility at W3C](https://www.w3.org/WAI/standards-guidelines/mobile/){: target="_blank"}    
- [W3C Mobile Accessibility: How WCAG 2.0 and Other W3C/WAI Guidelines Apply to Mobile](https://www.w3.org/TR/mobile-accessibility-mapping/){: target="_blank"}    
- [W3C First Public Working Draft](https://www.w3.org/news/2015/first-public-working-draft-performance-timeline-level-2/){: target="_blank"}   
- [W3C User Agent Accessibility Guidelines (UAAG) 2.0](https://www.w3.org/TR/UAAG20/){: target="_blank"}    
- [W3C Mobile Accessibility Examples from UAAG 2.0 Reference](https://www.w3.org/TR/IMPLEMENTING-UAAG20/mobile.html){: target="_blank"}    
- [MDN Mobile accessibility checklist](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Mobile_accessibility_checklist){: target="_blank"}    
- [보건복지부 블로그](https://blog.naver.com/prologue/PrologueList.naver?blogId=mohw2016){: target="_blank"}     
- [행정안전부 - 전자정부 웹사이트 UI UX 가이드라인](https://www.mois.go.kr/frt/bbs/type001/commonSelectBoardArticle.do?bbsId=BBSMSTR_000000000045&nttId=69451){: target="_blank"}     
- [널리 알리는 기술 소식 커뮤니티](https://nuli.navercorp.com/community/article){: target="_blank"}     
