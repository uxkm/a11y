# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹과 모바일 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines)과 모바일 접근성 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 모바일 앱 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 모바일 앱을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 앱의 사용성을 크게 향상시킵니다.    
   
   
### 명도 대비   
**관련 지침 : 화면에 표시되는 모든 사용자 인터페이스 컴포넌트와 텍스트는 전경색과 배경색이 구분될 수 있도록 제공되어야 한다.**   
명도 대비는 텍스트와 배경 또는 인터페이스 컴포넌트 간의 색상 차이를 의미하며, 이를 통해 콘텐츠가 보다 쉽게 인식될 수 있도록 해야 합니다. WCAG 가이드라인에서는 명도 대비 비율을 최소한 4.5:1 이상 유지할 것을 권장하며, 큰 텍스트(18pt 이상) 또는 굵은 텍스트(14pt 이상)는 3:1의 비율을 유지하도록 규정하고 있습니다. 명도 대비가 부족하면 저시력 사용자나 시각 장애인은 콘텐츠를 인식하는 데 어려움을 겪게 됩니다.   
[WCAG 2.2 Quick Reference - Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/quickref/#contrast-minimum){: target="_blank"}

예시)    
- **잘못된 예**: 연한 회색 텍스트가 흰색 배경에 표시되어 텍스트가 구분되지 않는 경우.    
- **올바른 예**: 진한 회색 텍스트가 흰색 배경에 표시되어 명확히 구분되는 경우.     

<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast-minimum.png" alt="">
  <figcaption>WCAG 명도 대비 권장사항</figcaption>
</figure>   
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast-minimum-1.png" alt="">
  <figcaption>텍스트 크기와 무게 명도 대비 상세</figcaption>
</figure>   

**키워드**   
#모바일 앱 접근성, #모바일 앱 접근성 콘텐츠 제작 기법, #WCAG2.2, #명도 대비, #저시력 사용자, #색상 대비, #사용자 인터페이스, #텍스트 가독성

#### 1. 필요성        
명도 대비는 저시력 사용자, 고령자, 시각 장애인이 앱을 사용할 때 중요한 정보를 놓치지 않도록 보장하는 핵심 요소입니다. 명확한 대비가 없으면 텍스트와 UI 컴포넌트가 배경과 혼동될 수 있어 사용자의 접근성이 떨어집니다. 명도 대비가 유지되면 더 많은 사용자들이 콘텐츠를 쉽게 이해하고 접근할 수 있습니다.     


#### 2. 대상       
- **저시력 사용자**: 명도 대비가 낮은 텍스트와 UI 컴포넌트를 인식하는 데 어려움을 겪는 사용자.   
- **고령자**: 시력 저하로 인해 명도 대비가 중요한 사용자.   
- **시각 장애인**: 색상 인식이 어렵거나 제한적인 사용자.   
- **비장애 사용자**: 햇빛이나 어두운 환경에서 명도 대비가 적절치 않을 경우 콘텐츠를 인식하는 데 어려움을 겪는 사용자.      

#### 3. 체크리스트       
- **명도 대비 비율 확인**: 텍스트와 배경, UI 요소의 대비가 WCAG 기준(최소 4.5:1)을 충족하는가?   
- **폰트 크기와 대비 비율**: 큰 텍스트나 굵은 텍스트의 경우 최소 3:1의 대비 비율을 유지하는가?   
- **상태 변화 반영**: 버튼, 링크, 체크박스 등 UI 요소의 활성화 상태가 색상 변화 외에도 명확하게 표시되고 있는가?   
- **배경 이미지 사용 시 대비**: 배경 이미지 위에 텍스트를 배치할 경우, 텍스트가 이미지와 충분한 대비를 이루고 있는가?     


#### 4. 기기별 테스트 방법      
**iOS**     
- **명도 대비 테스트**: iOS 설정에서 색상 필터 및 스마트 반전 기능을 사용하여 명도 대비가 유지되고 있는지 확인.    
- **VoiceOver 사용**: VoiceOver를 통해 텍스트 및 UI 요소가 명확하게 인식되는지 확인.   
- **iOS 개발자 도구**: Xcode의 Accessibility Inspector를 사용하여 명도 대비를 자동으로 분석하고, 기준에 맞는지 확인.   
- [iPhone 사용 설명서 - VoiceOver](https://help.apple.com/iphone/11/?lang=ko#/iph3e2e415f){: target="_blank"}
   
**Android**   
- **명도 대비 테스트**: Android 디바이스에서 '색상 반전'과 '고대비 텍스트' 설정을 활성화하여 앱의 명도 대비를 테스트.   
- **TalkBack 사용**: 텍스트와 UI 요소가 충분한 대비를 유지하여 사용자가 쉽게 인식할 수 있는지 확인.    
- **Accessibility Scanner 사용**: Google Play에서 제공하는 Accessibility Scanner 앱을 통해 명도 대비 문제를 자동으로 탐지.      
- [Android 접근성 고객센터 - TalkBack 및 Android](https://support.google.com/accessibility/android/topic/10601571?hl=ko&ref_topic=3529932&sjid=14261166623289476037-AP){: target="_blank"}
- [접근성 검사기 (Accessibility Scanner)](https://developer.android.com/codelabs/starting-android-accessibility?hl=ko#2){: target="_blank"}

#### 5. QA 지표       
- **대비 비율**: 텍스트와 배경, UI 요소 간의 대비 비율이 4.5:1(일반 텍스트) 또는 3:1(큰 텍스트)을 충족하는지 여부.    
- **대비 문제 비율**: 앱 내에서 명도 대비가 부족한 요소의 비율.   
- **사용자 피드백**: 저시력 사용자, 고령자 등을 대상으로 한 접근성 테스트 결과 및 피드백.      


#### 6. 개발방법     

**네이티브**     

- **iOS**    
  명도 대비 체크 및 조정   
  ```sh
  let label = UILabel()
  label.text = "Important Info"
  label.textColor = .darkGray  // 명도 대비 기준을 충족하도록 적절한 색상 사용
  label.backgroundColor = .white
  ```    

- **Android**        
  명도 대비 조정   
  ```sh
  <TextView
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:text="Important Info"
  android:textColor="#4A4A4A"  <!-- 진한 색상으로 명도 대비 기준 충족 -->
  android:background="#FFFFFF" />
  ```   

- **하이브리드(html)**     
  ```sh
  <div style="background-color: #FFFFFF; color: #333333;">
    Important Info
  </div>
  ```   
- **하이브리드(Vue)**     
  ```sh
  <template>
    <div :style="{ backgroundColor: '#FFFFFF', color: '#333333' }">
      Important Info
    </div>
  </template>
  ```
- **하이브리드(React)**    
  ```sh
  function ImportantInfo() {
    return (
      <div style={{ backgroundColor: '#FFFFFF', color: '#333333' }}>
        Important Info
      </div>
    );
  }
  ```
    

#### 7. 점검 기준     
- **명도 대비 비율**: 텍스트와 배경, UI 요소의 대비 비율이 최소 4.5:1(일반 텍스트) 또는 3:1(큰 텍스트) 이상을 유지하고 있는가?   
- **대비 문제 시각화**: 명도 대비 부족 시 텍스트나 UI 요소가 충분히 구별될 수 있는 대체 방법이 제공되고 있는가?   
- **대비 도구 사용 여부**: 앱 설계 시 명도 대비를 확인하기 위한 자동화된 도구를 사용하여 테스트가 이루어졌는가?     
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast.png" alt="">
  <figcaption>디자인 설계시 시맨틱 컬러 가이드 예시</figcaption>
</figure>   
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast-1.png" alt="">
  <figcaption>텍스트에 사용 가능한 색상 예시</figcaption>
</figure>   

#### 8. 점검 방법     
**iOS**         
- **Xcode Accessibility Inspector**: Xcode의 Accessibility Inspector를 사용해 앱의 명도 대비를 분석하고 자동으로 테스트.    

**Android**    
- **Accessibility Scanner**: Android의 Accessibility Scanner 앱을 사용하여 명도 대비 문제를 탐지.    

**하이브리드**     
- Colour Contrast Analyser (CCA) 프로그램을 사용하여 전경색과 배경색의 대비를 측정하여 점검.    
  [평가툴 다운로드 - Colour Contrast Analyser (CCA)](https://www.tpgi.com/color-contrast-checker/){: target="_blank"}
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast01.png" alt="">
    <figcaption>Colour Contrast Analyser (CCA)</figcaption>
  </figure>   
- Color Contrast Checker 사이트에서 체크
  배경색과 텍스트 색상을 지정하여 작은 텍스트와 큰 텍스트의 명암비를 파악할 수 있다. 값의 상태에 따라 Poor, Good, Super와 같은 상태 표시로 적절한 대비 상태를 직관적으로 인지할 수 있다.    
  [Color Contrast Checker](https://coolors.co/contrast-checker){: target="_blank"}
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast02.png" alt="">
    <figcaption>Color Contrast Checker 사이트</figcaption>
  </figure>   
- WCAG Color Contrast Checker 사이트에서 체크
  위 사이트는 WCAG(Web Content Accessibility Guidelines)의 AA, AAA 기준으로 Small text, Large text, UI components에 따라서 Pass 또는 Fail을 표시해준다.    
  [WCAG Color Contrast Checker](https://accessibleweb.com/color-contrast-checker/){: target="_blank"}
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast03.png" alt="">
    <figcaption>WCAG Color Contrast Checker 사이트</figcaption>
  </figure>   
- Leonardo 사이트에서 체크
  한 번에 여러 개의 색상을 체크하거나 색상 팔레트의 명암비를 체크하고 싶을 때 유용하다. 여러 가지 색상을 추가할 수 있으며 색상 대비를 조정하거나 밝기를 조정해서 팔레트를 구성할 수 있다. 우측에 표시되는 팔레트에는 배경 색상 대비 명암비가 자동으로 표시된다. 배경 색상을 변경하면 명암비도 자동으로 변경된다.    
  [Leonardo](https://leonardocolor.io/theme.html#){: target="_blank"}
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast04.png" alt="">
    <figcaption>Leonardo 사이트</figcaption>
  </figure>   
- WCAG Color contrast checker 확장 프로그램
  현재 운영 중인 사이트의 명암비를 체크할 수 있는 플러그인이다. 플러그인을 설치하고 실행하면 좌측 패널에서 현재 보고 있는 페이지의 각 콘텐츠 명암비를 체크해준다. 사이즈도 Small, Large로 자동으로 보여주며 요소를 클릭하면 해당 위치로 자동 스크롤 되어 확인할 수 있다.    
  [WCAG Color contrast checker](https://chromewebstore.google.com/detail/wcag-color-contrast-check/plnahcmalebffmaghcpcmpaciebdhgdf){: target="_blank"}
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast05.png" alt="">
    <figcaption>WCAG Color contrast checker 확장 프로그램</figcaption>
  </figure>   
- 피그마 플러그인
  해당 플러그인을 사용하면 피그마 내에서 선택한 디자인의 명암비를 바로 확인할 수 있다. 웹접근성 지침(AA, AAA)의 기준에 따라 표시도 해주며, 제안 색상을 선택하면 일괄적으로 별경할 수도 있다. 변경은 Pro 버전이라서 그냥 확인하는 용도로도 충분히 사용성이 좋은 것 같다.    
  [Figma : Stark - Contrast & Accessibility Checker](https://www.figma.com/community/plugin/732603254453395948/stark-contrast-accessibility-checker){: target="_blank"}
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast06.png" alt="">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast06-1.png" alt="">
    <img src="./../images/a11y-mobile/img_a11yMobile_contrast06-2.png" alt="">
    <figcaption>피그마 플러그인 Contrast & Accessibility Checker</figcaption>
  </figure>   



#### 9. 준수 사례       

**사례1**   
  
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast_ex_do01.png" alt="">
  <figcaption>텍스트 그림자 효과 적용</figcaption>
</figure>

**사례2**   
  
<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast_ex_do02.png" alt="">
  <figcaption>글자와 배경의 명도대비가 3:1 이상인 경우</figcaption>
</figure>

#### 10. 미준수 사례       

**사례1**    

<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast_ex_donot01.png" alt="">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast_ex_donot01-1.png" alt="">
  <figcaption>input의 placeholder나 버튼의 색상</figcaption>
</figure>

**사례2**    

<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast_ex_donot02.png" alt="">
  <figcaption>글자와 배경의 명도대비가 3:1 미만인 경우</figcaption>
</figure>

**사례3**    

<figure aria-hidden="true" style="text-align:center;border:1px solid #000">
  <img src="./../images/a11y-mobile/img_a11yMobile_contrast_ex_donot03.png" alt="">
  <figcaption>글자와 배경의 명도대비가 3:1 미만인 경우</figcaption>
</figure>


#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/UeRoj4zVQKU?si=HmF1ezEljt0pq6Bl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 모바일 앱 접근성 (4.명도대비)](https://www.youtube.com/embed/UeRoj4zVQKU?si=HmF1ezEljt0pq6Bl){: target="_blank"}    

<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/q8THhm0y1GA?si=npQe6MpgZbS4N7dg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

   
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


---
---



**자막, 수화 등의 제공**   
   - 영상이나 음성 콘텐츠에는 동등한 내용의 자막, 원고 또는 수화가 제공되어야 한다.   
   
**색에 무관한 인식**   
   - 화면에 표시되는 모든 정보는 색에 관계없이 인식될 수 있어야 한다.      
   

**명확한 지시 사항**    
   - 지시 사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.       
   
**알림 기능**    
   - 알림 정보는 화면 표시, 소리, 진동 등 다양한 방법으로 제공되어야 한다.       
   
**초점**     
   - 의미나 기능을 갖는 모든 사용자 인터페이스 컴포넌트에는 초점(focus)이 적용되고, 초점은 논리적인 순서로 이동되어야 한다.       
   
**누르기 동작 지원**     
   - 터치(touch) 기반 모바일 기기의 모든 컨트롤은 누르기 동작으로 제어할 수 있어야 한다.       
   
**응답 시간 조절**     
    - 시간 제한이 있는 콘텐츠는 응답 시간을 조절할 수 있어야 한다.       
   
**정지 기능 제공**     
    - 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.       
   
**컨트롤의 크기와 간격**     
    - 컨트롤은 충분한 크기와 간격으로 제공되어야 한다.       
   
**입력 도움**     
    - 입력 서식 이용 시, 입력 오류를 방지하거나 정정할 수 있는 방법을 제공해야 한다.       
   
**사용자 인터페이스의 일관성**     
    - 사용자 인터페이스 컴포넌트들은 일관성 있게 배치되어야 한다.       
   
**깜박거림의 사용 제한**     
    - 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.       
   
**자동재생 금지**     
    - 자동으로 재생되는 배경음을 사용하지 않아야 한다.       
   
**예측가능성**     
    - 사용자가 의도하지 않는 화면 전환이나 이벤트 등이 실행되는 경우 사용자가 이해할 수 있는 방법으로 제공되어야 한다.       
   
**폰트 관련 기능의 활용**     
    - 텍스트 콘텐츠는 운영체제에서 제공하는 폰트 관련 기능을 활용할 수 있는 방법을 제공해야 한다.       
   
**보조 기술과의 호환성**     
    - 사용자 인터페이스 컴포넌트는 보조 기술을 이용하여 사용할 수 있도록 해야 한다.       
   


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
- [Colour Contrast Analyser (CCA)](https://www.tpgi.com/color-contrast-checker/){: target="_blank"}
- [Color Contrast Checker](https://coolors.co/contrast-checker){: target="_blank"}
- [WCAG Color Contrast Checker](https://accessibleweb.com/color-contrast-checker/){: target="_blank"}
- [Leonardo](https://leonardocolor.io/theme.html#){: target="_blank"}
- [WCAG Color contrast checker](https://chromewebstore.google.com/detail/wcag-color-contrast-check/plnahcmalebffmaghcpcmpaciebdhgdf){: target="_blank"}
- [Figma : Stark - Contrast & Accessibility Checker](https://www.figma.com/community/plugin/732603254453395948/stark-contrast-accessibility-checker){: target="_blank"}
- [Fabien Gavinet의 아티클 - Colors that make sense](https://medium.com/getaround-eu/colors-that-make-sense-505d0f3509c1){: target="_blank"}     
