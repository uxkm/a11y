# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹과 모바일 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines)과 모바일 접근성 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 모바일 앱 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 모바일 앱을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 앱의 사용성을 크게 향상시킵니다.    

### 대체 텍스트 제공 (Alternative Text)
**텍스트 아닌 콘텐츠는 대체 가능한 텍스트와 함께 제공되어야 한다.**   
대체 텍스트는 비 텍스트 콘텐츠를 설명하는 중요한 요소로, 접근성을 높이기 위해 필수적으로 제공되어야 합니다. 다양한 테스트 도구를 활용해 웹 및 모바일 앱에서 대체 텍스트를 포함한 접근성 요소를 철저히 점검하고, 사용자 경험을 개선할 수 있습니다. 접근성을 준수함으로써 모든 사용자에게 포용적인 디지털 환경을 제공합니다.   
[WCAG 2.2 Quick Reference - Non-text Content](https://www.w3.org/WAI/WCAG22/quickref/#non-text-content){: target="_blank"}

**키워드**   
#모바일 앱 접근성, #모바일 앱 접근성 콘텐츠 제작 기법, #WCAG2.2, #대체 텍스트, #비 텍스트 콘텐츠, #accessibilityLabel, #contentDescription, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #VoiceOver, #TalkBack, #UIAccessibility API #AccessibilityNodeInfo API, #Swift, #Kotlin, #네이티브 #하이브리드

#### 1. 필요성        
대체 텍스트는 이미지, 동영상, 아이콘 등 비 텍스트 콘텐츠의 의미를 텍스트로 설명하여, 시각 장애인이나 저시력 사용자가 스크린 리더를 통해 콘텐츠를 이해할 수 있도록 돕습니다. 이는 접근성을 보장하며, 웹 및 앱에서 모든 사용자가 동등하게 콘텐츠에 접근할 수 있게 합니다.   

#### 2. 대상       
- **시각 장애인**: 스크린 리더를 사용하는 사용자들.   
- **저시력 사용자**: 텍스트 크기 조정 및 색상 대비에 의존하는 사용자들.   
- **고령자**: 시력이 저하된 사용자들.   
- **인지 장애인**: 복잡한 비주얼 콘텐츠를 이해하는 데 어려움을 겪는 사용자들.   

#### 3. 체크리스트       
- **대체 텍스트 제공 여부**: 모든 비 텍스트 콘텐츠에 대체 텍스트가 제공되고 있는가?   
- **적절성**: 대체 텍스트가 콘텐츠의 의미를 정확하게 전달하고 있는가?   
- **중복 여부**: 같은 콘텐츠에 대해 중복된 대체 텍스트가 제공되고 있지 않은가?    
- **불필요한 정보 배제**: 장식용 이미지에 대체 텍스트가 불필요하게 포함되어 있지 않은가?     
- **스크린 리더 테스트**: 대체 텍스트가 스크린 리더에서 올바르게 읽히는가?     


#### 4. 기기별 테스트 방법      
**iOS**     
- **VoiceOver 활성화**: 설정 > 접근성 > VoiceOver를 활성화하여 대체 텍스트가 올바르게 읽히는지 테스트합니다.   
- **Accessibility Inspector 사용**: Xcode의 'Accessibility Inspector'를 통해 UI 요소의 대체 텍스트 적용 상태를 확인합니다.    
- [iPhone 사용 설명서 - VoiceOver](https://help.apple.com/iphone/11/?lang=ko#/iph3e2e415f){: target="_blank"}
   
**Android**   
- **TalkBack 활성화**: 설정 > 접근성 > TalkBack을 활성화하여 대체 텍스트가 적절하게 읽히는지 테스트합니다.    
- **Accessibility Scanner 사용**: Google Play에서 제공하는 'Accessibility Scanner' 앱을 사용하여 대체 텍스트의 적용 여부를 자동으로 탐지합니다.      
- [Android 접근성 고객센터 - TalkBack 및 Android](https://support.google.com/accessibility/android/topic/10601571?hl=ko&ref_topic=3529932&sjid=14261166623289476037-AP){: target="_blank"}

#### 5. QA 지표       
- **대체 텍스트 오류 비율**: 대체 텍스트가 누락되거나 부정확하게 제공된 UI 요소의 비율.   
- **스크린 리더 정확성**: 스크린 리더를 통해 올바르게 읽히는 대체 텍스트의 비율.   
- **사용자 피드백**: 실제 사용자 테스트를 통해 대체 텍스트의 적절성에 대한 피드백을 수집.   


#### 6. 개발방법       
**네이티브**     

- **iOS**    
  - [관련문서:Apple's Accessibility Programming Guide for iOS](https://developer.apple.com/accessibility/ios/){: target="_blank"}
  - **Interface Builder 이용하여 요소에 대체 텍스트 적용하는 방법**   
      - Xcode에서 Interface Builder를 열고, UI 요소를 선택합니다.    
      - 'Identity Inspector'의 'Accessibility' 섹션을 찾아 'Label' 필드에 대체 텍스트를 입력합니다.   
  - **UIAccessibility API를 활용하여 코드에 대체 텍스트 제공**    
```sh
let imageView = UIImageView(image: UIImage(named: "sunrise.jpg"))
imageView.accessibilityLabel = "A beautiful sunrise over the mountains"
```

- **Android**         
  - [관련문서:Android Accessibility Overview](https://developer.android.com/guide/topics/ui/accessibility){: target="_blank"}
  - **contentDescription 속성 사용**    
```sh
<ImageView
    android:id="@+id/myImage"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:contentDescription="A beautiful sunrise over the mountains" />
```   
- **코드에서 contentDescription 설정**    
```sh
val myButton: Button = findViewById(R.id.my_button)
myButton.contentDescription = "Submit"
```

- **하이브리드(html)**    
```sh
<img src="sunrise.jpg" alt="A beautiful sunrise over the mountains">
```
- **하이브리드(Vue)**    
```sh
<template>
  <img :src="sunriseImage" alt="A beautiful sunrise over the mountains">
</template>

<script>
export default {
  data() {
    return {
      sunriseImage: 'sunrise.jpg'
    };
  }
};
</script>
```
- **하이브리드(React)**    
```sh
import React from 'react';

function SunriseImage() {
  return <img src="sunrise.jpg" alt="A beautiful sunrise over the mountains" />;
}

export default SunriseImage;
```


#### 7. 점검 기준     
텍스트가 아닌 콘텐츠에 해당 이미지가 제공하는 의미나 용도를 동일하게 인식할 수 있는 적절한 대체 텍스트를 제공한다.    

**오류유형**    
- 이미지 요소가 제공하는 정보와 동일한 정보가 음성으로 출력되지 않는 경우      
- 의미와 용도를 이해할 수 없는 대체 텍스트를 제공하는 경우     
- 의미없는 이미지에 대체텍스트를 제공하는 경우     
- 대체 텍스트 제공 없이 설명만 제공되는 경우(Hint로만 제공된 경우)     
- 객체 유형 정보가 반복 제공되는 경우 (~이미지이미지, ~버튼버튼 등)    
- 객체 유형에 대한 정보가 잘못 제공된 경우     
- display:none, visibility:hidden으로 대체텍스트가 제공된 경우     
- 화면에 보이지 않는 형태로 대체텍스트가 제공된 경우 (터치방식으로 대체정보 확인이 불가한 경우)       
   
**주의사항**     
- 기능을 제공하는 경우 이용방법 등 충분한 설명을 제공하지 않은 경우 (권고)     
- 숫자 정보에 대해 의미전달이 미흡한 대체텍스트를 제공하는 경우 (권고) : 준수예) 6.20 --> 6월20일     
- 권고) 객체 유형정보를 정확히 제공할 것을 권장함(Traits 정보)     
- IR기법으로 대체텍스트를 제공 시 hidden형태가 아니더라도 화면 터치방식으로는 대체정보 인지 불가함(오류)     

#### 8. 점검 방법     
**VoiceOver**         
- **음성출력 형태**: VoiceOver는 UI 요소의 accessibilityLabel을 읽어줍니다. 예를 들어, "Submit button"이라고 출력합니다.    
- **제공방법**: Xcode의 Interface Builder에서 Label 필드에 텍스트를 입력하거나, 코드에서 accessibilityLabel을 설정합니다.    

**TalkBack**    
- **음성출력 형태**: TalkBack은 contentDescription 속성에 설정된 텍스트를 읽어줍니다.    
- **제공방법**: Android Studio에서 XML의 contentDescription 속성을 사용하거나, 코드에서 직접 설정합니다.    

**방법 1 (문서 제공기준)**
TalkBack(또는 Voice Assistant 등) 기능으로 텍스트가 아닌 콘텐츠에 대응하는 대체 텍스트의 적절성 여부를 확인한다.    
- 화면 구성 정보를 제공하는지 확인한다. (Title, List View, Grid View)     
- 화면 내 구체적인 Contents를 읽어주는지 확인한다. (Text, Imge)     
- 화면 내 기능을 읽어주는지 확인한다. (Button 등)     
<figure aria-hidden="true" style="text-align:center">
   <img src="./../images/a11y-mobile/img_a11yMobile_check01-01.jpg" alt="">
   <img src="./../images/a11y-mobile/img_a11yMobile_check01-02.jpg" alt="">
   <figcaption>이미지 출처 : 모바일 애플리케이션 접근성 제작기법</figcaption>
</figure>

**방법 2 (문서 제공기준)**
음성출력 표시 기능으로 텍스트가 아닌 콘텐츠에 대응하는 대체 텍스트의 적절성 여부를 점검한다.    
- 설정→접근성→시각→Talk Back→설정→개발자 설정→음성출력 표시 체크 후 확인한다.     
<figure aria-hidden="true" style="text-align:center">
   <img src="./../images/a11y-mobile/img_a11yMobile_check02-01.jpg" alt="">
   <figcaption>이미지 출처 : 모바일 애플리케이션 접근성 제작기법</figcaption>
</figure>

**방법 3 (문서 제공기준)**
UIAutoMatorViewer를 활용하여 점검한다.     
- Android Studio를 이용한 실행방법     
  - Toolbar에서 Android Device Monitor 버튼을 선택    
    <figure aria-hidden="true" style="text-align:center">
        <img src="./../images/a11y-mobile/img_a11yMobile_check03-01.jpg" alt="">
        <figcaption>이미지 출처 : 모바일 애플리케이션 접근성 제작기법</figcaption>
    </figure>

#### 9. 준수 사례       


#### 10. 미준수 사례       


#### 11. 접근성 테스트 도구 활용 점검방법      
**Lighthouse**    
- Lighthouse는 Google Chrome의 DevTools에 내장된 자동화 도구로, 웹 페이지의 접근성을 분석할 수 있습니다.    
- **사용법**    
    1. Google Chrome에서 웹 페이지를 엽니다.    
    2. DevTools (F12)를 열고 'Lighthouse' 탭을 선택합니다.    
    3. 'Accessibility' 항목을 선택하고 'Generate report'를 클릭하여 보고서를 생성합니다.    
    4. Lighthouse는 접근성 점수와 함께 개선이 필요한 부분을 제시합니다.    
   
**Axe**    
- Axe는 웹 접근성 테스트를 위한 브라우저 확장 프로그램으로, WCAG 가이드라인에 따른 접근성 오류를 실시간으로 탐지합니다.    
- **사용법**        
    1. Chrome 또는 Firefox에 Axe 확장 프로그램을 설치합니다.   
    2. 웹 페이지를 열고 Axe 확장 프로그램을 실행하여 분석을 시작합니다.   
    3. Axe는 페이지에서 발견된 접근성 문제와 이를 해결하기 위한 권장사항을 제시합니다.   
   
**Accessibility Scanner (Android)**    
- Accessibility Scanner는 Android 기기에서 접근성 문제를 탐지하는 Google Play의 앱입니다.    
- **사용법**    
    1. Android 기기에 Accessibility Scanner 앱을 설치합니다.   
    2. 앱을 실행하고 분석하려는 화면에서 스캔을 시작합니다.   
    3. 앱은 화면에서 발견된 접근성 문제를 보고하고 개선 방법을 제시합니다.   
 
#### 12. 참고 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/eQHPJ4tk-ag?si=mMQd3txeiPLQc_4B" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 모바일 앱 접근성 (1.대체 텍스트)](https://www.youtube.com/watch?v=eQHPJ4tk-ag){: target="_blank"}    



---



**자막, 수화 등의 제공**   
   - 영상이나 음성 콘텐츠에는 동등한 내용의 자막, 원고 또는 수화가 제공되어야 한다.   
   
**색에 무관한 인식**   
   - 화면에 표시되는 모든 정보는 색에 관계없이 인식될 수 있어야 한다.      
   
**명도 대비**   
   - 화면에 표시되는 모든 사용자 인터페이스 컴포넌트와 텍스트는 전경색과 배경색이 구분될 수 있도록 제공되어야 한다.      
   
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
