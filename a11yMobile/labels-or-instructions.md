# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹과 모바일 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines)과 모바일 접근성 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 모바일 앱 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 모바일 앱을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 앱의 사용성을 크게 향상시킵니다.    

### 명확한 지시 사항
**관련 지침 : 지시 사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.**   
명확한 지시 사항은 사용자가 앱을 사용하면서 필요한 작업을 쉽게 이해하고 수행할 수 있도록 돕는 지침입니다. 지시 사항은 단순하고 이해하기 쉬운 언어로 작성되며, 행동을 유도할 때에는 구체적으로 어떤 조치를 해야 하는지 설명해야 합니다. 버튼, 링크, 입력 필드, 경고 메시지와 같은 UI 요소에 대한 명확한 설명과 안내를 제공하여 사용자들이 앱을 쉽게 탐색하고 기능을 활용할 수 있도록 합니다.   
[WCAG 2.2 Quick Reference - Label in Name](https://www.w3.org/WAI/WCAG22/quickref/#label-in-name){: target="_blank"}

**키워드**   
#모바일 앱 접근성, #모바일 앱 접근성 콘텐츠 제작 기법, #WCAG2.2, #명확한 지시 사항, #사용자 인터페이스, #지침 제공, #시각 장애, #인지 장애, #색각 이상, #청각 장애

#### 1. 필요성        
명확한 지시 사항은 모든 사용자가 작업을 이해하고 수행할 수 있도록 돕습니다. 지시 사항이 불분명하면 사용자는 필요한 정보를 놓치거나 오류를 범할 수 있습니다. 특히, 시각 장애인이나 인지 장애가 있는 사용자들은 텍스트와 안내의 의미를 쉽게 이해할 수 있어야 하며, 이를 통해 접근성을 보장할 수 있습니다.   

#### 2. 대상       
- **시각 장애인**: 스크린 리더를 사용하는 사용자.    
- **인지 장애인**: 복잡한 정보를 이해하기 어려운 사용자.    
- **고령 사용자**: 시력이 저하되거나 빠르게 정보를 처리하기 어려운 사용자.    
- **비장애인 포함 전체 사용자**: 명확하고 일관된 지시 사항을 통해 작업을 더 빠르고 쉽게 수행할 수 있는 사용자. 접근성이 잘 구현된 앱은 모든 사용자가 더 나은 사용자 경험을 할 수 있도록 도와줍니다.   

#### 3. 체크리스트       
- **지시 사항의 명확성**: 모든 지시 사항이 구체적이고 이해하기 쉬운 언어로 작성되었는가?    
- **라벨과 설명의 일관성**: 버튼, 링크, 입력 필드 등의 라벨과 설명이 일관되게 사용되었는가?    
- **에러 메시지의 명확성**: 에러 메시지가 사용자가 문제를 이해하고 해결할 수 있도록 충분히 설명되었는가?    
- **스크린 리더 호환성**: 스크린 리더를 사용할 때 지시 사항이 잘 전달되고 있는가?     


#### 4. 기기별 테스트 방법      
**iOS**    
- **VoiceOver 사용**: 지시 사항이 VoiceOver를 통해 명확히 전달되는지 테스트.    
- **폰트 크기 및 색상 대비 설정**: 지시 사항이 모든 접근성 설정에서도 읽기 쉬운지 확인.    

**Android**    
- **TalkBack 사용**: 지시 사항이 TalkBack을 통해 명확하게 전달되는지 테스트.    
- **고대비 모드 테스트**: 고대비 모드에서 지시 사항이 잘 보이는지 확인.    


#### 5. QA 지표     
- **지시 사항 명확성 점수**: 사용자 테스트를 통해 지시 사항의 명확성을 평가.    
- **에러 메시지 정확성 비율**: 제공된 에러 메시지가 문제를 설명하고 해결 방법을 제시하는 비율.     
- **스크린 리더 적합성**: 스크린 리더를 사용했을 때 지시 사항이 잘 인식되고 전달되는지 여부.  

#### 6. 개발방법     

**iOS**    
- UILabel과 UIButton의 접근성 속성 설정    

```sh
let submitButton = UIButton()
submitButton.setTitle("제출", for: .normal)
submitButton.accessibilityLabel = "신청서 제출 버튼"
submitButton.accessibilityHint = "신청서를 제출하려면 클릭하세요."
```

- 에러 메시지 제공   

```sh
let errorMessageLabel = UILabel()
errorMessageLabel.text = "이름을 입력하세요."
errorMessageLabel.textColor = .red
errorMessageLabel.accessibilityLabel = "오류: 이름 입력 필드가 비어 있습니다."
```

**Android**    

- Button의 접근성 속성 설정   

```sh
Button submitButton = findViewById(R.id.submitButton);
submitButton.setText("제출");
submitButton.setContentDescription("신청서 제출 버튼. 클릭하여 제출");
```

- 에러 메시지 제공   

```sh
TextView errorMessage = findViewById(R.id.errorMessage);
errorMessage.setText("이름을 입력하세요.");
errorMessage.setTextColor(Color.RED);
errorMessage.setContentDescription("오류: 이름 입력 필드가 비어 있습니다.");
```

**하이브리드(html)**   

- 버튼에 aria-label 설명 추가   

```sh
<button aria-label="신청서 제출" aria-describedby="submitHint">제출</button>
<div id="submitHint">신청서를 제출하려면 클릭하세요.</div>
```

- 에러 메시지 제공   

```sh
<span role="alert" style="color: red;">오류: 이름을 입력하세요.</span>
```

**하이브리드(Vue)**   

- 버튼에 aria-label 설명 추가   

```sh
<template>
  <button :aria-label="'신청서 제출'" @click="submitForm">제출</button>
  <p v-if="errorMessage" role="alert">{{ errorMessage }}</p>
</template>

<script>
export default {
  data() {
    return {
      errorMessage: ""
    };
  },
  methods: {
    submitForm() {
      if (this.isFormValid()) {
        // 제출 로직
      } else {
        this.errorMessage = "이름을 입력하세요.";
      }
    }
  }
};
</script>
```

**하이브리드(React)**   

- 버튼에 aria-label 설명 추가   

```sh
function App() {
  const [errorMessage, setErrorMessage] = React.useState("");

  const handleSubmit = () => {
    if (isFormValid()) {
      // 제출 로직
    } else {
      setErrorMessage("이름을 입력하세요.");
    }
  };

  return (
    <div>
      <button aria-label="신청서 제출" onClick={handleSubmit}>
        제출
      </button>
      {errorMessage && <p role="alert" style={{ color: "red" }}>{errorMessage}</p>}
    </div>
  );
}
```



#### 7. 점검 기준     

**오류 유형**    

- **모호한 지시 사항**: "여기를 클릭하세요"와 같이 구체적이지 않은 표현 사용.   
- **일관성 없는 라벨**: 같은 기능을 하는 요소가 화면마다 다른 라벨로 제공되는 경우.   
- **부족한 에러 메시지 정보**: "오류 발생"과 같이 구체적인 이유나 해결 방법이 없는 메시지.   
- **스크린 리더 호환성 부족**: 스크린 리더로 지시 사항이 제대로 읽히지 않거나 전달되지 않는 경우.   
- 색, 크기, 모양, 방향 등으로만 정보를 제공한 경우    
- 전달하고자 하는 지시사항을 소리로만 정보를 제공한 경우    

**주의사항**   

- **구체적인 지시 사항 사용**: "파일을 선택하려면 '파일 업로드' 버튼을 클릭하세요"와 같이 구체적으로 작성합니다.    
- **일관된 라벨 사용**: 같은 기능을 하는 버튼이나 링크는 동일한 라벨을 사용해야 합니다.   
- **에러 메시지 개선**: 사용자가 문제를 해결할 수 있도록 구체적인 지침을 제공합니다(예: "비밀번호는 최소 8자 이상이어야 합니다").   
- **스크린 리더 테스트 수행**: 개발 중 스크린 리더를 사용하여 라벨과 설명이 명확히 전달되는지 확인합니다.    
-  노인이나 약시자의 경우에 브라우저의 글자체를 확대시켜 콘텐츠를 표시하면 콘텐츠의 표시 위치가 지시하는 위치와 달라져 혼란을 줄 수 있으므로 가급적 위치 정보를 이용하여 지시하지 않도록 콘텐츠를 구현하는 것을 권장    

#### 8. 점검 방법     
페이지를 구성하는 콘트롤이 특정요소로만 지시를 하거나 표현하는지 점검한다. (대체 수단 없이 음성 혹은 음향으로 지시사항을 전달하는 경우 포함)     

**특정요소로만 지시를 하는 사례**
- 방향, 위치 정보로만 이용하는 사용법을 알려주는 경우    
- 화면의 위치만으로 객체를 지정하는 경우    
- 버튼의 모양만을 이용하여 사용법을 알려주는 경우    
- 음성으로만 지시하는 경우 등    

**iOS**    

- **VoiceOver 사용**: iOS의 VoiceOver 기능을 켜고, 지시 사항이 음성으로 명확하게 전달되는지 테스트합니다. 버튼, 입력 필드, 에러 메시지 등에서 올바른 라벨과 설명이 전달되는지 확인합니다.    
  예시) iPhone의 설정 > 손쉬운 사용 > VoiceOver를 켜고, 앱에서 버튼을 클릭할 때 "신청서 제출 버튼"이라는 지시 사항이 VoiceOver에서 출력되는지 확인합니다.     
- **폰트 크기 및 색상 대비 설정**: 설정에서 폰트 크기를 크게 설정하거나 색상 대비(고대비)를 활성화한 후, 지시 사항이 여전히 명확하게 보이는지 확인합니다.      
  예시) 설정 > 손쉬운 사용 > 디스플레이 및 텍스트 크기에서 '더 굵게', '투명도 줄이기' 등을 적용하여 텍스트 가독성을 확인합니다.      

**Android**     

- **TalkBack 사용**: Android의 TalkBack 기능을 켜고, 버튼, 링크, 입력 필드 등에 올바른 지시 사항이 음성으로 전달되는지 확인합니다.     
  예시) Android 설정 > 손쉬운 사용 > TalkBack을 켜고, 앱에서 버튼을 클릭할 때 "신청서 제출 버튼"이라는 설명이 TalkBack으로 읽히는지 테스트합니다.     
- **고대비 모드 테스트**: Android에서 색상 반전 또는 고대비 텍스트 설정을 활성화한 후, 앱에서 지시 사항이 명확하게 보이는지 테스트합니다.    
  예시) 설정 > 손쉬운 사용 > 색상 반전 또는 고대비 텍스트 활성화 후, UI 요소들이 충분히 가독성이 있는지 확인합니다.    

**HTML**    

- **스크린 리더 사용**: PC에서 스크린 리더(NVDA, JAWS 등)를 사용하여 웹 페이지에서 버튼, 링크, 입력 필드의 접근성 라벨이 명확하게 전달되는지 확인합니다.     
  예시) NVDA 스크린 리더를 실행하고, 버튼을 클릭할 때 "신청서 제출 버튼"이라는 음성 피드백이 올바르게 출력되는지 확인합니다.    
- **색상 대비 도구 사용**: Chrome의 DevTools 또는 Axe와 같은 자동화 접근성 도구를 사용하여 색상 대비 및 접근성 라벨 설정이 잘 되어 있는지 점검합니다.    
  예시) DevTools > Audits에서 접근성 분석을 실행하여 색상 대비 및 라벨 적절성을 확인합니다.    

**Vue**   

- **스크린 리더 사용**: Vue.js로 개발된 웹 애플리케이션에서도 NVDA 또는 VoiceOver 같은 스크린 리더를 사용해 지시 사항과 라벨이 적절하게 전달되는지 점검합니다.    
  예시) Vue.js 컴포넌트에서 "aria-label" 속성이 올바르게 설정되어 있는지, 스크린 리더로 확인합니다.    
- **Vue 접근성 플러그인 사용**: Vue.js용 접근성 플러그인을 설치하여 자동으로 접근성 문제를 탐지하고 수정할 수 있는 방법도 사용합니다.    

**React**    

- **스크린 리더 및 자동화 도구 사용**: React로 개발된 애플리케이션에서는 NVDA와 같은 스크린 리더와 함께 Lighthouse 또는 Axe 같은 접근성 도구로 점검합니다.    
  예시) React 컴포넌트의 접근성 속성이 제대로 설정되었는지 확인하고, 접근성 오류가 있는지 Lighthouse로 분석합니다.    
- **React 접근성 개발자 도구**: React 개발자 도구를 사용해 컴포넌트별로 접근성 라벨과 속성이 올바르게 설정되었는지 확인합니다.     


#### 9. 준수 사례       

**사례1**   

- 지시사항을 명확하게 제공한 경우    
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_labelor_ex_do01.png" alt="">
    <figcaption>출처 : 모바일 애플리케이션 접근성 제작기법</figcaption>
  </figure>

- 자동 가입 방지를 위한 인증 도구의 하나로 캡챠(captcha)를 사용    
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_labelor_ex_do02.png" alt="">
    <figcaption>출처 : 모바일 애플리케이션 접근성 제작기법</figcaption>
  </figure>
  캡챠의 지시사항이 “팝콘이 있는 이미지를 모두 선택하세요”와 같이 시각에만 의존하고 있어 시각에 장애가 있는 사용자는 지시 사항을 인식하고 수행하는 것이 불가능하다. 이런 경우에는 대체할 수 있는 수단을 제공하는 것이 바람직하며, 이 애플리케이션에서는 오디오서비스를 제공하고 있다).     



#### 10. 미준수 사례       

**사례1**   

- 색, 크기, 모양, 방향 등으로만 정보를 제공한 경우    
  '여기서 확인하세요!'로 방향으로만 정보를 제공하고 있음     
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_labelor_ex_donot01.png" alt="">
    <figcaption>출처 : 모바일 애플리케이션 접근성 제작기법</figcaption>
  </figure>

- '마이페이지/이곳'으로 방향으로만 정보를 제공하고 있음.      
  텍스트 안에 링크나 버튼을 넣지 않아야 한다. 아래 예처럼 텍스트 안에 링크가 있는 경우 스크린 리더는 빠르게 텍스트를 읽어 나가기 때문에 화면의 레이아웃을 파악하기 힘든 시각장애인은 링크 위치를 알 수 없다.    
  <figure aria-hidden="true" style="text-align:center;border:1px solid #000">
    <img src="./../images/a11y-mobile/img_a11yMobile_labelor_ex_donot02.png" alt="">
    <figcaption>출처 : 모바일 애플리케이션 접근성 제작기법</figcaption>
  </figure>


#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/f2M5ej1-D2w?si=eFExck_hs80jgSnM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 모바일 앱 접근성 (5. 명확한지시사항)](https://www.youtube.com/embed/f2M5ej1-D2w?si=eFExck_hs80jgSnM){: target="_blank"}    
   
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
