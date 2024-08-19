## 접근성 체크리스트

### 모바일 앱 접근성
<!-- > 모바일 접근성은 모바일 디바이스와 애플리케이션을 사용할 때 모든 사람들이 정보와 기능에 접근할 수 있도록 하는 것을 의미하고, 터치스크린 사용, 소형 화면 크기, 다양한 입력 방식 등 모바일 특성을 고려한 접근성을 말한다.  -->

<!-- > 국내에서는 행정안전부고시 제2011-38호에 따르면 "모바일 접근성 이란 모바일 기기를 사용하여 모바일 애플리케이션을 이용하고자 하는 장애인, 고령자 등을 포함한 모든 사람들에게 활용가능성이 제공됨을 말한다." 라고 정의하고 있다.
국제 웹 접근성 이니셔티브는 모바일 접근성을 WCAG(Web Content Accessibility Guidelines)의 일환으로 다루고 있으며, 국내에서는 이러한 국제 기준에 맞춰 모바일 앱 접근성 지침을 마련하여 적용하고 있다.   
웹 콘텐츠 접근성 가이드라인(WCAG)과 마찬가지로 모바일 애플리케이션 정보접근성도 사용자가 콘텐츠를 인지할 수 있게 하고, 콘텐츠를 운용하며, 콘텐츠를 이해하고, 견고한 콘텐츠를 제공하는 것을 중요하게 여긴다.
 -->
> 모바일 애플리케이션 콘텐츠를 구축, 운영, 개선 및 유지 보수할 경우에 적용하는 것으로 모바일 전화기, 태블릿기기 등 모바일 기기에서 실행되는 모든 애플리케이션 및 콘텐츠를    
WCAG 2.0(Web Content Accessibility Guidelines 2.0)에서 제시하고 있는 접근성 설계의 4가지 원칙 기준으로,    
**모바일 애플리케이션 콘텐츠의 설계 및 개발을 위한 지침을 제시하고 있다.**

### 5. 인식의 용이성 (Perceivable)
#### 5.1 (대체 텍스트) 텍스트 아닌 콘텐츠는 대체 가능한 텍스트와 함께 제공되어야 한다.
> 모든 이미지에는 대체 텍스트를 제공하여야 합니다. 이는 시각 장애인 사용자가 스크린 리더를 통해 이미지의 내용을 이해할 수 있도록 제공한다.   
[WCAG 2.2 Guideline : 1.1.1 비텍스트 콘텐츠(Text Alternatives)](https://www.w3.org/TR/WCAG22/#non-text-content){: target="_blank"}     
[UAAG 2.0 Reference](https://www.w3.org/TR/IMPLEMENTING-UAAG20/mobile.html#gl-access-alternative-content){: target="_blank"}  

1. **필요성**    
   - 접근성 보장: 시각 장애 사용자는 스크린 리더를 통해 웹 페이지나 앱의 내용을 접근. 대체 텍스트가 제공되면 이미지나 비디오의 의미를 스크린 리더가 읽어준다.   
   - SEO 향상: 검색 엔진은 이미지 파일을 직접 해석하지 못하므로, 대체 텍스트는 검색 엔진 최적화(SEO)에 기여한다.   
   - 콘텐츠 로드 실패 시 대처: 이미지가 로드되지 않거나 손상된 경우, 대체 텍스트는 이미지의 의미를 그대로 전달할 수 있다.    
   - 법적 준수: 웹 접근성 관련 법률을 준수하여 모든 사용자가 정보에 동등하게 접근할 수 있도록 보장.    
2. **제공 방법**    
   - 모든 이미지에 대체 텍스트 제공     
     - 콘텐츠의 의미를 설명하는 간단하고 명확한 대체 텍스트를 모든 이미지에 추가합니다. 의미 없는 장식용 이미지는 alt=""로 설정하여 스크린 리더가 이를 무시하도록 할 수 있다.   
   - 기타 비텍스트 콘텐츠에 대한 설명 제공     
     - 비디오나 오디오 콘텐츠에는 자막이나 텍스트 설명을 제공하여, 청각 장애 사용자나 비디오를 시청할 수 없는 사용자들이 콘텐츠를 이해할 수 있도록 한다.    
   - 적절한 길이와 명확성 유지     
     - 대체 텍스트는 간결하고 명확해야 하며, 콘텐츠의 핵심 의미를 정확하게 전달해야 합니다. 너무 길거나 짧지 않도록 주의.    

```sh
<!-- 기본 예시 -->   
<img src="created_by02_gray.jpg" alt="마이크 앞에서 노래를 부르는 아이">

<!-- 잘못된 예시 : alt 속성과 aria-label을 중복 사용한 경우 -->
<img src="submit_button.png" alt="제출" aria-label="제출">

<!-- 올바른 예시1 : alt 속성만 사용하는 경우 (이미지) -->
<img src="submit_button.png" alt="제출">

<!-- 올바른 예시2 : aria-label 속성만 사용하는 경우 (텍스트가 없는 버튼 등) -->
<button aria-label="제출"><img src="submit_button.png" alt=""></button>
```

**검수 방법**
- 대체 텍스트 존재 확인: 모든 이미지 및 비텍스트 콘텐츠에 적절한 대체 텍스트가 제공되고 있는지 확인하였는가?   
- 마크업에서 alt 속성, aria-label 속성 등이 올바르게 사용되고 중복된 정보를 제공하였는지 확인하였는가?   
- 모바일 기기에서 화면 읽기 소프트웨어(예: iOS의 VoiceOver, Android의 TalkBack)를 사용하여 텍스트가 아닌 콘텐츠에 대한 대체 텍스트가 올바르게 읽히는지 확인하였는가?   
- 접근성 검사 도구(예: Google Lighthouse, Axe)를 사용하여 자동화된 접근성 검사를 수행하고 문제점을 확인하였는가?   


#### 5.2 (자막, 수화 등의 제공) 영상이나 음성 콘텐츠에는 동등한 내용의 자막, 원고 또는 수화가 제공되어야 한다.
> 동영상 및 오디오 콘텐츠에는 자막, 대체 텍스트, 오디오 설명 등을 제공해야 한다.   
[WCAG 2.2 Guideline : 1.2.2 자막 (미디어)(Captions (Prerecorded))](https://www.w3.org/TR/WCAG22/#captions-prerecorded)   
[WCAG 2.2 Guideline : 1.2.3 오디오 설명 또는 미디어 대체 (오디오)(Audio Description or Media Alternative (Prerecorded))](https://www.w3.org/TR/WCAG22/#audio-description-or-media-alternative-prerecorded)   

1. **필요성**    
   - 청각 장애인: 청각 장애를 가진 사용자도 콘텐츠를 이해할 수 있도록 한다.   
   - 비공개 환경: 공공장소나 소음을 내기 어려운 환경에서도 콘텐츠를 이용할 수 있게 한다.   
   - 언어 학습: 자막을 통해 외국어 학습이나 언어 이해를 도울 수 있다.    
2. **제공 방법**    
   - 자막 (Captions)     
     - 동기 자막: 영상과 동시에 제공되는 자막으로, 대화뿐만 아니라 중요한 소리(예: [박수], [전화벨])도 포함.    
     - 폐쇄 자막 (Closed Captions): 사용자가 켜고 끌 수 있는 자막.    
     - 열린 자막 (Open Captions): 영상에 항상 표시되는 자막.   
   - 원고 (Transcript)     
     - 영상이나 오디오의 대화 내용과 중요한 소리를 텍스트로 제공.    
     - 동기화가 필요 없는 경우, 사용자가 내용을 쉽게 검색하고 읽을 수 있다.    
   - 수화 (Sign Language)     
     - 수화 통역을 통해 청각 장애인이 콘텐츠를 이해할 수 있도록 도움.    
     - 화면 구석에 수화 통역사를 표시하는 방법을 사용.    


```sh
<!-- 잘못된 예시 : 영상 콘텐츠에 자막, 원고 또는 수화가 제공되지 않은 경우 -->
<video src="video.mp4" controls></video>

<!-- 올바른 예시1 : 영상 콘텐츠에 자막을 제공하는 경우 -->
<video src="video.mp4" controls>
  <track kind="captions" src="captions_en.vtt" srclang="en" label="English">
</video>

<!-- 올바른 예시2 : 영상 콘텐츠에 원고를 제공하는 경우 -->
<video src="video.mp4" controls></video>
<a href="transcript.txt">영상 원고 보기</a>

<!-- 올바른 예시3 : 영상 콘텐츠에 수화 통역을 제공하는 경우 -->
<video src="video_with_sign_language.mp4" controls></video>
```

**검수 방법**
- 자막이 정확하게 표시되고, 대화와 동기화되는지 확인하였는가?   
- 원고가 영상이나 오디오의 내용을 정확히 반영하고 있는지 확인하였는가?   
- 수화 통역이 영상의 내용을 정확히 전달하는지, 화면에 잘 보이는지 확인하였는가?   


#### 5.3 (색에 무관한 인식) 화면에 표시되는 모든 정보는 색에 관계없이 인식될 수 있어야 한다. 
> 콘텐츠는 색에 관계없이 인식될 수 있어야 한다. 이는 색상에 의존하는 정보 전달을 피해야 하며, 색상만으로는 정보를 전달하지 않도록 한다.   
WCAG 2.2 Guidelines : [1.4.1 색 사용(Use of Color)](https://www.w3.org/TR/WCAG22/#use-of-color){: target="_blank"}   

1. **필요성**    
   - 색각 장애 사용자 보호: 색각 장애를 가진 사용자들이 색을 구별하기 어려운 상황에서 정보를 놓칠 수 있습니다. 색 외의 다른 요소를 사용하면 이 문제를 해결할 수 있다.   
   - 사용자 경험 향상: 색만으로 정보를 전달하지 않음으로써 모든 사용자가 쉽게 정보를 인식하고 이해할 수 있다.    
   - 접근성 보장: 색을 구별할 수 없는 사용자를 포함해 다양한 사용자가 앱을 접근 가능하게 이용할 수 있도록 보장.    
2. **제공 방법**    
   - 텍스트 및 패턴 사용     
     - 중요한 정보나 상태는 색상 외에 텍스트, 패턴, 아이콘 등 다른 시각적 요소를 함께 사용하여 전달.   
     - 예를 들어, 오류 메시지는 빨간색으로만 표시하는 대신 "오류"라는 텍스트를 함께 표시하거나 아이콘을 사용.      
   - 명확한 레이블 제공     
     - 색으로 구분되는 요소들은 명확한 레이블이나 설명을 포함하여 색을 구별하지 않고도 이해할 수 있도록 구분.    
     - 예를 들어, 그래프에서 색으로 표시된 데이터는 각 데이터가 무엇을 의미하는지 레이블로 표시.   
   - 색상 대비를 고려한 디자인        
     - 색상 대비가 충분히 명확하도록 설계하여, 색각 장애 사용자가 색을 구분할 수 있도록 합니다. 그러나 이와 함께 색 외의 다른 구별 요소도 추가로 제공.    
   - 테스트 및 검수        
     - 색각 장애 시뮬레이션 도구를 사용하여 디자인을 테스트하고, 색에 관계없이 정보가 전달될 수 있는지 확인.    

```sh
<!-- 네이티브 앱 예시 (Android) - 텍스트와 아이콘을 사용하여 상태를 전달 -->
// xml code
<TextView
    android:id="@+id/statusText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="오류 발생"
    android:textColor="#FF0000" <!-- 색상 외에 텍스트로 오류 상태를 전달 -->
    android:drawableStart="@drawable/ic_error" /> <!-- 오류 아이콘 사용 -->
// java code
Button button = findViewById(R.id.myButton);// 버튼 상태를 텍스트와 색상으로 구분
button.setText("비활성화됨");
button.setTextColor(Color.GRAY); // 비활성화된 상태를 회색 텍스트로 표시
button.setEnabled(false);

<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 색상 외의 요소를 사용하여 구분 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Color Independent Recognition Example</title>
    <style>
        .error-message {
            color: #FF0000;
            font-weight: bold;
        }
        .success-message {
            color: #008000;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <p class="error-message">⚠️ 오류 발생: 입력한 데이터가 유효하지 않습니다.</p> <!-- 텍스트와 아이콘 사용 -->
    <p class="success-message">✔️ 성공: 데이터가 정상적으로 저장되었습니다.</p> <!-- 텍스트와 아이콘 사용 -->
</body>
</html>

<!-- 잘못된 예시 (네이티브) - 텍스트 없이 색상만으로 상태를 전달하여 색각 장애 사용자가 정보를 이해하기 어려움 -->
<TextView
    android:id="@+id/statusText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:textColor="#FF0000" /> <!-- 텍스트 없이 색상만 사용 -->


<!-- 잘못된 예시 (하이브리드) - 색상만으로 정보를 구분하여 색각 장애 사용자가 정보를 구별하기 어려움 -->
<p style="color: #FF0000;">오류</p> <!-- 색상만으로 정보 전달 -->
<p style="color: #008000;">성공</p> <!-- 색상만으로 정보 전달 -->


<!-- 올바른 예시 - (네이티브) - 색상과 함께 텍스트 및 아이콘을 사용하여 상태를 명확하게 전달함 -->
<TextView
    android:id="@+id/statusText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="오류 발생"
    android:textColor="#FF0000"
    android:drawableStart="@drawable/ic_error" />

<!-- 올바른 예시 (하이브리드) - 색상 외의 텍스트와 아이콘을 사용하여 정보를 전달함. -->
<p class="error-message">⚠️ 오류 발생: 입력한 데이터가 유효하지 않습니다.</p>
<p class="success-message">✔️ 성공: 데이터가 정상적으로 저장되었습니다.</p>
```


**검수 방법**
- 색에 무관한 정보 전달 확인: 모든 중요한 정보가 색상 외의 텍스트, 아이콘, 패턴 등 다른 시각적 요소로도 전달되고 있는지 확인하였는가?     
- 색각 장애 테스트: 색각 장애 시뮬레이션 도구를 사용하여 디자인이 색각 장애 사용자에게도 동일한 정보를 제공하는지 테스트하였는가?     
- 사용자 테스트: 다양한 사용자가 색상 외의 요소를 통해 정보를 올바르게 인식할 수 있는지 테스트하였는가?     
- 접근성 검사 도구 사용: WAVE, Axe 등의 도구를 사용하여 색상만으로 정보를 전달하는 요소를 점검하였는가?   


#### 5.4 (명도 대비) 화면에 표시되는 모든 사용자 인터페이스 컴포넌트와 텍스트는 전경색과 배경색이 구분될 수 있도록 제공되어야 한다.  
> 페이지에서 보이는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 충분한 대비를 제공하여, 저시력장애인, 색각장애인, 고령자 등도 콘텐츠를 인식할 수 있도록 제공해야 한다.    
다만, 로고, 장식목적의 콘텐츠, 마우스나 키보드를 활용하여 초점을 받았을 때 명도 대비가 커지는 콘텐츠 등은 예외로 한다.    
**중요 : 작업 시 많이 오류를 범하는 항목**
WCAG 2.2 Guidelines : [1.4.3 명도 대비 (Contrast (Minimum))](https://www.w3.org/TR/WCAG22/#contrast-minimum){: target="_blank"}   

1. **필요성**    
   - 시각 장애 사용자: 저시력 사용자나 색각 이상 사용자도 명확하게 텍스트와 UI 요소를 인식할 수 있어야 한다.   
   - 다양한 환경: 밝은 햇빛이나 어두운 조명 환경에서도 정보를 쉽게 읽을 수 있도록 보장.    
   - 사용자 피로 감소: 명도 대비가 충분하면 눈의 피로를 줄이고 장시간 사용에도 편안함을 제공.    
2. **제공 방법**    
   - 충분한 명도 대비 비율 사용     
     - 일반 텍스트: 최소 명도 대비 비율 4.5:1   
     - 큰 텍스트(18pt 이상 또는 14pt 볼드체 이상): 최소 명도 대비 비율 3:1      
     - UI 요소와 그래픽 객체: 최소 명도 대비 비율 3:1      
   - 색 선택     
     - 전경색과 배경색의 대비를 명확히 하여 가독성을 높임    
     - 예: 흰색 배경에 검은색 텍스트 또는 어두운 배경에 밝은 텍스트   
   - 명도 대비 도구 사용        
     - 명도 대비를 계산해주는 툴(예: WebAIM Contrast Checker)을 사용하여 충분한 대비를 보장    


```sh
<!-- 네이티브 앱 예시 (Android) - 명도 대비를 고려한 텍스트와 버튼 디자인 -->
<TextView
    android:id="@+id/label"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="로그인"
    android:textColor="#FFFFFF" <!-- 전경색: 흰색 -->
    android:background="#000000" <!-- 배경색: 검정색 -->
    android:textSize="18sp" />

<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="제출"
    android:textColor="#FFFFFF" <!-- 전경색: 흰색 -->
    android:background="#007AFF" <!-- 배경색: 파란색 -->
    android:padding="16dp" />


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 명도 대비를 고려한 텍스트와 버튼 스타일 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contrast Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0; /* 배경색: 연회색 */
        }

        .button {
            background-color: #007AFF; /* 배경색: 파란색 */
            color: #FFFFFF; /* 전경색: 흰색 */
            padding: 16px;
            border: none;
            font-size: 16px;
            border-radius: 5px;
        }

        .text {
            color: #000000; /* 전경색: 검정색 */
            font-size: 18px;
            background-color: #FFFFFF; /* 배경색: 흰색 */
            padding: 10px;
        }
    </style>
</head>
<body>
    <p class="text">로그인</p>
    <button class="button">제출</button>
</body>
</html>


<!-- 잘못된 예시 (네이티브) - 텍스트와 배경색의 대비가 부족하여, 사용자가 내용을 읽기 어려움 -->
<TextView
    android:id="@+id/label"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="로그인"
    android:textColor="#888888" <!-- 전경색: 회색 -->
    android:background="#AAAAAA" <!-- 배경색: 연회색 -->
    android:textSize="18sp" />


<!-- 잘못된 예시 (하이브리드) - 명도 대비가 낮아 텍스트가 배경에 묻혀 잘 보이지 않음. -->
<style>
    .button {
        background-color: #CCCCCC; /* 배경색: 연회색 */
        color: #AAAAAA; /* 전경색: 밝은 회색 */
        padding: 16px;
        border: none;
        font-size: 16px;
        border-radius: 5px;
    }
</style>
<p class="text" style="color: #888888; background-color: #AAAAAA;">로그인</p> <!-- 명도 대비 부족 -->
<button class="button">제출</button>


<!-- 올바른 예시 (네이티브) - 텍스트와 배경의 명도 대비를 충분히 확보하여, 텍스트가 명확하게 보이도록 함 -->
<TextView
    android:id="@+id/label"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="로그인"
    android:textColor="#FFFFFF" <!-- 전경색: 흰색 -->
    android:background="#000000" <!-- 배경색: 검정색 -->
    android:textSize="18sp" />


<!-- 올바른 예시 (하이브리드) - 텍스트와 배경색 간의 명도 대비를 충분히 확보하여 가독성을 보장함 -->
<style>
    .button {
        background-color: #007AFF; /* 배경색: 파란색 */
        color: #FFFFFF; /* 전경색: 흰색 */
        padding: 16px;
        border: none;
        font-size: 16px;
        border-radius: 5px;
    }
</style>
<p class="text" style="color: #000000; background-color: #FFFFFF;">로그인</p>
<button class="button">제출</button>
```

**검수 방법**
- 콘텐츠의 명도 대비: 페이지가 제공하는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 명도 대비는 4.5:1 이상이어야 한다. 준수하였는가?     
- 폰트 크기에 따른 명도 대비: 텍스트 콘텐츠를 구성하고 있는 텍스트 폰트를 18pt 이상 또는 14pt 이상의 굵은 폰트를 사용하는 경우, 명도 대비를 3:1까지 낮출 수 있다. 준수하였는가?   
- 화면 확대가 가능한 콘텐츠: 화면 확대가 가능하도록 구현한 텍스트 콘텐츠(텍스트 및 텍스트 이미지)의 명도 대비는 3:1까지 낮출 수 있다. 준수하였는가?   
- 명도 대비 검사 도구를 사용하여 텍스트와 UI 요소의 대비 비율을 확인하였는가?   
- Axe, WAVE 등의 접근성 검사 도구를 사용하여 페이지 전체의 명도 대비 문제를 확인하였는가?   


#### 5.5 (명확한 지시 사항) 지시 사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.  
> 사용자 인터페이스를 설계할 때, 지시사항이나 안내는 특정 감각적 특성(모양, 크기, 위치, 방향, 색, 소리 등)에 의존하지 않고 명확히 전달되어야 한다.    
즉, 색상에만 의존하여 정보를 전달하는 것이 아니라 텍스트나 다른 시각적 단서도 함께 제공해야 한다.    
WCAG 2.2 Guidelines : [WCAG 2.2 - 레이블 또는 지시 사항 (Labels or Instructions)](https://www.w3.org/TR/WCAG22/#labels-or-instructions){: target="_blank"}

1. **필요성**    
   - 다양한 사용자를 고려: 시각, 청각, 인지 장애를 가진 사용자뿐만 아니라 다양한 상황에서 접근성을 보장   
   - 명확한 커뮤니케이션: 모호하지 않고 명확한 지시 사항은 사용자의 실수를 줄이고, 사용자 경험을 향상    
   - 일관성 유지: 일관된 지시 사항은 모든 사용자가 동일한 방식으로 인터페이스를 이해하고 사용할 수 있게 한다    
2. **제공 방법**    
   - 텍스트 기반 지시 사항     
     - 지시 사항을 텍스트로 명확하게 설명   
     - 예: “오른쪽 상단의 빨간 버튼을 클릭하세요” 대신 “‘제출’ 버튼을 클릭하세요”.      
   - 명확한 아이콘과 라벨     
     - 아이콘에 설명 텍스트(라벨)를 추가하여 의미를 명확히 제공    
     - 예: 저장 아이콘에 “저장” 텍스트 라벨 추가   
   - 다양한 대체수단 제공        
     - 단순히 색이나 모양에 의존하지 않고, 텍스트, 패턴, 위치 등 다양한 대체수단을 함께 제공    
     - 예: “파란색 버튼을 클릭하세요” 대신 “‘제출’ 버튼을 클릭하세요 (파란색 버튼)”.    
   - 소리 이외의 시각적 대체수단        
     - 소리로만 전달되는 정보를 시각적 대체수단(텍스트, 아이콘 등)으로도 제공    
     - 예: 경고음을 텍스트 알림과 함께 제공.    


```sh
<!-- 네이티브 앱 예시 (Android) - 텍스트 기반의 명확한 지시 사항 제공 -->
<TextView
    android:id="@+id/instructionText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="다음 단계로 진행하려면 '다음' 버튼을 누르세요."
    android:textSize="16sp" />

<Button
    android:id="@+id/nextButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="다음"
    android:contentDescription="다음 단계로 진행 버튼" /> <!-- 명확한 레이블과 설명 제공 -->

// 버튼 클릭 이벤트 처리
Button nextButton = findViewById(R.id.nextButton);
nextButton.setOnClickListener(v -> {
    // 다음 단계로 진행하는 로직
});


<!-- 하이브리드 앱 예시 - 지시 사항을 텍스트로 명확하게 제공 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clear Instructions Example</title>
    <style>
        .instruction {
            font-size: 16px;
            margin-bottom: 10px;
        }

        .button {
            background-color: #007AFF;
            color: #FFFFFF;
            padding: 10px 20px;
            border: none;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <p class="instruction">다음 단계로 진행하려면 아래 '다음' 버튼을 클릭하세요.</p>
    <button class="button" aria-label="다음 단계로 진행">다음</button> <!-- 명확한 레이블 제공 -->
</body>
</html>


<!-- 잘못된 예시 (네이티브) - 색상이나 위치에 의존한 지시 사항 제공으로 인해 시각 장애 사용자가 지시 사항을 이해하기 어려움. -->
<TextView
    android:id="@+id/instructionText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="녹색 버튼을 눌러 진행하세요." /> <!-- 색상에 의존한 지시 사항 -->


<!-- 잘못된 예시 (하이브리드) - 색상이나 모양만으로 지시 사항을 제공하여, 텍스트 없이 정보가 전달되기 어려움. -->
<p style="font-size: 16px;">오른쪽 위 모서리에 있는 빨간 버튼을 누르세요.</p> <!-- 위치에 의존한 지시 사항 -->
<button style="background-color: red;">Proceed</button> <!-- 색상에 의존 -->


<!-- 올바른 예시 (네이티브) - 명확한 텍스트로 지시 사항을 제공하여, 색상이나 위치에 의존하지 않고도 지시 사항을 이해할 수 있도록 함 -->
<TextView
    android:id="@+id/instructionText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="다음 단계로 진행하려면 '다음' 버튼을 누르세요." />

<Button
    android:id="@+id/nextButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="다음"
    android:contentDescription="다음 단계로 진행 버튼" />


<!-- 올바른 예시 (하이브리드) - 텍스트와 함께 명확한 레이블을 제공하여 모든 사용자가 지시 사항을 이해할 수 있도록 함. -->
<p class="instruction">다음 단계로 진행하려면 아래 '다음' 버튼을 클릭하세요.</p>
<button class="button" aria-label="다음 단계로 진행">다음</button>
```

**검수 방법**
- 지시 사항이 색상, 위치, 모양 등에 의존하지 않고 텍스트로 명확하게 제공되는지 확인하였는가?    
- 지시 사항이 색상이나 소리 이외에도 텍스트로 제공되었는지 확인하였는가?     
- 지시 사항이 일관되게 사용되고 있는지, 모호한 부분이 없는지 검토하였는가?     
- Axe, WAVE 등의 접근성 검사 도구를 사용하여 지시 사항의 명확성을 점검하였는가?     
- 다양한 사용자(시각, 청각, 인지 장애를 가진 사용자 포함)와 상황에서 지시 사항이 명확하게 이해되는지 테스트하였는가?     
         

#### 5.6 (알림 기능) 알림 정보는 화면 표시, 소리, 진동 등 다양한 방법으로 제공되어야 한다.  
> 알림 정보는 화면 표시, 소리, 진동 등 다양한 방법으로 제공되어야 한다. 이는 사용자가 놓치기 쉬운 중요한 정보를 다양한 감각을 통해 전달함으로써 접근성을 높이는 데 중요하다.   
WCAG 2.2 Guidelines : [1.3.3 감각 특성 (Sensory Characteristics)](https://www.w3.org/TR/WCAG22/#sensory-characteristics){: target="_blank"}   

1. **필요성**    
   - 다양한 사용자 고려: 시각, 청각, 촉각 장애를 가진 사용자가 알림을 받을 수 있도록 한다   
   - 사용자 환경 다양성: 사용 환경에 따라 알림을 인지할 수 있는 다양한 방법을 제공    
   - 중요 정보 전달: 중요한 정보나 긴급 상황에서 사용자가 놓치지 않도록 한다    
2. **제공 방법**    
   - 화면 표시     
     - 팝업 창, 배너, 토스트 메시지 등 시각적인 방법으로 알림을 제공   
     - 예: "새 메시지가 도착했습니다."라는 팝업 알림.      
   - 소리     
     - 청각적인 방법으로 알림을 제공하여 사용자 설정에 따라 알림음을 설정할 수 있게 한다    
     - 예: 새로운 이메일이 도착했을 때 소리로 알림   
   - 진동        
     - 촉각적인 방법으로 알림을 제공. 특히 청각 장애인이나 시각 장애인을 위해 유용하다    
     - 예: 휴대폰이 진동으로 새로운 알림을 전달.    
   - 다중 알림 방식        
     - 화면 표시, 소리, 진동 등 여러 가지 방법을 조합하여 사용자가 알림을 놓치지 않도록 한다    
     - 예: 중요한 일정 알림 시 화면에 팝업을 띄우고, 소리와 진동을 함께 제공.    


```sh
<!-- 네이티브 앱 예시 (Android) - 화면 표시, 소리, 진동을 통한 알림. 알림을 생성하는 코드 예시 -->
NotificationCompat.Builder builder = new NotificationCompat.Builder(this, "channelId")
        .setSmallIcon(R.drawable.notification_icon)
        .setContentTitle("새 메시지")
        .setContentText("새로운 메시지가 도착했습니다.")
        .setPriority(NotificationCompat.PRIORITY_HIGH)
        .setVibrate(new long[] { 0, 500, 1000 }) // 진동 패턴 설정
        .setSound(RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION)) // 소리 알림 설정
        .setAutoCancel(true); // 알림 클릭 시 자동 삭제

NotificationManagerCompat notificationManager = NotificationManagerCompat.from(this);
notificationManager.notify(1001, builder.build()); // 알림 표시

// 버튼 클릭 이벤트 처리
Button nextButton = findViewById(R.id.nextButton);
nextButton.setOnClickListener(v -> {
    // 다음 단계로 진행하는 로직
});


<!-- 하이브리드 앱 예시 - 화면 표시와 소리, 진동을 통한 알림 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Notification Example</title>
</head>
<body>
    <button onclick="sendNotification()">알림 보내기</button>

    <script>
        function sendNotification() {
            // 화면 표시 (브라우저 알림)
            if (Notification.permission === "granted") {
                const notification = new Notification("새 메시지", {
                    body: "새로운 메시지가 도착했습니다.",
                    icon: "notification_icon.png"
                });
            }

            // 소리 알림
            const audio = new Audio('notification_sound.mp3');
            audio.play();

            // 진동 알림 (모바일 기기에서 작동)
            if (navigator.vibrate) {
                navigator.vibrate([500, 1000, 500]); // 진동 패턴 설정
            }
        }

        // 알림 권한 요청
        if (Notification.permission !== "granted") {
            Notification.requestPermission();
        }
    </script>
</body>
</html>


<!-- 잘못된 예시 (네이티브) - 시각적 알림만 제공되어 소리나 진동이 필요한 사용자는 알림을 놓칠 수 있음. -->
NotificationCompat.Builder builder = new NotificationCompat.Builder(this, "channelId")
        .setSmallIcon(R.drawable.notification_icon)
        .setContentTitle("새 메시지")
        .setContentText("새로운 메시지가 도착했습니다.")
        .setPriority(NotificationCompat.PRIORITY_HIGH)
        .setAutoCancel(true); // 시각적 알림만 제공


<!-- 잘못된 예시 (하이브리드) - 소리 알림만 제공되어 청각 장애를 가진 사용자는 알림을 인식할 수 없음. -->
<script>
    function sendNotification() {
        // 소리 알림만 제공
        const audio = new Audio('notification_sound.mp3');
        audio.play();
    }
</script>


<!-- 올바른 예시 (네이티브) - 화면 표시, 소리, 진동을 함께 사용하여 모든 사용자가 알림을 인식할 수 있도록 함 -->
NotificationCompat.Builder builder = new NotificationCompat.Builder(this, "channelId")
        .setSmallIcon(R.drawable.notification_icon)
        .setContentTitle("새 메시지")
        .setContentText("새로운 메시지가 도착했습니다.")
        .setPriority(NotificationCompat.PRIORITY_HIGH)
        .setVibrate(new long[] { 0, 500, 1000 }) // 진동 패턴 설정
        .setSound(RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION)) // 소리 알림 설정
        .setAutoCancel(true); // 알림 클릭 시 자동 삭제

<!-- 올바른 예시 (하이브리드) - 화면 표시, 소리, 진동을 모두 활용하여 다양한 방법으로 알림을 제공함. -->
<script>
    function sendNotification() {
        // 화면 표시 (브라우저 알림)
        if (Notification.permission === "granted") {
            const notification = new Notification("새 메시지", {
                body: "새로운 메시지가 도착했습니다.",
                icon: "notification_icon.png"
            });
        }

        // 소리 알림
        const audio = new Audio('notification_sound.mp3');
        audio.play();

        // 진동 알림 (모바일 기기에서 작동)
        if (navigator.vibrate) {
            navigator.vibrate([500, 1000, 500]); // 진동 패턴 설정
        }
    }

    // 알림 권한 요청
    if (Notification.permission !== "granted") {
        Notification.requestPermission();
    }
</script>
```

**검수 방법**
- 시각, 청각, 촉각 장애를 가진 사용자와 다양한 환경에서 알림이 제대로 전달되는지 테스트 하였는가?     
- Axe, WAVE 등의 접근성 검사 도구를 사용하여 알림 기능의 접근성을 점검하였는가?     
- 조용한 환경, 시끄러운 환경, 어두운 환경 등 다양한 환경에서 알림이 인지되는지 확인하였는가?   



### 6. 운용의 용이성 (Operable)
#### 6.1 (초점) 의미나 기능을 갖는 모든 사용자 인터페이스 컴포넌트에는 초점(focus)이 적용되고, 초점은 논리적인 순서로 이동되어야 한다.
> 의미나 기능을 갖는 모든 사용자 인터페이스 컴포넌트에는 초점(focus)이 적용되고, 초점은 논리적인 순서로 이동되어야 합니다. 이는 터치 스크린을 사용하는 모바일 기기에서 접근성을 높이기 위해 중요한 원칙.    
**중요 : 작업 시 가장 많이 오류를 범하는 항목**
WCAG 2.2 Guidelines : [2.4.3 초점 순서 (Focus Order)](https://www.w3.org/TR/WCAG22/#focus-order){: target="_blank"}
WCAG 2.2 Guidelines : [2.4.7 초점 표시 (Focus Visible)](https://www.w3.org/TR/WCAG22/#focus-visible){: target="_blank"}

1. **필요성**    
   - 키보드 및 스위치 장치 사용자: 물리적 키보드, 스위치 장치, 스크린 리더 등을 사용하는 사용자들이 있다   
   - 접근성: 시각 장애 사용자나 기타 접근성 도구를 사용하는 사용자가 앱을 논리적인 순서로 탐색할 수 있도록 한다    
   - 사용 편의성: 명확한 초점 표시와 논리적인 초점 이동 순서는 사용 편의성을 크게 향상   
2. **제공 방법**    
   - 초점 가능한 요소 식별     
     - 버튼, 링크, 입력 필드 등 모든 상호작용 가능한 요소에는 초점이 적용되도록 한다   
     - 예: Button, TextView, EditText, ImageButton 등.      
   - 명확한 초점 스타일 제공     
     - 초점이 위치한 요소는 시각적으로 구별될 수 있도록 명확한 스타일을 제공    
     - 예: 초점이 있는 요소에 테두리, 배경색 등을 적용하여 시각적으로 구별   
   - 논리적인 초점 이동 순서        
     - 앱의 UI 요소를 논리적인 순서로 배치하여 사용자가 탐색할 때 초점이 자연스럽게 이동하도록 한다    
     - 필요시 android:nextFocusDown, android:nextFocusUp, android:nextFocusLeft, android:nextFocusRight 속성을 사용하여 초점 순서를 제어한다.    
   - 접근성 속성 사용        
     - 화면 표시, 소리, 진동 등 여러 가지 방법을 조합하여 사용자가 알림을 놓치지 않도록 한다    
     - contentDescription 속성을 사용하여 초점이 있는 요소의 의미와 기능을 명확히 전달.    


```sh
<!-- 네이티브 방식의 예시 -->
<!-- 초점 가능한 요소 설정 -->
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="제출"
    android:contentDescription="제출 버튼" />

<!-- 명확한 초점 스타일 제공 -->
<EditText
    android:id="@+id/nameInput"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="이름 입력"
    android:background="@drawable/focused_background" />

<!-- 논리적인 초점 이동 순서 설정 -->
<LinearLayout
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/nameInput"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="이름 입력"
        android:nextFocusDown="@id/emailInput" />

    <EditText
        android:id="@+id/emailInput"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="이메일 입력"
        android:nextFocusDown="@id/submitButton" />

    <Button
        android:id="@+id/submitButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="제출" />
</LinearLayout>


<!-- 하이브리드 방식의 예시 -->
<!-- 잘못된 예시 1 : 초점이 적용되지 않은 경우 -->
<div>클릭하세요</div>

<!-- 잘못된 예시 2 : 초점 스타일이 명확하지 않은 경우 -->
<a href="page.html" style="outline: none;">링크</a>

<!-- 올바른 예시 1 : 초점이 적용된 경우 -->
<button>클릭하세요</button>

<!-- 올바른 예시 2 : 명확한 초점 스타일을 제공한 경우 -->
<a href="page.html" style="outline: 2px solid #00f;">링크</a>

<!-- 올바른 예시 3 : 논리적인 초점 이동 순서를 설정한 경우 -->
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  <nav>
    <a href="#content">본문으로 이동</a>
    <a href="#menu">메뉴로 이동</a>
  </nav>
  <main id="content">
    <h1>메인 콘텐츠</h1>
    <p>여기에 주요 내용이 있습니다.</p>
  </main>
  <aside id="menu">
    <h2>메뉴</h2>
    <ul>
      <li><a href="page1.html">페이지 1</a></li>
      <li><a href="page2.html">페이지 2</a></li>
    </ul>
  </aside>
</body>
</html>
```

**검수 방법**
- 키보드로 탐색 테스트: 키보드나 스위치 장치를 사용하여 앱을 탐색하면서 모든 상호작용 요소에 초점이 제대로 적용되는지 확인하였는가?     
- 초점 스타일 확인: 초점이 적용된 요소가 시각적으로 명확히 구별되는지 확인하였는가?     
- 논리적인 순서 확인: 키보드로 앱을 탐색할 때 초점 이동 순서가 논리적이고 직관적인지 확인하였는가?     
- 접근성 검사 도구 사용: Axe, WAVE, Google Accessibility Scanner, TalkBack 등의 접근성 검사 도구를 사용하여 초점 관련 문제를 자동으로 검출하였는가?     


#### 6.2 (누르기 동작 지원) 터치(touch) 기반 모바일 기기의 모든 컨트롤은 누르기 동작으로 제어할 수 있어야 한다. 
> 터치(touch) 기반 모바일 기기의 모든 컨트롤은 누르기 동작으로 제어할 수 있어야 한다. 이는 모바일 앱의 접근성을 높이기 위한 기본적인 원칙으로, 다양한 사용자들이 직관적이고 쉽게 인터페이스를 조작할 수 있도록 보장한다.    
WCAG 2.2 Guidelines : [2.5.1 터치 조작 (Pointer Gestures))](https://www.w3.org/TR/WCAG22/#pointer-gestures){: target="_blank"}

1. **필요성**    
   - 터치스크린 사용자를 위한 접근성: 모바일 기기를 사용하는 대부분의 사용자들이 터치스크린을 통해 앱을 조작하기 때문에, 모든 기능은 누르기 동작으로 접근 가능해야 한다   
   - 직관적 조작: 다양한 사용자들이 직관적으로 컨트롤을 사용할 수 있도록 보장하여, 앱 사용 경험을 개선    
   - 보조 기기 사용자 고려: 터치 외에 스위치, 스타일러스 등 다른 입력 장치를 사용하는 사용자들도 있습니다. 이러한 장치도 기본적으로 누르기 동작을 지원   
2. **제공 방법**    
   - 모든 인터랙티브 요소의 터치 가능성 보장     
     - 버튼, 링크, 메뉴 항목 등 모든 상호작용 가능한 요소는 터치로 쉽게 누를 수 있어야 한다   
     - 예: 작은 터치 영역은 확대하거나, 요소 간 충분한 간격을 두어 실수로 누르는 것을 방지.      
   - 표준 터치 제스처 사용     
     - 사용자들이 익숙한 터치 제스처(단일 탭, 더블 탭 등)를 사용하여 조작할 수 있도록 한다    
     - 커스텀 제스처를 사용하는 경우, 그 사용 방법을 명확하게 안내해야 한다   
   - 시각적 피드백 제공        
     - 사용자가 터치했을 때 즉각적인 시각적 피드백을 제공하여 동작이 인식되었음을 알려준다    
     - 예: 버튼을 터치했을 때 색상이 변하거나, 눌린 효과가 나타나는 등.    
   - 중복된 제어 방식 제공        
     - 제스처만으로 접근할 수 있는 기능에는 누르기 동작을 통한 대체 접근 방법을 제공    
     - 예: 스와이프 제스처로만 열 수 있는 메뉴는, 누르기 동작을 통해서도 열 수 있도록 추가 버튼을 제공.    


```sh
<!-- 터치 가능한 버튼 (네이티브) -->
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="제출"
    android:contentDescription="제출 버튼" />

<!-- 시각적 피드백 적용 (네이티브) -->
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="제출"
    android:background="?android:attr/selectableItemBackground" />

<!-- 터치 영역 확대 (네이티브) -->
<Button
    android:id="@+id/smallButton"
    android:layout_width="64dp"
    android:layout_height="64dp"
    android:text="작은 버튼"
    android:padding="16dp" />


<!-- 하이브리드 방식의 예시 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Touch Button Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }

        .button {
            background-color: #007AFF;
            color: white;
            padding: 16px 32px;
            text-align: center;
            font-size: 16px;
            border-radius: 5px;
            margin: 16px;
            cursor: pointer;
            border: none;
            transition: background-color 0.3s ease;
        }

        .button:active {
            background-color: #005BB5; /* 시각적 피드백 */
            transform: scale(0.98); /* 버튼이 눌린 효과 */
        }

    </style>
</head>
<body>
    <button class="button" aria-label="제출 버튼">제출</button>
</body>
</html>
```

**검수 방법**
- 터치 테스트: (네이티브)Android Studio나 Xcode를 통해 앱을 실제 디바이스에서 테스트하여 터치가 제대로 인식되는지 확인하였는가?   
- 터치 테스트: (하이브리드)React Native 앱을 에뮬레이터나 실제 디바이스에서 테스트하여 모든 터치 인터랙션이 예상대로 동작하는지 확인하였는가?     
- 다양한 입력 장치로 테스트: 스타일, 기타 입력 장치를 사용하여 앱을 테스트하고, 터치 가능한 모든 요소가 제대로 작동하는지 확인하였는가?     
- 시각적 피드백 확인: 터치 동작 시 시각적 피드백(예: 색상 변화, 투명도 변화 등)이 있는지 확인하였는가?     
- 접근성 검사 도구 사용: Axe, WAVE, Google Google Accessibility Scanner 또는 React Native용 접근성 검사 도구를 사용하여 앱의 접근성을 확인하였는가?     


#### 6.3 (응답 시간 조절) 시간 제한이 있는 콘텐츠는 응답 시간을 조절할 수 있어야 한다.  
> 시간 제한이 있는 콘텐츠(예: 자동 로그아웃, 타임아웃 폼 제출 등)는 사용자가 응답 시간을 조절할 수 있어야 한다. 이는 모바일 앱에서 장애를 가진 사용자를 포함한 모든 사용자가 충분한 시간을 가지고 콘텐츠를 이용할 수 있도록 보장하는 중요한 접근성 원칙이다.    
WCAG 2.2 Guidelines : [2.2.1 타이밍 조정(Timing Adjustable)](https://www.w3.org/TR/WCAG22/#timing-adjustable){: target="_blank"}

1. **필요성**    
   - 장애 사용자 보호: 장애를 가진 사용자들은 콘텐츠를 이해하고 반응하는 데 더 많은 시간이 필요할 수 있습니다. 시간 제한을 조절할 수 없다면, 이러한 사용자들이 중요한 작업을 완료하지 못할 위험이 있다   
   - 사용자 편의성: 시간 제한을 연장하거나 비활성화할 수 있는 기능은 사용자가 보다 편안하게 앱을 사용할 수 있도록 도와줍니다. 이는 특히 느린 인터넷 연결을 사용하거나 복잡한 양식을 작성해야 하는 사용자들에게 유용하다    
   - 다양한 환경 대응: 사용자는 이동 중이거나 여러 작업을 동시에 수행하는 경우가 많습니다. 이런 상황에서 시간 제한을 조절할 수 있는 기능은 중요한 역할을 한다   
2. **제공 방법**    
   - 시간 연장 기능 제공     
     - 사용자에게 시간이 만료되기 전에 경고 메시지를 띄우고, 시간을 연장할 수 있는 옵션을 제공.      
   - 시간 제한 비활성화 옵션 제공     
     - 사용자가 특정 작업을 수행할 때 시간 제한을 비활성화할 수 있는 설정 옵션을 제공.   
   - 사용자 경고        
     - 시간 제한이 가까워지면 사용자에게 시각적, 청각적 또는 진동 알림을 통해 경고를 제공.    


```sh
<!-- 네이티브 앱 예시 (Android) - 시간 연장 알림 다이얼로그 -->
new AlertDialog.Builder(this)
    .setTitle("시간 연장")
    .setMessage("세션이 만료됩니다. 시간을 연장하시겠습니까?")
    .setPositiveButton("예", (dialog, which) -> {
        // 세션 연장 로직
    })
    .setNegativeButton("아니요", (dialog, which) -> {
        // 세션 종료 로직
    })
    .show();

<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 시간 연장 알림 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>세션 연장 예시</title>
    <style>
        .dialog {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0,0,0,0.5);
            z-index: 1000;
        }
        .dialog.active {
            display: block;
        }
    </style>
</head>
<body>
    <div id="timeoutDialog" class="dialog">
        <p>세션이 만료됩니다. 시간을 연장하시겠습니까?</p>
        <button id="extendTime">예</button>
        <button id="endSession">아니요</button>
    </div>

    <script>
        // 세션 타임아웃 시 다이얼로그 표시
        setTimeout(function() {
            document.getElementById('timeoutDialog').classList.add('active');
        }, 5000); // 5초 후에 타임아웃 다이얼로그 표시

        document.getElementById('extendTime').addEventListener('click', function() {
            // 세션 연장 로직
            document.getElementById('timeoutDialog').classList.remove('active');
        });

        document.getElementById('endSession').addEventListener('click', function() {
            // 세션 종료 로직
        });
    </script>
</body>
</html>

<!-- 잘못된 예시 (네이티브) - 자동 로그아웃 로직만 있고, 사용자에게 시간 연장 선택권을 제공하지 않음 -->
handler.postDelayed(() -> logout(), 5000);

<!-- 잘못된 예시 (하이브리드) - 사용자에게 알림 없이 폼이 자동 제출됨 -->
<script>
    setTimeout(function() {
        document.getElementById('myForm').submit();
    }, 5000);
</script>

<!-- 올바른 예시 (네이티브) -->
new AlertDialog.Builder(this)
    .setTitle("시간 연장")
    .setMessage("세션이 만료됩니다. 시간을 연장하시겠습니까?")
    .setPositiveButton("예", (dialog, which) -> {
        // 세션 연장 로직
    })
    .setNegativeButton("아니요", (dialog, which) -> {
        // 세션 종료 로직
    })
    .show();

<!-- 올바른 예시 (하이브리드) - 타임아웃 전에 사용자에게 연장 옵션 제공 -->
<script>
    setTimeout(function() {
        document.getElementById('timeoutDialog').classList.add('active');
    }, 5000);
</script>
```

**검수 방법**
- 시간 제한이 있는 모든 기능 확인: 시간 제한이 있는 기능(예: 자동 로그아웃, 폼 제출)이 사용자가 조정할 수 있도록 설계되었는지 확인하였는가?   
- 사용자 테스트: 실제 사용자가 시간을 연장할 수 있는지, 충분히 인지할 수 있는지를 테스트하였는가?     
- 시각적 피드백 확인: 터치 동작 시 시각적 피드백(예: 색상 변화, 투명도 변화 등)이 있는지 확인하였는가?     
- 접근성 도구 사용: Google Accessibility Scanner와 같은 접근성 검사 도구를 사용하여 해당 기능이 올바르게 동작하는지 확인하였는가?     


#### 6.4 (정지 기능 제공) 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.   
> 자동으로 움직이거나 갱신되는 콘텐츠(예: 슬라이드쇼, 애니메이션, 자동 갱신 광고 등)는 사용자가 이를 제어하거나 정지할 수 있는 기능을 제공해야 한다.    
이는 사용자가 콘텐츠를 충분히 읽고 이해할 수 있도록 도우며, 특정 사용자들에게 불편을 줄 수 있는 요소들을 제어할 수 있게 한다.    
WCAG 2.2 Guidelines : [2.2.2 일시 정지, 정지, 숨기기(Pause, Stop, Hide)](https://www.w3.org/TR/WCAG22/#pause-stop-hide){: target="_blank"}

1. **필요성**    
   - 인지 장애 사용자 보호: 자동으로 변경되는 콘텐츠는 주의 집중에 어려움을 겪는 사용자들에게 혼란을 줄 수 있습니다. 이들이 스스로 움직임을 제어하거나 정지할 수 있는 기능이 필요   
   - 시각 장애 사용자 지원: 자동으로 움직이는 콘텐츠는 스크린 리더 사용자에게 혼란을 줄 수 있으므로, 이러한 콘텐츠를 제어할 수 있는 옵션이 중요    
   - 사용자 경험 개선: 사용자가 콘텐츠를 스스로 제어할 수 있을 때, 더 나은 사용자 경험을 제공할 수 있다   
2. **제공 방법**    
   - 정지, 일시 정지, 또는 숨기기 기능 제공     
     - 슬라이드쇼나 자동 갱신 콘텐츠에 사용자가 정지하거나 일시 정지할 수 있는 버튼을 제공.      
   - 움직임을 비활성화할 수 있는 설정 제공     
     - 사용자 설정에서 자동 갱신 또는 애니메이션을 비활성화할 수 있는 옵션을 제공.   
   - 시각적 제어 제공        
     - 움직이는 콘텐츠에 대한 제어 버튼은 사용자에게 쉽게 접근 가능하고 눈에 띄는 위치에 배치.    


```sh
<!-- 네이티브 앱 예시 (Android) - 자동 슬라이드쇼 제어 버튼 -->
ImageView imageView = findViewById(R.id.imageView);
Button pauseButton = findViewById(R.id.pauseButton);
Button playButton = findViewById(R.id.playButton);

pauseButton.setOnClickListener(v -> {
    // 슬라이드쇼 일시 정지 로직
    imageView.clearAnimation();
});

playButton.setOnClickListener(v -> {
    // 슬라이드쇼 재생 로직
    Animation anim = new AlphaAnimation(0.0f, 1.0f);
    anim.setDuration(2000); // 2초 간격으로 슬라이드 변경
    anim.setRepeatCount(Animation.INFINITE);
    imageView.startAnimation(anim);
});

<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 자동 슬라이드쇼 제어 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>슬라이드쇼 제어 예시</title>
    <style>
        .controls {
            margin-top: 20px;
        }
        .controls button {
            padding: 10px 20px;
            margin-right: 10px;
        }
    </style>
</head>
<body>
    <div id="slideshow">
        <img id="slideImage" src="image1.jpg" alt="슬라이드 이미지">
    </div>
    <div class="controls">
        <button id="pauseButton">일시 정지</button>
        <button id="playButton">재생</button>
    </div>

    <script>
        let slideshowInterval;

        function startSlideshow() {
            slideshowInterval = setInterval(function() {
                // 슬라이드 변경 로직
                const slideImage = document.getElementById('slideImage');
                slideImage.src = slideImage.src === 'image1.jpg' ? 'image2.jpg' : 'image1.jpg';
            }, 2000); // 2초 간격으로 슬라이드 변경
        }

        document.getElementById('pauseButton').addEventListener('click', function() {
            clearInterval(slideshowInterval);
        });

        document.getElementById('playButton').addEventListener('click', function() {
            startSlideshow();
        });

        // 초기 슬라이드쇼 시작
        startSlideshow();
    </script>
</body>
</html>

<!-- 잘못된 예시 (네이티브) - 슬라이드쇼가 자동으로 변경되지만 정지 또는 제어할 방법이 제공되지 않음 -->
Animation anim = new AlphaAnimation(0.0f, 1.0f);
anim.setDuration(2000); // 2초 간격으로 슬라이드 변경
anim.setRepeatCount(Animation.INFINITE);
imageView.startAnimation(anim);

<!-- 잘못된 예시 (하이브리드) - 사용자가 정지할 수 없는 자동 슬라이드쇼 -->
<!-- 하이브리드 앱 - 잘못된 예시 -->
<script>
    setInterval(function() {
        const slideImage = document.getElementById('slideImage');
        slideImage.src = slideImage.src === 'image1.jpg' ? 'image2.jpg' : 'image1.jpg';
    }, 2000);
</script>

<!-- 올바른 예시 - (네이티브) - 슬라이드쇼를 일시 정지하거나 재생할 수 있는 제어 버튼을 제공 -->
pauseButton.setOnClickListener(v -> {
    // 슬라이드쇼 일시 정지 로직
    imageView.clearAnimation();
});

playButton.setOnClickListener(v -> {
    // 슬라이드쇼 재생 로직
    Animation anim = new AlphaAnimation(0.0f, 1.0f);
    anim.setDuration(2000); // 2초 간격으로 슬라이드 변경
    anim.setRepeatCount(Animation.INFINITE);
    imageView.startAnimation(anim);
});

<!-- 올바른 예시 (하이브리드) - 사용자가 슬라이드쇼를 정지하거나 다시 시작할 수 있도록 제어 버튼을 제공 -->
<!-- 하이브리드 앱 - 올바른 예시 -->
<script>
    document.getElementById('pauseButton').addEventListener('click', function() {
        clearInterval(slideshowInterval);
    });

    document.getElementById('playButton').addEventListener('click', function() {
        startSlideshow();
    });
</script>
```

**검수 방법**
- 자동 변경되는 모든 콘텐츠 확인: 자동으로 변경되거나 움직이는 모든 콘텐츠가 사용자 제어 기능을 제공하는지 확인하였는가?   
- 사용자 테스트: 실제 사용자들이 자동 콘텐츠를 제어할 수 있는지, 제어 버튼이 명확하고 사용하기 쉬운지를 테스트하였는가?     
- 접근성 도구 사용: Google Accessibility Scanner와 같은 접근성 검사 도구를 사용하여 자동 콘텐츠 제어 기능이 올바르게 작동하는지 확인하였는가?     


#### 6.5 (컨트롤의 크기와 간격) 컨트롤은 충분한 크기와 간격으로 제공되어야 한다.   
> 모바일 기기의 터치스크린에서 컨트롤(예: 버튼, 링크, 입력 필드)은 충분한 크기와 간격을 가져야 한다.    
이는 사용자가 실수로 잘못된 버튼을 누르거나 여러 컨트롤을 동시에 터치하는 것을 방지하고, 인터페이스를 쉽게 조작할 수 있도록 한다.    
WCAG 2.2 Guidelines : [2.5.5 크기와 간격(Target Size)](https://www.w3.org/TR/WCAG22/#target-size-enhanced){: target="_blank"}

1. **필요성**    
   - 사용자 편의성: 작은 컨트롤이나 가까이 배치된 컨트롤은 사용자에게 불편을 줄 수 있으며, 특히 손이 크거나 섬세한 조작이 어려운 사용자들에게 문제가 될 수 있다   
   - 오류 감소: 충분한 크기와 간격은 실수로 잘못된 버튼을 누르는 등의 오류를 줄여준다    
   - 접근성 보장: 시각 장애나 운동 장애를 가진 사용자들이 모바일 앱을 쉽게 사용할 수 있도록 하는 데 중요한 역할을 한다   
2. **제공 방법**    
   - 충분한 크기의 컨트롤 제공     
     - 사용자가 쉽게 누를 수 있는 크기의 버튼, 링크, 입력 필드 등 터치 가능한 요소는 최소한 44x44dp 이상의 크기로 제공해야 한다.      
   - 컨트롤 간의 충분한 간격 유지     
     - 컨트롤과 컨트롤의 중심간 간격을 최소한 9mm이상으로 충분히 제공하여 사용자가 실수로 여러 컨트롤을 동시에 터치하는 것을 방지한다.   
   - 터치 영역 확대        
     - 시각적으로 작은 컨트롤이라도, 터치 영역을 실제 컨트롤보다 크게 설정하여 사용자가 쉽게 조작할 수 있도록 한다.    


```sh
<!-- 네이티브 앱 예시 (Android) - 충분한 크기와 간격을 가진 버튼 -->
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:minWidth="48dp"
    android:minHeight="48dp"
    android:layout_margin="16dp"
    android:text="제출" />


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 충분한 크기와 간격을 가진 버튼 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Button Size Example</title>
    <style>
        .button {
            padding: 16px 24px; /* 터치 영역을 확보 */
            font-size: 18px;
            margin: 16px; /* 다른 컨트롤과의 간격 유지 */
            background-color: #007AFF;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <button class="button">제출</button>
</body>
</html>

<!-- 잘못된 예시 (네이티브) - 버튼의 크기가 너무 작고, 인접한 다른 컨트롤과 너무 가까이 배치되어 있어 터치하기 어려움 -->
<Button
    android:id="@+id/submitButton"
    android:layout_width="32dp"
    android:layout_height="32dp"
    android:layout_margin="4dp"
    android:text="제출" />

<!-- 잘못된 예시 (네이티브) - 작은 크기의 버튼이 촘촘하게 배치되어 있어 실수로 다른 버튼을 터치할 위험이 크다 -->
<button style="padding: 8px 12px; margin: 4px; font-size: 12px;">제출</button>


<!-- 올바른 예시 (네이티브) - 버튼의 크기를 충분히 키우고, 인접한 다른 컨트롤과의 간격을 확보 -->
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:minWidth="48dp"
    android:minHeight="48dp"
    android:layout_margin="16dp"
    android:text="제출" />

<!-- 올바른 예시 (하이브리드) - 버튼의 크기와 간격을 충분히 확보하여 사용자들이 쉽게 터치할 수 있도록 제공 -->
<button style="padding: 16px 24px; margin: 16px; font-size: 18px;">제출</button>
```

**검수 방법**
- 크기와 간격이 적절한지 확인: 컨트롤의 크기와 간격이 충분히 확보되었는지 확인합니다. 버튼이 최소 44x44dp 이상이고, 인접한 컨트롤과의 간격이 충분한지 테스트하였는가?   
- 터치 테스트: 실제 기기에서 터치스크린으로 컨트롤을 사용해보고, 실수로 다른 컨트롤을 터치할 가능성이 없는지 확인하였는가?     
- 접근성 검사 도구 사용: Google Accessibility Scanner와 같은 도구를 사용하여 크기와 간격이 접근성 기준을 충족하는지 점검하였는가?     


### 7. 이해의 용이성 (Understandable)
#### 7.1 (입력 도움) 입력 서식 이용 시, 입력 오류를 방지하거나 정정할 수 있는 방법을 제공해야 한다.   
> 입력 서식을 이용할 때 사용자가 잘못된 정보를 입력하지 않도록 도와주는 방법을 제공하거나, 오류 발생 시 이를 쉽게 정정할 수 있도록 안내해야 한다.    
이러한 기능은 사용자들이 올바른 데이터를 입력하도록 유도하며, 특히 인지 장애가 있는 사용자들에게 매우 중요.    
**중요 : 작업 시 많이 오류를 범하는 항목**   
WCAG 2.2 Guidelines : [3.3.1 오류 식별(Error Identification)](https://www.w3.org/TR/WCAG22/#error-identification){: target="_blank"}
WCAG 2.2 Guidelines : [3.3.3 오류 제안(Error Suggestion)](https://www.w3.org/TR/WCAG22/#error-suggestion){: target="_blank"}

1. **필요성**    
   - 사용자 편의성: 입력 과정에서 발생할 수 있는 오류를 최소화하여 사용자의 부담을 줄임   
   - 오류 방지: 사용자가 입력해야 하는 형식에 대한 명확한 지침을 제공함으로써 오류 발생을 줄일 수 있다    
   - 오류 정정 지원: 오류가 발생했을 때 사용자가 쉽게 이를 수정할 수 있는 피드백과 도움을 제공   
   - 접근성 보장: 특히 인지 장애나 시각 장애가 있는 사용자들이 입력 오류를 쉽게 식별하고 수정할 수 있도록 돕는다   
2. **제공 방법**    
   - 명확한 입력 지침 제공     
     - 입력 서식의 각 필드에 대해 사용자가 기대되는 입력 형식을 명확히 안내합니다(예: 전화번호 형식, 이메일 형식).      
     - 입력 필드에 힌트(placeholder)나 레이블(label)을 사용하여 입력 형식을 설명.      
   - 실시간 입력 검증     
     - 사용자가 입력하는 동안 실시간으로 오류를 검증하고, 문제가 있을 경우 즉시 피드백을 제공(예: 이메일 주소 형식 오류).   
   - 오류 발생 시 시각적 피드백 제공        
     - 오류가 발생한 필드를 시각적으로 강조(예: 빨간색 테두리)하고, 오류 메시지를 명확하게 표시하여 무엇이 잘못되었는지 설명.    
   - 오류 수정 가이드 제공        
     - 오류 메시지에 오류 수정 방법을 포함시켜 사용자가 쉽게 문제를 해결할 수 있도록 제공.    


```sh
<!-- 네이티브 앱 예시 (Android) - 실시간 입력 검증과 오류 피드백 -->
// xml code
<EditText
    android:id="@+id/emailInput"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="이메일 입력"
    android:inputType="textEmailAddress" />

<TextView
    android:id="@+id/emailError"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="올바른 이메일 주소를 입력하세요."
    android:textColor="#FF0000"
    android:visibility="gone" />

// java code
EditText emailInput = findViewById(R.id.emailInput);
TextView emailError = findViewById(R.id.emailError);

emailInput.addTextChangedListener(new TextWatcher() {
    @Override
    public void beforeTextChanged(CharSequence s, int start, int count, int after) {}

    @Override
    public void onTextChanged(CharSequence s, int start, int before, int count) {
        if (!Patterns.EMAIL_ADDRESS.matcher(s).matches()) {
            emailError.setVisibility(View.VISIBLE);
        } else {
            emailError.setVisibility(View.GONE);
        }
    }

    @Override
    public void afterTextChanged(Editable s) {}
});


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 실시간 입력 검증과 오류 피드백 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation Example</title>
    <style>
        .error {
            color: red;
            display: none;
            margin-top: 8px;
        }
        input:invalid {
            border-color: red;
        }
    </style>
</head>
<body>
    <form id="emailForm">
        <label for="emailInput">이메일:</label>
        <input type="email" id="emailInput" placeholder="example@domain.com" required>
        <div id="emailError" class="error">올바른 이메일 주소를 입력하세요.</div>
    </form>

    <script>
        const emailInput = document.getElementById('emailInput');
        const emailError = document.getElementById('emailError');

        emailInput.addEventListener('input', function() {
            if (emailInput.validity.typeMismatch) {
                emailError.style.display = 'block';
            } else {
                emailError.style.display = 'none';
            }
        });
    </script>
</body>
</html>

<!-- 잘못된 예시 (네이티브) - 이메일 형식이 잘못되었을 때 아무런 피드백을 제공하지 않음 -->
<EditText
    android:id="@+id/emailInput"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="이메일 입력" />


<!-- 잘못된 예시 (네이티브) - 사용자가 입력한 내용이 잘못되었을 때에도 명확한 오류 메시지를 제공하지 않음 -->
<input type="email" id="emailInput" placeholder="example@domain.com">

<!-- 올바른 예시 (네이티브) - 실시간으로 이메일 형식을 검증하고, 오류 시 사용자에게 명확한 피드백을 제공 -->
<EditText
    android:id="@+id/emailInput"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="이메일 입력"
    android:inputType="textEmailAddress" />

<TextView
    android:id="@+id/emailError"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="올바른 이메일 주소를 입력하세요."
    android:textColor="#FF0000"
    android:visibility="gone" />


<!-- 올바른 예시 (하이브리드) - 입력된 내용이 잘못되었을 때 즉시 오류 메시지를 표시하여 사용자가 쉽게 오류를 수정할 수 있도록 제공 -->
<input type="email" id="emailInput" placeholder="example@domain.com" required>
<div id="emailError" class="error">올바른 이메일 주소를 입력하세요.</div>
```

**검수 방법**
- 입력 검증 기능 테스트: 모든 입력 필드에 대해 실시간 검증과 오류 피드백이 제대로 작동하는지 확인하였는가?   
- 오류 메시지의 명확성 확인: 오류 메시지가 명확하고 사용자가 쉽게 이해할 수 있는지 검토하였는가?     
- 사용자 테스트: 실제 사용자들이 입력 과정에서 발생한 오류를 쉽게 식별하고 수정할 수 있는지 테스트하였는가?     
- 접근성 검사 도구 사용: Google Accessibility Scanner와 같은 도구를 사용하여 입력 필드와 오류 메시지가 접근성 기준을 충족하는지 점검하였는가?     


#### 7.2 (사용자 인터페이스의 일관성) 사용자 인터페이스 컴포넌트들은 일관성 있게 배치되어야 한다.    
> 사용자 인터페이스(UI) 컴포넌트들이 일관성 있게 배치되면 사용자는 앱을 보다 쉽게 탐색하고 이해할 수 있다.    
일관성 있는 UI는 사용자가 각 요소의 위치와 동작을 예측할 수 있게 해주며, 특히 장애를 가진 사용자들에게 더욱 중요한 역할을 한다.    
WCAG 2.2 Guidelines : [3.2.3 일관된 내비게이션(Consistent Navigation)](https://www.w3.org/TR/WCAG22/#consistent-navigation){: target="_blank"}
WCAG 2.2 Guidelines : [3.2.4 일관된 식별자(Consistent Identification)](https://www.w3.org/TR/WCAG22/#consistent-identification){: target="_blank"}

1. **필요성**    
   - 사용자 경험 향상: 일관성 있는 UI는 사용자가 앱을 더 쉽게 배우고 사용할 수 있도록 합니다. 반복적인 패턴은 사용자에게 익숙함을 주어 학습 곡선을 줄임   
   - 오류 감소: 일관성 있는 배치는 사용자가 인터페이스의 작동 방식을 이해하기 쉽게 하여, 실수로 잘못된 요소를 누르거나 잘못된 동작을 수행하는 것을 줄임   
   - 접근성 보장: 특히 인지 장애나 시각 장애를 가진 사용자들이 앱을 사용할 때, 일관된 레이아웃과 컴포넌트 배치는 중요한 접근성 요소가 된다   
2. **제공 방법**    
   - 컴포넌트의 위치 일관성 유지     
     - 주요 UI 컴포넌트(예: 내비게이션 메뉴, 버튼, 입력 필드 등)는 앱 내 모든 화면에서 일관된 위치에 배치되어야 한다.      
     - 예를 들어, “뒤로 가기” 버튼은 항상 화면의 왼쪽 상단에 위치.      
   - 시각적 디자인 일관성 유지     
     - 버튼, 텍스트, 아이콘 등의 시각적 스타일(예: 색상, 폰트, 크기)을 일관되게 사용하여 사용자에게 일관된 시각적 경험을 제공.   
     - 텍스트 필드는 모든 화면에서 동일한 크기와 스타일을 사용하여 일관된 시각적 힌트를 제공.   
   - 동작 패턴 일관성 유지        
     - 특정 동작(예: 스와이프, 탭 등)에 대한 응답은 모든 화면에서 동일하게 처리되어야 합니다. 예를 들어, 스와이프 제스처로 메뉴를 열거나 닫는 경우, 모든 화면에서 동일하게 작동하도록 제공.    
   - 내비게이션 구조의 일관성 유지        
     - 앱 내 모든 페이지와 기능은 일관된 내비게이션 구조를 따라야 한다. 사용자는 언제든지 동일한 방식으로 원하는 페이지로 이동할 수 있어야 한다.    


```sh
<!-- 네이티브 앱 예시 (Android) - 일관된 버튼 배치 -->
// xml code
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="16dp">

    <!-- 뒤로 가기 버튼: 모든 화면에서 왼쪽 상단에 일관되게 배치 -->
    <Button
        android:id="@+id/backButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="뒤로 가기"
        android:layout_gravity="start" />

    <!-- 주요 작업 버튼: 항상 동일한 스타일과 위치 유지 -->
    <Button
        android:id="@+id/mainActionButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="저장"
        android:layout_marginTop="16dp" />
</LinearLayout>


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 일관된 내비게이션과 버튼 스타일-->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>일관성 있는 UI 예시</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        nav {
            width: 100%;
            background-color: #007AFF;
            padding: 16px;
            color: white;
            text-align: center;
        }

        button {
            padding: 16px;
            margin: 16px;
            background-color: #007AFF;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
        }

        /* 모든 버튼에 동일한 스타일 적용 */
        .primary-button {
            background-color: #007AFF;
        }

        .secondary-button {
            background-color: #005BB5;
        }
    </style>
</head>
<body>
    <!-- 일관된 내비게이션 -->
    <nav>내비게이션 바</nav>

    <!-- 일관된 버튼 스타일 -->
    <button class="primary-button">저장</button>
    <button class="secondary-button">취소</button>
</body>
</html>


<!-- 잘못된 예시 (네이티브) - 동일한 작업을 수행하는 버튼이 각 화면마다 다른 위치에 배치되거나 스타일이 일관되지 않음 -->
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="16dp">

    <!-- 동일한 기능을 하는 버튼이 다른 위치에 배치됨 -->
    <Button
        android:id="@+id/backButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="뒤로 가기"
        android:layout_gravity="end" />

    <Button
        android:id="@+id/saveButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="저장"
        android:layout_gravity="center" />
</LinearLayout>



<!-- 잘못된 예시 (네이티브) - 동일한 동작을 수행하는 버튼이 다른 페이지에서 서로 다른 색상과 크기로 제공됨 -->
<button style="padding: 12px; background-color: green;">저장</button>
<button style="padding: 20px; background-color: red;">저장</button>


<!-- 올바른 예시 (네이티브) - 동일한 기능을 수행하는 버튼이 모든 화면에서 일관된 위치에 배치되고, 일관된 스타일이 적용됨 -->
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="16dp">

    <Button
        android:id="@+id/backButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="뒤로 가기"
        android:layout_gravity="start" />

    <Button
        android:id="@+id/saveButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="저장"
        android:layout_marginTop="16dp" />
</LinearLayout>

<!-- 올바른 예시 (하이브리드) - 동일한 기능을 수행하는 버튼이 모든 페이지에서 동일한 스타일과 위치를 유지함 -->
<button class="primary-button">저장</button>
```

**검수 방법**
- UI 컴포넌트의 위치와 스타일 일관성 확인: 모든 화면에서 주요 UI 컴포넌트(예: 내비게이션 바, 버튼 등)가 일관된 위치와 스타일로 배치되었는지 확인하였는가?     
- 사용자 테스트: 다양한 사용자가 앱을 사용하면서 일관성 있는 인터페이스로 인해 앱 사용이 쉬운지, 예상 가능한지 평가하였는가?     
- 접근성 검사 도구 사용: Google Accessibility Scanner와 같은 도구를 사용하여 UI 컴포넌트의 일관성이 접근성 기준을 충족하는지 점검하였는가?     


#### 7.3 (깜박거림의 사용 제한) 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.    
> 깜박이거나 번쩍이는 콘텐츠는 특정 사용자들에게 심각한 건강 문제를 일으킬 수 있다. 특히, 이러한 콘텐츠는 광과민성 발작을 유발할 위험이 있으며, 시각적으로 불편함을 줄 수 있다. 따라서, 깜박임의 빈도를 제한하거나, 깜박임이 없는 대체 콘텐츠를 제공해야 한다.    
WCAG 2.2 Guidelines : [2.3.1 3초 이상의 깜박임 (Three Flashes or Below Threshold)](https://www.w3.org/TR/WCAG22/#three-flashes-or-below-threshold){: target="_blank"}

1. **필요성**    
   - 광과민성 발작 방지: 일부 사용자들은 깜박이거나 번쩍이는 콘텐츠에 노출되면 발작을 일으킬 수 있습니다. 이를 방지하기 위해 깜박임을 사용하지 않거나, 깜박임 빈도를 제한해야 한다   
   - 시각적 불편함 감소: 지속적인 깜박임은 시각적 피로를 유발하고, 사용자 경험을 저해할 수 있다   
   - 접근성 보장: 시각 장애가 있는 사용자뿐만 아니라 모든 사용자가 콘텐츠를 안전하게 접근할 수 있도록 보장   
2. **제공 방법**    
   - 깜박임 빈도 제한     
     - 콘텐츠가 깜박이거나 번쩍여야 할 경우, 깜박임의 빈도를 초당 3회 이하로 제한합니다. 이는 발작을 유발할 수 있는 위험을 줄여줌.      
   - 대체 콘텐츠 제공     
     - 깜박이거나 번쩍이는 콘텐츠 대신, 정적인 이미지나 영상으로 대체할 수 있는 방법을 제공.   
   - 깜박임 완화 옵션 제공        
     - 사용자 설정에서 깜박임을 완화하거나 비활성화할 수 있는 옵션을 제공.    
   - 콘텐츠 검토        
     - 콘텐츠가 광과민성 발작을 유발할 가능성이 있는지 확인하고, 이에 따라 콘텐츠를 수정하거나 제거.    

```sh
<!-- 네이티브 앱 예시 (Android) - 깜박임을 피하는 애니메이션 설정 -->
// xml code
<ImageView
    android:id="@+id/flashingImage"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:src="@drawable/static_image" /> <!-- 깜박이는 이미지 대신 정적 이미지 사용 -->

// java code
Animation animation = new AlphaAnimation(0.0f, 1.0f);// 깜박임을 제한하는 애니메이션 설정
animation.setDuration(1000); // 1초간의 깜박임 주기
animation.setRepeatCount(Animation.INFINITE);
animation.setRepeatMode(Animation.REVERSE);

if (animation.getDuration() > 333) { // 깜박임 빈도가 초당 3회 이하인지 확인
    imageView.startAnimation(animation);
} else {
    // 깜박임이 과도한 경우 애니메이션을 사용하지 않음
    imageView.setImageResource(R.drawable.static_image);
}


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 깜박임 대신 CSS 애니메이션 사용 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>깜박임 제한 예시</title>
    <style>
        .fading {
            animation: fadeInOut 3s infinite;
        }

        @keyframes fadeInOut {
            0%, 100% {
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
        }
    </style>
</head>
<body>
    <div class="fading">이 텍스트는 깜박이지 않고 천천히 사라집니다.</div>
</body>
</html>


<!-- 잘못된 예시 (네이티브) - 깜박임 빈도가 초당 3회 이상인 애니메이션이 사용됨. -->
// java code
Animation animation = new AlphaAnimation(0.0f, 1.0f);
animation.setDuration(100); // 0.1초간의 깜박임 주기 - 초당 10회 이상 깜박임
animation.setRepeatCount(Animation.INFINITE);
imageView.startAnimation(animation);


<!-- 잘못된 예시 (하이브리드) - 깜박임 빈도가 높은 애니메이션이 포함되어 있어 사용자가 불편을 느낄 수 있음. -->
<style>
    @keyframes blink {
        0%, 100% {
            opacity: 0;
        }
        50% {
            opacity: 1;
        }
    }

    .blinking {
        animation: blink 0.5s infinite; /* 초당 2회 깜박임 */
    }
</style>
<div class="blinking">이 텍스트는 깜박입니다.</div>


<!-- 올바른 예시 (네이티브) - 깜박임 대신 정적인 이미지를 사용하거나, 깜박임 빈도가 초당 3회 이하인 애니메이션을 사용 -->
Animation animation = new AlphaAnimation(0.0f, 1.0f);
animation.setDuration(1000); // 1초간의 깜박임 주기 - 초당 1회 깜박임
animation.setRepeatCount(Animation.INFINITE);
imageView.startAnimation(animation);


<!-- 올바른 예시 (하이브리드) - 깜박임 대신 천천히 사라지는 애니메이션을 사용하거나, 깜박임 빈도가 낮은 애니메이션을 적용 -->
<style>
    @keyframes fadeInOut {
        0%, 100% {
            opacity: 0;
        }
        50% {
            opacity: 1;
        }
    }

    .fading {
        animation: fadeInOut 3s infinite; /* 초당 0.33회 깜박임 */
    }
</style>

<div class="fading">이 텍스트는 천천히 사라집니다.</div>
```

**검수 방법**
- 깜박임 빈도 확인: 모든 애니메이션이 초당 3회 이하로 깜박이는지 확인합니다. 과도한 깜박임이 없는지 검토하였는가?     
- 대체 콘텐츠 확인: 깜박임을 사용하지 않고도 동일한 정보를 전달할 수 있는 대체 콘텐츠가 있는지 확인하였는가?     
- 사용자 테스트: 실제 사용자들이 깜박임으로 인해 불편함을 느끼지 않는지 테스트하였는가?     
- 접근성 검사 도구 사용: 다양한 접근성 검사 도구를 사용하여 깜박임과 관련된 잠재적인 문제를 식별하고 해결하였는가?     


#### 7.4 (자동재생 금지) 자동으로 재생되는 배경음을 사용하지 않아야 한다.    
> 자동으로 재생되는 배경음악이나 소리는 사용자가 원치 않는 상황에서 재생될 수 있어 불편함을 초래할 수 있으며, 특히 보조 기술을 사용하는 사용자들에게는 중요한 정보를 방해할 수 있다. 따라서, 배경음악이나 소리가 자동으로 재생되지 않도록 해야 하며, 재생을 원할 경우 사용자가 직접 제어할 수 있도록 해야 한다.        
WCAG 2.2 Guidelines : [1.4.2 오디오 제어(Audio Control)](https://www.w3.org/TR/WCAG22/#audio-control){: target="_blank"}

1. **필요성**    
   - 사용자 제어 권한 보장: 사용자가 앱에서 소리를 듣는 시점과 방법을 스스로 결정할 수 있어야 합니다. 자동으로 재생되는 소리는 사용자의 경험을 방해하고, 특히 공공장소나 조용한 환경에서는 더욱 큰 불편을 초래할 수 있다   
   - 보조 기술 사용 방해: 자동 재생되는 소리는 스크린 리더와 같은 보조 기술의 동작을 방해하여, 시각 장애 사용자들이 앱을 사용하는 데 어려움을 겪게 할 수 있다   
   - 배터리 및 데이터 사용 절약: 불필요한 자동 재생은 배터리와 데이터 사용량을 증가시킬 수 있습니다. 사용자가 원치 않는 상황에서 재생을 막음으로써 자원을 절약할 수 있다   
2. **제공 방법**    
   - 자동 재생 비활성화     
     - 앱이 시작되거나 특정 화면에 진입할 때, 배경음악이나 소리를 자동으로 재생하지 않도록 설정.      
   - 사용자 제어 옵션 제공     
     - 배경음악이나 소리를 듣고 싶다면, 사용자가 직접 재생 버튼을 눌러 선택적으로 재생할 수 있도록 제어 옵션을 제공.   
   - 자동 재생을 방지하는 설정 제공        
     - 앱 설정에서 모든 소리 또는 음악의 자동 재생을 완전히 비활성화할 수 있는 옵션을 제공.    

```sh
<!-- 네이티브 앱 예시 (Android) - 배경음악을 자동으로 재생하지 않도록 설정 -->
// java code
MediaPlayer mediaPlayer = MediaPlayer.create(this, R.raw.background_music);// 음악 재생 컨트롤
Button playButton = findViewById(R.id.playButton);

playButton.setOnClickListener(v -> {
    if (!mediaPlayer.isPlaying()) {
        mediaPlayer.start();
    }
});


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 배경음악 재생을 사용자 선택으로 설정 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Audio Control Example</title>
</head>
<body>
    <button id="playButton">음악 재생</button>
    <audio id="backgroundAudio" src="background_music.mp3"></audio>

    <script>
        const playButton = document.getElementById('playButton');
        const backgroundAudio = document.getElementById('backgroundAudio');

        playButton.addEventListener('click', () => {
            if (backgroundAudio.paused) {
                backgroundAudio.play();
            }
        });
    </script>
</body>
</html>


<!-- 잘못된 예시 (네이티브) - 앱이 시작되면 사용자가 원하지 않는 상황에서도 자동으로 배경음악이 재생됨 -->
// java code
MediaPlayer mediaPlayer = MediaPlayer.create(this, R.raw.background_music);// 앱이 시작되면 자동으로 배경음악 재생
mediaPlayer.start(); // 사용자의 동의 없이 자동 재생


<!-- 잘못된 예시 (하이브리드) - 페이지가 로드되자마자 자동으로 소리가 재생되며, 사용자가 이를 제어할 방법이 제공되지 않음. -->
<audio id="backgroundAudio" src="background_music.mp3" autoplay></audio>


<!-- 올바른 예시 (네이티브) - 배경음악 재생은 사용자의 클릭으로만 시작되며, 자동으로 재생되지 않음 -->
MediaPlayer mediaPlayer = MediaPlayer.create(this, R.raw.background_music);
Button playButton = findViewById(R.id.playButton);

playButton.setOnClickListener(v -> {
    if (!mediaPlayer.isPlaying()) {
        mediaPlayer.start();
    }
});


<!-- 올바른 예시 (하이브리드) - 사용자가 클릭 후 일어날 이벤트에 대해 명확히 이해하고 동의하도록 피드백을 제공한 후 화면을 전환 -->
<button id="playButton">음악 재생</button>
<audio id="backgroundAudio" src="background_music.mp3"></audio>
```

**검수 방법**
- 자동 재생 여부 확인: 앱이 실행되거나 특정 페이지로 이동할 때 소리가 자동으로 재생되지 않는지 확인하였는가?     
- 사용자 제어 테스트: 사용자가 직접 소리 재생을 제어할 수 있는지 확인합니다. 재생 버튼이 명확히 표시되고 기능이 올바르게 작동하는지 테스트하였는가?     
- 접근성 검사 도구 사용: Google Accessibility Scanner와 같은 도구를 사용하여 자동 재생과 관련된 접근성 문제를 점검하였는가?     


#### 7.5 (예측가능성) 사용자가 의도하지 않는 화면 전환이나 이벤트 등이 실행되는 경우 사용자가 이해할 수 있는 방법으로 제공되어야 한다.    
> 사용자 인터페이스(UI)에서 예상치 못한 화면 전환이나 이벤트는 사용자에게 혼란을 줄 수 있다. 이러한 상황이 발생할 경우, 사용자는 이 동작의 이유와 결과를 이해할 수 있어야 하며, 예측 가능한 방식으로 제공되어야 한다.    
예측 가능한 UI는 특히 시각, 청각, 인지 장애를 가진 사용자들에게 매우 중요하다.      
WCAG 2.2 Guidelines : [3.2.1 온포커스(On Focus)](https://www.w3.org/TR/WCAG22/#on-focus){: target="_blank"}
WCAG 2.2 Guidelines : [3.2.2 온입력(On Input)](https://www.w3.org/TR/WCAG22/#on-input){: target="_blank"}

1. **필요성**    
   - 사용자 경험 향상: 예상치 못한 화면 전환이나 이벤트는 사용자에게 혼란을 주고, 앱 사용을 어렵게 만듭니다. 예측 가능한 UI는 사용자가 앱을 더 쉽게 이해하고 사용할 수 있게 해준다   
   - 오류 방지: 예측할 수 없는 UI 동작은 사용자로 하여금 실수를 유발할 수 있으며, 이로 인해 중요한 정보를 놓치거나 잘못된 동작을 수행할 수 있다   
   - 접근성 보장: 예측 가능한 동작은 접근성을 높여, 특히 시각, 청각, 인지 장애를 가진 사용자들이 앱을 원활하게 사용할 수 있도록 돕는다   
2. **제공 방법**    
   - 사용자 피드백 제공     
     - 예상치 못한 화면 전환이나 이벤트가 발생할 경우, 사용자에게 왜 이 변화가 발생했는지 명확하게 설명하는 피드백을 제공합니다. 예를 들어, 화면이 새로고침되거나 페이지가 자동으로 이동될 때 알림 메시지를 표시.      
   - 명확한 경고 메시지 제공     
     - 사용자 동작이 중요한 변화를 일으킬 수 있는 경우(예: 데이터 제출, 삭제 등), 명확한 경고 메시지를 제공하여 사용자가 확인하도록 한다.   
   - 화면 전환에 대한 시각적 피드백 제공        
     - 화면 전환이 일어날 때, 애니메이션이나 화면 전환 효과를 통해 사용자에게 이를 명확히 알려준다.    
   - 자동화된 동작 최소화        
     - 자동으로 화면 전환이 이루어지지 않도록 하며, 필요한 경우 사용자가 수동으로 제어할 수 있는 옵션을 제공.    

```sh
<!-- 네이티브 앱 예시 (Android) - 예상치 못한 화면 전환 시 피드백 제공 -->
// java code
Button deleteButton = findViewById(R.id.deleteButton);// 예를 들어, 사용자가 데이터 삭제 버튼을 클릭했을 때
deleteButton.setOnClickListener(v -> {
    new AlertDialog.Builder(this)
        .setTitle("데이터 삭제")
        .setMessage("이 작업은 되돌릴 수 없습니다. 계속하시겠습니까?")
        .setPositiveButton("예", (dialog, which) -> {
            // 데이터를 삭제하고 화면을 전환
            deleteData();
            startActivity(new Intent(this, MainActivity.class));
        })
        .setNegativeButton("아니요", null)
        .show();
});


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 예상치 못한 페이지 전환에 대한 피드백 제공 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Predictability Example</title>
</head>
<body>
    <button id="deleteButton">데이터 삭제</button>

    <script>
        document.getElementById('deleteButton').addEventListener('click', function() {
            const userConfirmed = confirm("이 작업은 되돌릴 수 없습니다. 계속하시겠습니까?");
            if (userConfirmed) {
                // 데이터 삭제 후 페이지 이동
                deleteData(); // 가상의 데이터 삭제 함수
                window.location.href = 'main.html';
            }
        });

        function deleteData() {
            // 데이터 삭제 로직
        }
    </script>
</body>
</html>


<!-- 잘못된 예시 (네이티브) - 사용자가 버튼을 클릭하자마자 별다른 경고 없이 화면이 전환되어 사용자가 혼란스러워 함 -->
// java code
Button deleteButton = findViewById(R.id.deleteButton);
deleteButton.setOnClickListener(v -> {
    // 사용자의 동의 없이 데이터를 삭제하고 화면 전환
    deleteData();
    startActivity(new Intent(this, MainActivity.class));
});


<!-- 잘못된 예시 (하이브리드) - 페이지가 자동으로 리로드되거나 이동되어 사용자가 당황스러워 함 -->
<!-- 하이브리드 앱 - 잘못된 예시 -->
<script>
    document.getElementById('deleteButton').addEventListener('click', function() {
        // 사용자 확인 없이 페이지 이동
        deleteData();
        window.location.href = 'main.html';
    });
</script>


<!-- 올바른 예시 (네이티브) - 화면 전환 전 사용자가 예상할 수 있도록 명확한 경고 메시지를 제공하여 사용자가 확인할 수 있도록 한다 -->
Button deleteButton = findViewById(R.id.deleteButton);

deleteButton.setOnClickListener(v -> {
    new AlertDialog.Builder(this)
        .setTitle("데이터 삭제")
        .setMessage("이 작업은 되돌릴 수 없습니다. 계속하시겠습니까?")
        .setPositiveButton("예", (dialog, which) -> {
            deleteData();
            startActivity(new Intent(this, MainActivity.class));
        })
        .setNegativeButton("아니요", null)
        .show();
});

<!-- 올바른 예시 (하이브리드) - 사용자가 클릭 후 일어날 이벤트에 대해 명확히 이해하고 동의하도록 피드백을 제공한 후 화면을 전환 -->
<script>
    document.getElementById('deleteButton').addEventListener('click', function() {
        const userConfirmed = confirm("이 작업은 되돌릴 수 없습니다. 계속하시겠습니까?");
        if (userConfirmed) {
            deleteData();
            window.location.href = 'main.html';
        }
    });
</script>
```

**검수 방법**
- 예측 가능한 동작 확인: 모든 화면 전환 및 이벤트가 사용자에게 예측 가능하게 제공되는지 확인합니다. 사용자가 예상치 못한 변화에 대비할 수 있는지 검토하였는가?     
- 사용자 피드백 테스트: 사용자 동작에 따라 제공되는 피드백이 명확하고 이해하기 쉬운지 테스트하였는가?     
- 접근성 검사 도구 사용: Google Accessibility Scanner와 같은 도구를 사용하여 예측 가능성과 관련된 접근성 문제를 점검하였는가?     


### 8. 견고성 (Robust)
#### 8.1 (폰트 관련 기능의 활용) 텍스트 콘텐츠는 운영체제에서 제공하는 폰트 관련 기능을 활용할 수 있는 방법을 제공해야 한다.    
> 모바일 운영체제는 사용자가 텍스트 크기, 글꼴, 대비 등을 조정할 수 있는 기능을 제공하며, 이러한 기능을 앱 내에서 지원함으로써 사용자가 자신에게 적합한 텍스트 환경을 설정할 수 있게 해야 한다.    
이를 통해 접근성을 높이고, 다양한 사용자들이 앱을 편리하게 사용할 수 있도록 도와준다.    
일관성 있는 UI는 사용자가 각 요소의 위치와 동작을 예측할 수 있게 해주며, 특히 장애를 가진 사용자들에게 더욱 중요한 역할을 한다.    
WCAG 2.2 Guidelines : [1.4.3 명도 대비(Contrast)](https://www.w3.org/TR/WCAG22/#contrast-minimum){: target="_blank"}
WCAG 2.2 Guidelines : [1.4.4 텍스트 크기 조정(Resize Text)](https://www.w3.org/TR/WCAG22/#resize-text){: target="_blank"}

1. **필요성**    
   - 사용자 맞춤화 보장: 각 사용자는 텍스트를 읽는 데 필요한 요구사항이 다릅니다. 운영체제의 폰트 설정을 따르는 앱은 이러한 개인 맞춤화를 지원   
   - 가독성 향상: 텍스트 크기나 대비를 조절할 수 있으면 사용자는 자신의 시력에 맞게 텍스트를 쉽게 읽을 수 있다   
   - 접근성 보장: 시각 장애나 저시력을 가진 사용자가 텍스트를 더 쉽게 읽을 수 있도록 폰트 관련 기능을 지원함으로써 접근성을 높일 수 있다   
2. **제공 방법**    
   - 운영체제 폰트 설정 준수     
     - 앱에서 텍스트 콘텐츠는 운영체제의 텍스트 크기, 글꼴, 그리고 대비 설정을 자동으로 따라야 합니다. 사용자가 설정한 텍스트 크기와 스타일이 앱 내에서도 동일하게 적용되도록 한다.      
   - 동적 텍스트 크기 지원     
     - 사용자가 텍스트 크기를 조절할 수 있는 기능을 제공합니다. 예를 들어, Android의 sp 단위나 iOS의 Dynamic Type을 사용하여 텍스트 크기를 설정.   
   - 사용자 정의 설정 제공        
     - 앱 내에서 추가적인 폰트 크기 조절 기능이나 고대비 모드를 제공하여, 사용자가 텍스트를 더 쉽게 읽을 수 있도록 한다.    

```sh
<!-- 네이티브 앱 예시 (Android) - 운영체제의 폰트 설정을 따르는 텍스트 -->
// xml code
<TextView
    android:id="@+id/sampleText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="여기에 텍스트를 입력하세요"
    android:textSize="18sp" <!-- 운영체제의 텍스트 크기 설정에 따라 크기가 조정됨 -->
    android:fontFamily="sans-serif" />


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - 운영체제의 폰트 설정을 따르는 텍스트 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Font Settings Example</title>
    <style>
        body {
            font-size: calc(1em + 1vw); /* 텍스트 크기를 반응형으로 설정하여 운영체제 설정을 따름 */
            font-family: system-ui, sans-serif; /* 시스템 폰트를 사용하여 운영체제의 폰트 설정을 따름 */
        }
    </style>
</head>
<body>
    <p>운영체제의 폰트 설정을 따르는 텍스트 예시입니다.</p>
</body>
</html>



<!-- 잘못된 예시 (네이티브) - 텍스트 크기를 고정값으로 설정하여 운영체제의 텍스트 크기 설정을 따르지 않음 -->
// xml code
<TextView
    android:id="@+id/sampleText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="여기에 텍스트를 입력하세요"
    android:textSize="14dp" <!-- 고정된 텍스트 크기 -->
    android:fontFamily="sans-serif" />


<!-- 잘못된 예시 (하이브리드) - 폰트 크기가 고정되어 있으며, 사용자가 텍스트 크기를 조절할 수 있는 옵션이 제공되지 않음 -->
<style>
    body {
        font-size: 14px; /* 고정된 텍스트 크기 */
        font-family: Arial, sans-serif; /* 시스템 폰트가 아닌 고정 폰트 사용 */
    }
</style>
<p>이 텍스트는 고정된 크기와 폰트로 설정되어 있습니다.</p>


<!-- 올바른 예시 (네이티브) - 운영체제의 텍스트 크기 설정을 따르고, 폰트 크기가 조정 가능하도록 설정함 -->
<TextView
    android:id="@+id/sampleText"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="여기에 텍스트를 입력하세요"
    android:textSize="18sp" <!-- 운영체제의 설정을 따름 -->
    android:fontFamily="sans-serif" />


<!-- 올바른 예시 (하이브리드) - 반응형 텍스트 크기와 시스템 폰트를 사용하여 운영체제의 폰트 설정을 따름 -->
<style>
    body {
        font-size: calc(1em + 1vw); /* 반응형 텍스트 크기 */
        font-family: system-ui, sans-serif; /* 시스템 폰트 사용 */
    }
</style>
<p>운영체제의 폰트 설정을 따르는 텍스트 예시입니다.</p>
```

**검수 방법**
- 운영체제 설정 확인: 운영체제의 텍스트 크기나 폰트 설정을 변경한 후, 앱의 텍스트가 이에 따라 적절히 조정되는지 확인하였는가?     
- 가독성 테스트: 텍스트가 모든 사용자에게 가독성이 높고, 다양한 텍스트 크기에서 읽기 쉽게 표시되는지 테스트하였는가?     
- 접근성 검사 도구 사용: Google Accessibility Scanner와 같은 도구를 사용하여 텍스트 관련 접근성 문제를 점검하였는가?     


#### 8.2 (보조 기술과의 호환성) 사용자 인터페이스 컴포넌트는 보조 기술을 이용하여 사용할 수 있도록 해야 한다.    
> 보조 기술은 시각, 청각, 신체적 장애를 가진 사용자들이 컴퓨터와 모바일 기기를 사용할 수 있도록 도와주는 장치나 소프트웨어이며, UI 컴포넌트가 이러한 보조 기술과 호환되도록 설계되면, 모든 사용자가 앱을 접근 가능하게 이용할 수 있다. 이 호환성을 보장하기 위해 UI 컴포넌트에는 적절한 접근성 속성이 적용되어야 한다.    
WCAG 2.2 Guidelines : [2.1.1 키보드(Keyboard)](https://www.w3.org/TR/WCAG22/#keyboard){: target="_blank"}
WCAG 2.2 Guidelines : [4.1.2 이름, 역할, 값(Name, Role, Value)](https://www.w3.org/TR/WCAG22/#name-role-value){: target="_blank"}

1. **필요성**    
   - 접근성 보장: 시각, 청각, 신체적 장애를 가진 사용자들이 보조 기술을 통해 앱을 사용할 수 있도록 보장   
   - 법적 요구사항 준수: 많은 국가에서 웹 및 모바일 앱의 접근성을 보장하는 법적 요구사항이 있으며, 이를 준수함으로써 법적 문제를 피할 수 있다   
   - 포용적 사용자 경험 제공: 보조 기술을 사용하는 사용자들도 비장애인 사용자와 동일하게 앱의 모든 기능을 활용할 수 있어야 한다   
2. **제공 방법**    
   - 적절한 접근성 속성 사용     
     - UI 컴포넌트에 aria 속성, role 속성, label 등을 사용하여 보조 기술이 각 요소를 올바르게 인식할 수 있도록 한다.      
   - 포커스 관리     
     - 모든 인터랙티브 요소는 포커스를 받을 수 있어야 하며, 포커스가 논리적인 순서로 이동하도록 설정. 사용자가 키보드나 보조 기술을 통해 앱을 탐색할 수 있도록 한다.   
   - 텍스트 대체 제공        
     - 이미지, 버튼, 링크 등의 비텍스트 요소에 대해 스크린 리더가 읽을 수 있는 텍스트 대체(alt 텍스트, aria-label 등)를 제공.    
   - 동작 피드백 제공        
     - 사용자가 UI 컴포넌트와 상호작용할 때, 시각적 피드백뿐만 아니라 보조 기술을 통한 피드백도 제공하여 현재 상태를 명확하게 전달.    
   - 보조 기술과의 테스트        
     - 앱이 주요 보조 기술(스크린 리더, 음성 인식 소프트웨어 등)과 호환되는지 정기적으로 테스트하고, 발견된 문제를 수정.    

```sh
<!-- 네이티브 앱 예시 (Android) - 보조 기술을 위한 접근성 속성 설정 -->
// xml code
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="제출"
    android:contentDescription="폼 제출 버튼" <!-- 스크린 리더에 의해 읽혀질 텍스트 -->
    android:importantForAccessibility="yes" />
// java code
Button submitButton = findViewById(R.id.submitButton);// 특정 동작에 대한 피드백 제공
submitButton.setOnClickListener(v -> {
    submitButton.setContentDescription("폼이 제출되었습니다.");// 버튼 클릭 시 스크린 리더에 읽힐 메시지 설정
    submitForm();// 폼 제출 로직 수행
});


<!-- 하이브리드 앱 예시 (HTML/JavaScript) - ARIA 속성을 사용하여 보조 기술 호환성 보장 -->
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Accessible Button Example</title>
</head>
<body>
    <button id="submitButton" aria-label="폼 제출">제출</button>

    <script>
        document.getElementById('submitButton').addEventListener('click', function() {
            this.setAttribute('aria-label', '폼이 제출되었습니다');// 폼 제출 후 상태를 업데이트하여 스크린 리더에 읽히도록 함
        });
    </script>
</body>
</html>



<!-- 잘못된 예시 (네이티브) - 버튼에 접근성 속성이 없어서 스크린 리더가 버튼의 역할을 알 수 없음 -->
// xml code
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="제출" />

<!-- 잘못된 예시 (하이브리드) - 버튼에 aria-label이 없어서 스크린 리더가 버튼의 기능을 읽을 수 없음 -->
<button id="submitButton">제출</button>


<!-- 올바른 예시 (네이티브) - 버튼에 contentDescription을 설정하여 스크린 리더가 버튼의 역할을 읽을 수 있도록 함 -->
<Button
    android:id="@+id/submitButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="제출"
    android:contentDescription="폼 제출 버튼"
    android:importantForAccessibility="yes" />


<!-- 올바른 예시 (하이브리드) - aria-label 속성을 사용하여 보조 기술이 버튼의 기능을 인식할 수 있도록 설정 -->
<button id="submitButton" aria-label="폼 제출">제출</button>
```

**검수 방법**
- 보조 기술 테스트: 스크린 리더(예: Android의 TalkBack, iOS의 VoiceOver)나 음성 인식 소프트웨어를 사용하여 앱을 테스트하고, 모든 UI 컴포넌트가 올바르게 인식되고 작동하는지 확인하였는가?     
- 포커스 이동 테스트: 키보드나 보조 기술을 통해 포커스를 이동시키며, 모든 인터랙티브 요소가 논리적 순서로 탐색되는지 확인하였는가?     
- 접근성 검사 도구 사용: Google Accessibility Scanner, WAVE 등의 도구를 사용하여 UI 컴포넌트의 접근성 문제를 점검하고 수정하였는가?     


---


### 모바일 앱 접근성 요약 보고서
1. **대체 텍스트**   
   - 텍스트 아닌 콘텐츠는 대체 가능한 텍스트와 함께 제공되어야 한다.
2. **자막, 수화 등의 제공**   
   - 영상이나 음성 콘텐츠에는 동등한 내용의 자막, 원고 또는 수화가 제공되어야 한다.
3. **색에 무관한 인식**   
   - 화면에 표시되는 모든 정보는 색에 관계없이 인식될 수 있어야 한다.
4. **명도 대비**   
   - 화면에 표시되는 모든 사용자 인터페이스 컴포넌트와 텍스트는 전경색과 배경색이 구분될 수 있도록 제공되어야 한다.
5. **명확한 지시 사항** 
   - 지시 사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.
6. **알림 기능** 
   - 알림 정보는 화면 표시, 소리, 진동 등 다양한 방법으로 제공되어야 한다.
7. **초점** 
   - 의미나 기능을 갖는 모든 사용자 인터페이스 컴포넌트에는 초점(focus)이 적용되고, 초점은 논리적인 순서로 이동되어야 한다.
8. **누르기 동작 지원** 
   - 터치(touch) 기반 모바일 기기의 모든 컨트롤은 누르기 동작으로 제어할 수 있어야 한다.
9.  **응답 시간 조절** 
    - 시간 제한이 있는 콘텐츠는 응답 시간을 조절할 수 있어야 한다.
10. **정지 기능 제공** 
    - 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.
11. **컨트롤의 크기와 간격** 
    - 컨트롤은 충분한 크기와 간격으로 제공되어야 한다.
12. **입력 도움** 
    - 입력 서식 이용 시, 입력 오류를 방지하거나 정정할 수 있는 방법을 제공해야 한다.
13. **사용자 인터페이스의 일관성** 
    - 사용자 인터페이스 컴포넌트들은 일관성 있게 배치되어야 한다.
14. **깜박거림의 사용 제한** 
    - 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.
15. **자동재생 금지** 
    - 자동으로 재생되는 배경음을 사용하지 않아야 한다.
16. **예측가능성** 
    - 사용자가 의도하지 않는 화면 전환이나 이벤트 등이 실행되는 경우 사용자가 이해할 수 있는 방법으로 제공되어야 한다.
17. **폰트 관련 기능의 활용** 
    - 텍스트 콘텐츠는 운영체제에서 제공하는 폰트 관련 기능을 활용할 수 있는 방법을 제공해야 한다.
18. **보조 기술과의 호환성** 
    - 사용자 인터페이스 컴포넌트는 보조 기술을 이용하여 사용할 수 있도록 해야 한다.


### 참조
- [W3C Mobile Accessibility at W3C](https://www.w3.org/WAI/standards-guidelines/mobile/){: target="_blank"}
- [W3C Mobile Accessibility: How WCAG 2.0 and Other W3C/WAI Guidelines Apply to Mobile](https://www.w3.org/TR/mobile-accessibility-mapping/){: target="_blank"}
- [W3C First Public Working Draft](https://www.w3.org/news/2015/first-public-working-draft-performance-timeline-level-2/){: target="_blank"}
- [W3C User Agent Accessibility Guidelines (UAAG) 2.0](https://www.w3.org/TR/UAAG20/){: target="_blank"}
- [W3C Mobile Accessibility Examples from UAAG 2.0 Reference](https://www.w3.org/TR/IMPLEMENTING-UAAG20/mobile.html){: target="_blank"}
- [MDN Mobile accessibility checklist](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Mobile_accessibility_checklist){: target="_blank"}
- [보건복지부 블로그](https://blog.naver.com/prologue/PrologueList.naver?blogId=mohw2016){: target="_blank"}
