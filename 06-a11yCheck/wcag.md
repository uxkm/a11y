## 접근성 체크리스트

**웹 콘텐츠 접근성**
<!-- > 웹 콘텐츠를 시각 장애, 저시력 장애, 청각 장애, 지체 장애, 학습 장애, 지적 장애, 뇌병변 장애, 광과민성 증후 등 다양한 장애를 가진 사용자들이 쉽게 접근할 수 있도록 구축하는 방법에는 몇 가지 중요한 원칙과 지침이 있습니다. 이러한 원칙과 지침은 장애인 사용자가 비장애인 사용자와 동등하게 인터넷을 이용할 수 있도록 돕기 위해 설계되었으며,   
kwcag 2.1 과 2.2 기준 접근성은 크게 세 가지 주요 구성 요소로 나눌 수 있다.    
원칙 (Principles), 지침 (Guidelines), 검사 항목 (Requirements). 원칙은 4 가지 기본 원칙에 기초하며,    
kwcag 2.1 원칙을 구현하기 위해 13개의 지침을 따라야 하고, 각 지침의 준수 여부를 확인하기 위해 24개의 검사 항목을 마련해야 한다.    
 -->
> kwcag 2.2 원칙을 구현하기 위해 14개의 지침을 따라야 하고, 각 지침의 준수 여부를 확인하기 위해 33개의 검사 항목을 마련해야 한다.    
검사 항목은 구체적인 테스트 가능한 기준을 제공하여 웹사이트가 원칙 및 지침을 준수하고 있는지 확인하는 데 사용된다.   
**지능정보화기본법 시행규칙 일부개정령(안) 입법예고에 따라 '24.9.1부터 심사기준이 변경되며 이에따라 kwcag 2.2 기준으로 체크리스트를 제공한다.**

### 5. 인식의 용이성 (Perceivable)

#### 5.1.1. (적절한 대체 텍스트 제공) 텍스트 아닌 콘텐츠는 그 의미나 용도를 인식할 수 있도록 대체 텍스트를 제공해야 한다.
> 모든 이미지에는 대체 텍스트를 제공하여야 합니다. 이는 시각 장애인 사용자가 스크린 리더를 통해 이미지의 내용을 이해할 수 있도록 제공한다.   
WCAG 2.2 Guidelines : [1.1 Text Alternatives](https://www.w3.org/TR/WCAG21/#text-alternatives){: target="_blank"}   

<figure aria-hidden="true" style="text-align:center">
   <img src="https://uxkm.io/_assets/images/created_by02_gray.jpg" alt="마이크 앞에서 노래를 부르는 소년">
   <figcaption>이미지 출처 : uxkm.io</figcaption>
</figure>

```sh
예시)   
<img src="created_by02_gray.jpg" alt="마이크 앞에서 노래를 부르는 아이">
```

**검수 방법**
- 이미지가 적절한 대체 텍스트를 포함하고 있는가?   
- 스크린 리더로 테스트하여 텍스트가 올바르게 읽히는가?   

#### 5.2.1. (자막 제공) 멀티미디어 콘텐츠에는 자막, 대본 또는 수어를 제공해야 한다.
> 동영상 및 오디오 콘텐츠에는 자막, 대체 텍스트, 오디오 설명 등을 제공해야 한다.   
WCAG 2.2 Guidelines : [1.2 Time-based Media](https://www.w3.org/TR/WCAG21/#time-based-media){: target="_blank"}   

<video src="https://www.w3.org/WAI/content-assets/wcag-act-rules/test-assets/perspective-video/perspective-video.mp4" controls style="width:100%">
    <track src="https://www.w3.org/WAI/content-assets/wcag-act-rules/test-assets/perspective-video/perspective-caption.vtt" kind="captions" />
</video>

```sh
예시 1)
캡션이 있는 비디오.
<video src="/test-assets/perspective-video/perspective-video-with-captions.mp4" controls></video>
예시 2)
캡션을 포함 track 요소가 연결되어 있는 비디오.   
<video src="/test-assets/perspective-video/perspective-video.mp4" controls>
    <track src="/test-assets/perspective-video/perspective-caption.vtt" kind="captions" />
</video>
```

**검수 방법**
- 비디오 플레이어에서 자막이 정상적으로 표시되는가?    
- 오디오 설명이 포함된 경우 자막, 대본 또는 수어를 제공하는가?   

#### 5.3.1. (표의 구성) 표는 이해하기 쉽게 구성해야 한다.
> 표는 데이터를 체계적으로 정리하고, 쉽게 이해할 수 있도록 구성해야 한다.   
[W3C Accessible Tables](https://www.w3.org/WAI/tutorials/tables/){: target="_blank"}   

```sh
<!-- 잘못된 예시: caption 미제공, scope속성 미제공, aria-* 속성 미제공 -->
<table>
    <thead>
        <tr>
            <th>제품명</th>
            <th>가격</th>
            <th>수량</th>
            <th>총 가격</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>사과</td>
            <td>1000원</td>
            <td>5</td>
            <td>5000원</td>
        </tr>
        ... 중략
    </tbody>
</table>

<!-- 올바른 예시: caption제공, scope속성 제공, aria-* 속성 연결 -->
<table aria-describedby="tableDescription">
    <caption id="tableDescription">다양한 제품의 가격, 수량 및 총 가격을 나타내는 표입니다.</caption>
    <thead>
        <tr>
            <th scope="col">제품명</th>
            <th scope="col">가격</th>
            <th scope="col">수량</th>
            <th scope="col">총 가격</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>사과</td>
            <td>1000원</td>
            <td>5</td>
            <td>5000원</td>
        </tr>
        ... 중략
    </tbody>
</table>
```

**검수 방법**
- 제목이 표의 내용을 잘 설명하고 있는지 확인하였는가?    
- 표의 헤더 셀과 테이터 셀의 관계(scope 속성) 정의가 되어있는가?    
- 캡션과 ARIA 속성이 적절하게 사용되었는지 확인하였는가?    

#### 5.3.2. (콘텐츠의 선형구조) 콘텐츠는 논리적인 순서로 제공해야 한다.
> 콘텐츠는 논리적인 순서로 제공되어야 한다.    
모든 사용자가 콘텐츠를 쉽게 탐색하고 이해할 수 있게 한다.    
논리적인 순서는 시각적으로나 코드 구조적으로나 일관되어야 한다.   
WCAG 2.2 Guidelines : [WCAG 2.2 - 1.3.2 Meaningful Sequence](https://www.w3.org/TR/WCAG22/#meaningful-sequence){: target="_blank"}   


```sh
<!-- 잘못된 예시 -->
<p>이 사이트는 다양한 정보를 제공합니다.</p>
<nav>
    <a href="#section1">섹션 1</a>
    <a href="#section2">섹션 2</a>
</nav>
<h2>섹션 1</h2>
<p>여기는 섹션 1의 내용입니다.</p>
<h1>사이트 제목</h1>
<h2>섹션 2</h2>
<p>여기는 섹션 2의 내용입니다.</p>

<!-- 올바른 예시 -->
<h1>사이트 제목</h1>
<p>이 사이트는 다양한 정보를 제공합니다.</p>
<nav>
    <a href="#section1">섹션 1</a>
    <a href="#section2">섹션 2</a>
</nav>
<h2>섹션 1</h2>
<p>여기는 섹션 1의 내용입니다.</p>
<h2>섹션 2</h2>
<p>여기는 섹션 2의 내용입니다.</p>
```

**검수 방법**
- 논리적인 순서로 배치되었는지 확인하였는가?    
- 스크린 리더(센스리더, JAWS, NVDA 등) 테스트를 통하여 확인하였는가?    


#### 5.3.3. (명확한 지시사항 제공) 지시사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.
> 웹 콘텐츠나 사용자 인터페이스를 설계할 때, 지시사항이나 안내는 특정 감각적 특성(모양, 크기, 위치, 방향, 색, 소리 등)에 의존하지 않고 명확히 전달되어야 한다.    
즉, 색상에만 의존하여 정보를 전달하는 것이 아니라 텍스트나 다른 시각적 단서도 함께 제공해야 한다.    
WCAG 2.2 Guidelines : [WCAG 2.2 - 1.3.3 Sensory Characteristics](https://www.w3.org/TR/WCAG22/#sensory-characteristics){: target="_blank"}


```sh
<!-- 잘못된 예시 -->
<p>녹색 버튼을 클릭하세요.</p>
<button style="background-color: green;">제출</button>

<!-- 올바른 예시 -->
<p>제출 버튼을 클릭하세요.</p>
<button style="background-color: green;">제출</button>
```

**검수 방법**
- 지시 사항이 색상, 위치, 모양 등에 의존하지 않고 텍스트로 명확하게 제공되는지 확인하였는가?    
- 지시 사항이 색상이나 소리 이외에도 텍스트로 제공되었는지 확인하였는가?     
- 지시 사항이 일관되게 사용되고 있는지, 모호한 부분이 없는지 검토하였는가?     
- Axe, WAVE 등의 접근성 검사 도구를 사용하여 지시 사항의 명확성을 점검하였는가?     
- 다양한 사용자(시각, 청각, 인지 장애를 가진 사용자 포함)와 상황에서 지시 사항이 명확하게 이해되는지 테스트하였는가?     
    


#### 5.4.1. (색에 무관한 콘텐츠 인식) 콘텐츠는 색에 관계없이 인식될 수 있어야 한다.
> 콘텐츠는 색에 관계없이 인식될 수 있어야 한다. 이는 색상에 의존하는 정보 전달을 피해야 하며, 색상만으로는 정보를 전달하지 않도록 한다.   
WCAG 2.2 Guidelines : [1.4.1 Use of Color](https://www.w3.org/TR/WCAG22/#use-of-color){: target="_blank"}   

<p>이 문장에서 <strong style="color: red;">빨간색 텍스트</strong>는 중요한 정보입니다.</p>
<p>이 문장에서 <strong style="color: red; font-weight: bold; text-decoration: underline;">중요한 정보</strong>가 포함되어 있습니다.</p>

```sh
<!-- 잘못된 예시: 색상만으로 중요한 정보를 전달 -->
<p>이 문장에서 <strong style="color: red;">빨간색 텍스트</strong>는 중요한 정보입니다.</p>

<!-- 올바른 예시: 색상 외에 굵은 글씨체와 밑줄 사용 -->
<p>이 문장에서 <strong style="color: red; font-weight: bold; text-decoration: underline;">중요한 정보</strong>가 포함되어 있습니다.</p>
```

**검수 방법**
- 색상만으로 정보를 전달하지 않았는가?     
- 흑백 모드나 명도 대비를 낮춘 상태에서 정보를 인식할 수 있는지 확인하였는가?     
- 접근성 검사 도구(예: Axe, WAVE)를 사용하여 색 정보 사용 문제를 자동으로 검출하였는가?   


#### 5.4.2. (자동 재생 금지) 자동으로 소리가 재생되지 않아야 한다.
> 웹 페이지에서 자동으로 소리(동영상, 오디오, 음성, 배경 음악 등 콘텐츠가 제공하는 모든 소리)가 재생됨으로 인해 화면낭독프로그램 사용자가 콘텐츠를 인식하고 사용하는 데 방해받지 않아야 한다.    
단, 3초 미만의 소리는 허용한다. 3초 이상 재생되는 소리는 제어할 수 있는 수단(멈춤, 일시정지, 음량 조절 등)을 함께 제공해야 한다. 참고로, 플랫폼은 콘텐츠가 제공하는 배경음의 음량을 조절하더라도 화면낭독프로그램의 음량에는 영향을 주지 않아야 한다.   
WCAG 2.2 Guidelines : [2.2.2 Pause, Stop, Hide](https://www.w3.org/TR/WCAG22/#pause-stop-hide){: target="_blank"}   

```sh
<!-- 예시: 자동 재생 금지 -->
<video id="myVideo" width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

<script>
    document.addEventListener('DOMContentLoaded', (event) => {
        const video = document.getElementById('myVideo');
        video.autoplay = false;
    });
</script>
```

**검수 방법**
- 페이지에 포함된 모든 오디오 및 비디오 요소를 확인하였는가?     
- 페이지가 로드될 때 오디오나 비디오가 자동으로 재생되지 않는지 확인하였는가?   
- 코드를 검토하여 autoplay 속성이 'false'로 설정, 제거되었는가?   

#### 5.4.3. (텍스트 콘텐츠의 명도 대비) 텍스트 콘텐츠와 배경 간의 명도대비는 4.5 대 1 이상이어야 한다.
> 페이지에서 보이는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 충분한 대비를 제공하여, 저시력장애인, 색각장애인, 고령자 등도 콘텐츠를 인식할 수 있도록 제공해야 한다.    
다만, 로고, 장식목적의 콘텐츠, 마우스나 키보드를 활용하여 초점을 받았을 때 명도 대비가 커지는 콘텐츠 등은 예외로 한다.    
**중요 : 작업 시 많이 오류를 범하는 항목**
WCAG 2.2 Guidelines : [1.4.3 Contrast (Minimum)](https://www.w3.org/TR/WCAG22/#pause-stop-hide){: target="_blank"}   

```sh
<!-- 잘못된 예시 -->
<style>
    .low-contrast {
        color: #777; /* 회색 텍스트 */
        background-color: #eee; /* 연한 회색 배경 */
    }
</style>
<div class="low-contrast">
    명도 대비가 충분하지 않습니다.
</div>

<!-- 올바른 예시 -->
<style>
    .high-contrast {
        color: #000; /* 검은색 텍스트 */
        background-color: #fff; /* 흰색 배경 */
    }
</style>
<div class="high-contrast">
    명도 대비가 충분합니다.
</div>
```

**검수 방법**
- 콘텐츠의 명도 대비: 웹 페이지가 제공하는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 명도 대비는 4.5:1 이상이어야 한다. 준수하였는가?     
- 폰트 크기에 따른 명도 대비: 텍스트 콘텐츠를 구성하고 있는 텍스트 폰트를 18pt 이상 또는 14pt 이상의 굵은 폰트를 사용하는 경우, 명도 대비를 3:1까지 낮출 수 있다. 준수하였는가?   
- 화면 확대가 가능한 콘텐츠: 화면 확대가 가능하도록 구현한 텍스트 콘텐츠(텍스트 및 텍스트 이미지)의 명도 대비는 3:1까지 낮출 수 있다. 준수하였는가?   


#### 5.4.4. (콘텐츠 간의 구분) 이웃한 콘텐츠는 구별될 수 있어야 한다.
> 웹 페이지 내에서 서로 인접한 콘텐츠 블록들이 명확하게 구분되어 사용자가 쉽게 이해하고 탐색할 수 있어야 한다는 의미입니다.    
이는 사용자가 더 쉽게 콘텐츠를 이해하고, 탐색하며, 상호작용할 수 있도록 돕습니다.    
WCAG 2.2 Guidelines : [1.4.8 Visual Presentation](https://www.w3.org/TR/WCAG22/#visual-presentation){: target="_blank"}   

```sh
<!-- 잘못된 예시 : 이웃한 콘텐츠가 구별되지 않아 사용자가 정보를 쉽게 찾기 어려움. 
예) 충분한 여백이나 구분선이 없는 경우가 이에 해당 -->
<style>
    .content {
        padding: 10px;
    }
</style>
<div class="content">첫 번째 콘텐츠</div>
<div class="content">두 번째 콘텐츠</div>

<!-- 올바른 예시 -->
<style>
    .content {
        padding: 10px;
        margin-bottom: 20px;
        border: 1px solid #ddd;
        background-color: #f9f9f9;
    }
</style>
<div class="content">첫 번째 콘텐츠</div>
<div class="content">두 번째 콘텐츠</div>
```

**검수 방법**
- 시각적 구분 확인: 콘텐츠 간에 충분한 여백, 구분선, 또는 배경색이 사용되어 이웃한 콘텐츠가 명확히 구별되는지 확인하였는가?   
- 콘텐츠의 가독성 확인: 텍스트와 배경의 대비가 충분하여 가독성이 높은지 확인였는가?   


### 운용의 용이성 (Operable)

#### 6.1.1. (키보드 사용 보장) 모든 기능은 키보드만으로도 사용할 수 있어야 한다. 
> 웹 접근성에서 키보드 사용 보장이란 모든 기능이 키보드만으로도 사용할 수 있어야 한다는 것을 의미한다. 이는 시각 장애나 지체 장애가 있는 사용자들이 마우스를 사용할 수 없는 경우에도 웹 페이지의 모든 기능을 사용할 수 있도록 하기 위함이며, 키보드 네비게이션, 폼 요소의 접근성, 인터랙티브 요소의 포커스 등이 포함된다.    
WCAG 2.2 Guidelines : [2.1.1 Keyboard](https://www.w3.org/TR/WCAG22/#keyboard){: target="_blank"}   

```sh
<!-- 잘못된 예시 : 키보드로 조작할 수 없는 경우
    커스텀 버튼이 마우스 클릭으로만 조작 가능하며, 키보드로는 조작할 수 없음
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Non-keyboard Accessible Example</title>
  <style>
    .custom-button {
      width: 100px;
      height: 50px;
      background-color: blue;
      color: white;
      text-align: center;
      line-height: 50px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="custom-button" onclick="alert('Button clicked!')">Click me</div>
</body>
</html>

<!-- 올바른 예시 : 키보드로 조작할 수 있는 경우
    tabindex="0" 속성을 추가하여 키보드 포커스를 받을 수 있게 하고, onkeypress 이벤트를 사용하여 Enter 키로 버튼을 조작할 수 있게 함
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Keyboard Accessible Example</title>
  <style>
    .custom-button {
      width: 100px;
      height: 50px;
      background-color: blue;
      color: white;
      text-align: center;
      line-height: 50px;
      cursor: pointer;
    }
    .custom-button:focus {
      outline: 2px solid yellow;
    }
  </style>
</head>
<body>
  <div class="custom-button" tabindex="0" onclick="alert('Button clicked!')" onkeypress="if(event.key === 'Enter') { this.click(); }">Click me</div>
</body>
</html>
```

**검수 방법**
- 키보드만 사용하여 웹 애플리케이션의 모든 기능을 탐색하고 조작할 수 있는지 확인하였는가?   
- Tab, Shift+Tab, Enter, Space, Arrow 키 등을 사용하여 인터페이스 요소가 예상대로 작동하는지 테스트하였는가?   
- Axe와 같은 접근성 검사 도구를 사용하여 키보드 접근성의 문제를 평가하였는가?   
- WAVE 도구를 사용하여 키보드 접근성과 관련된 접근성 문제를 검사하였는가?   
- NVDA, JAWS와 같은 스크린 리더를 사용하여 키보드만으로 모든 기능을 사용할 수 있는지 확인하였는가?   
- 스크린 리더로 각 인터페이스 요소를 탐색하며 키보드 접근성이 보장되는지 확인하였는가?   
- 브라우저의 개발자 도구를 사용하여 HTML 구조와 접근성 속성을 검사하고, 모든 인터페이스 요소가 키보드로 접근 가능한지 확인하였는가?   
- 다양한 사용자가 웹 사이트를 탐색하며 키보드만으로 모든 기능을 사용하는 데 어려움이 없는지 피드백을 받았습니까?   


#### 6.1.2. (초점 이동과 표시) 키보드에 의한 초점은 논리적으로 이동해야 하며, 시각적으로 구별할 수 있어야 한다.
> 키보드에 의한 초점은 논리적으로 이동하고, 시각적으로 구별할 수 있어야 한다. 이는 사용자가 키보드를 통해 웹 페이지를 탐색할 때 초점의 위치를 쉽게 인식하고, 초점 이동이 자연스럽게 이루어지도록 한다.   
WCAG 2.2 Guidelines : [Focus Order](https://www.w3.org/TR/WCAG22/#focus-order){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 초점 이동이 논리적이지 않고 시각적으로 구별되지 않는 경우 
     초점이 이동할 때 시각적 표시가 없으며, 초점 이동의 순서가 논리적이지 않음.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example Page</title>
</head>
<body>
  <div>
    <button>Button 1</button>
    <input type="text" placeholder="Text Input">
    <button>Button 2</button>
  </div>
</body>
</html>


<!-- 올바른 예시 1 : 초점 이동이 논리적이고 시각적으로 구별되는 경우
     :focus 가상 클래스를 사용하여 초점이 맞춰진 요소를 시각적으로 구별할 수 있도록 하고, 요소의 배치와 순서를 논리적으로 배치.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example Page</title>
  <style>
    button, input[type="text"] {
      margin: 10px;
    }
    button:focus, input[type="text"]:focus {
      outline: 2px solid blue;
      outline-offset: 2px;
    }
  </style>
</head>
<body>
  <div>
    <button>Button 1</button>
    <button>Button 2</button>
    <input type="text" placeholder="Text Input">
  </div>
</body>
</html>
```

**검수 방법**
- 키보드만 사용하여 페이지를 탐색하며, 초점 이동이 논리적으로 이루어지는지 확인하였습니까?     
- 초점이 맞춰진 요소가 시각적으로 구별되는지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 초점 이동의 논리성과 시각적 구별 가능성을 평가하였습니까?     
- WAVE 도구를 사용하여 초점 이동과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 초점 이동이 논리적이고 시각적으로 구별 가능한지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 HTML 구조와 CSS 스타일을 검사하고, 초점 이동이 올바르게 구현되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 초점 이동과 시각적 구별이 원활한지 피드백을 받았습니까?    


#### 6.1.3. (조작 가능) 사용자 입력 및 콘트롤은 조작 가능하도록 제공되어야 한다.
> 사용자 입력 및 컨트롤이 조작 가능하게 제공된다는 것은, 모든 사용자(장애가 있는 사용자 포함)가 웹 페이지의 모든 기능을 문제없이 사용할 수 있도록 하는 것을 의미하며, 키보드, 마우스, 터치스크린 등 다양한 입력 장치를 사용하여 웹 페이지를 조작할 수 있어야 함을 포함한다.   
WCAG 2.2 Guidelines : [Keyboard Accessible](https://www.w3.org/TR/WCAG22/#keyboard-accessible){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 조작 불가능한 컨트롤 
     버튼이 숨겨져 있어 접근할 수 없고, 텍스트 입력 필드가 읽기 전용으로 설정되어 있어 사용자가 입력 불가능
-->
<div>
  <button onclick="alert('Button clicked!')" style="display:none;">Hidden Button</button>
  <input type="text" placeholder="Enter text" readonly>
</div>

<!-- 잘못된 예시 2 : 키보드 접근성이 없는 경우 
     tabindex="-1" 속성으로 인해 버튼이 키보드 포커스를 받을 수 없음
-->
<div>
  <button onclick="alert('Button clicked!')" tabindex="-1">Non-focusable Button</button>
</div>


<!-- 올바른 예시 1 : 조작 가능한 컨트롤
     버튼이 표시되어 있으며, 텍스트 입력 필드가 조작 가능하게 설정.
-->
<div>
  <button onclick="alert('Button clicked!')">Click me</button>
  <input type="text" placeholder="Enter text">
</div>

<!-- 올바른 예시 2 : 키보드 접근성이 있는 경우
     버튼이 키보드 포커스를 받을 수 있도록 설정.
-->
<div>
  <button onclick="alert('Button clicked!')">Focusable Button</button>
</div>
```

**검수 방법**
- 키보드, 마우스, 터치스크린 등 다양한 입력 장치를 사용하여 웹 페이지의 모든 기능을 테스트하였습니까?     
- 모든 버튼, 링크, 입력 필드 등이 조작 가능한지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 사용자 입력 및 컨트롤의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 조작 가능 여부를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 모든 사용자 입력 및 컨트롤이 접근 가능하고 조작 가능한지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 HTML 구조와 CSS 스타일을 검사하고, 모든 사용자 입력 및 컨트롤이 조작 가능하게 설정되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 모든 기능을 문제없이 사용할 수 있는지 피드백을 받았습니까?    


#### 6.1.4 (문자 단축키) 문자 단축키는 오동작으로 인한 오류를 방지하여야 한다.
> 문자 단축키는 오동작을 방지할 수 있도록 설계되어야 하며, 사용자에게 혼란을 주지 않도록, 단축키를 사용할 때 명확한 컨텍스트가 필요하거나 추가 키(예: Ctrl, Alt, Shift)와 함께 사용해야 함을 의미한다.   
WCAG 2.2 Guidelines : [Character Key Shortcuts](https://www.w3.org/TR/WCAG22/#character-key-shortcuts){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 오동작 방지 없이 문자 단축키 사용
     사용자가 입력 필드에 텍스트를 입력할 때 'a' 키를 누르면 의도하지 않은 동작이 발생할 수 있음
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example Page</title>
  <script>
    document.addEventListener('keydown', function(event) {
      if (event.key === 'a') {
        alert('You pressed the "a" key!');
      }
    });
  </script>
</head>
<body>
  <input type="text" placeholder="Type something here">
</body>
</html>


<!-- 올바른 예시 1 : 오동작 방지를 위한 문자 단축키 사용
     'Ctrl' 키와 함께 'a' 키를 눌러야 단축키가 작동하도록 하여 오동작을 방지.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example Page</title>
  <script>
    document.addEventListener('keydown', function(event) {
      if (event.ctrlKey && event.key === 'a') {
        alert('You pressed "Ctrl + a"!');
        event.preventDefault(); // 기본 동작 방지
      }
    });
  </script>
</head>
<body>
  <input type="text" placeholder="Type something here">
</body>
</html>
```

**검수 방법**
- 다양한 입력 시나리오를 테스트하여 단축키가 의도치 않게 작동하지 않는지 확인하였습니까?     
- 단축키를 사용할 때 추가 키(예: Ctrl, Alt, Shift)와 함께 사용하도록 설정되었는지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 문자 단축키 사용의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 단축키 사용과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 단축키가 올바르게 작동하고, 오동작을 방지하도록 설정되었는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 단축키 이벤트 리스너와 스크립트를 검사하고, 오동작을 방지하기 위한 추가 키 설정이 올바르게 구현되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 단축키 사용에 불편함이 없는지 피드백을 받았습니까?    


#### 6.2.1. (응답시간 조절) 시간제한이 있는 콘텐츠는 응답시간을 조절할 수 있어야 한다.
> 시간제한이 있는 콘텐츠는 사용자가 응답시간을 조절할 수 있도록 해야 하며, 사용자가 콘텐츠를 충분히 읽고 이해하며 상호작용할 수 있는 시간을 제공하는 것을 의미한다. 사용자는 시간을 연장하거나, 일시 정지하거나, 시간제한을 제거할 수 있는 옵션을 제공받아야 한다.   
WCAG 2.2 Guidelines : [Timing Adjustable](https://www.w3.org/TR/WCAG22/#timing-adjustable){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 시간제한을 조절할 수 없는 경우
     시간제한이 고정되어 있으며 사용자가 조절할 수 없음
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Timed Quiz</title>
  <script>
    let timeLeft = 30;
    let timer = setInterval(function() {
      document.getElementById('time').textContent = timeLeft + ' seconds remaining';
      timeLeft--;
      if (timeLeft < 0) {
        clearInterval(timer);
        alert('Time is up!');
      }
    }, 1000);
  </script>
</head>
<body>
  <h1>Quiz</h1>
  <p id="time">30 seconds remaining</p>
  <form>
    <label for="question">What is 2 + 2?</label>
    <input type="text" id="question" name="question">
    <button type="submit">Submit</button>
  </form>
</body>
</html>


<!-- 올바른 예시 1 : 시간제한을 조절할 수 있는 경우
    사용자가 시간을 연장하거나, 일시 정지하거나, 다시 시작할 수 있는 옵션을 제공.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Timed Quiz</title>
  <script>
    let timeLeft = 30;
    let timer;

    function startTimer() {
      timer = setInterval(function() {
        document.getElementById('time').textContent = timeLeft + ' seconds remaining';
        timeLeft--;
        if (timeLeft < 0) {
          clearInterval(timer);
          alert('Time is up!');
        }
      }, 1000);
    }

    function extendTime() {
      timeLeft += 30; // Extend time by 30 seconds
    }

    function pauseTimer() {
      clearInterval(timer);
    }

    function resumeTimer() {
      startTimer();
    }

    window.onload = function() {
      startTimer();
    }
  </script>
</head>
<body>
  <h1>Quiz</h1>
  <p id="time">30 seconds remaining</p>
  <form>
    <label for="question">What is 2 + 2?</label>
    <input type="text" id="question" name="question">
    <button type="submit">Submit</button>
  </form>
  <button onclick="extendTime()">Extend Time</button>
  <button onclick="pauseTimer()">Pause</button>
  <button onclick="resumeTimer()">Resume</button>
</body>
</html>
```

**검수 방법**
- 시간을 연장, 일시 정지 및 다시 시작할 수 있는 옵션이 제공되는지 확인하였습니까?     
- 다양한 시나리오에서 시간이 올바르게 조절되는지 테스트하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 시간제한 조절 기능의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 시간제한 조절 기능과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 시간제한 조절 기능이 올바르게 작동하고 접근 가능한지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 시간제한 조절 스크립트와 HTML 구조를 검사하고, 모든 기능이 올바르게 구현되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 시간제한 조절 기능을 사용하는 데 어려움이 없는지 피드백을 받았습니까?    


#### 6.2.2. (정지 기능 제공) 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.
> 자동으로 변경되는 콘텐츠는 사용자가 이를 제어할 수 있도록 기능을 제공해야 하며, 사용자가 콘텐츠의 자동 변환을 멈추거나 일시 정지할 수 있는 옵션을 포함하여 시각적 혼란을 최소화하는 것을 의미한다.   
WCAG 2.2 Guidelines : [Pause, Stop, Hide](https://www.w3.org/TR/WCAG22/#pause-stop-hide){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 초당 3~50회 주기로 깜빡이는 콘텐츠 
     자동 슬라이드쇼를 제어할 수 있는 방법이 미제공
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Auto-changing Content</title>
  <style>
    #slider {
      width: 100%;
      height: 200px;
      overflow: hidden;
    }
    #slides {
      display: flex;
      width: 400%;
      animation: slide 8s infinite;
    }
    .slide {
      width: 100%;
      height: 200px;
    }
    @keyframes slide {
      0% { transform: translateX(0); }
      25% { transform: translateX(-100%); }
      50% { transform: translateX(-200%); }
      75% { transform: translateX(-300%); }
      100% { transform: translateX(0); }
    }
  </style>
</head>
<body>
  <div id="slider">
    <div id="slides">
      <div class="slide" style="background-color: red;"></div>
      <div class="slide" style="background-color: blue;"></div>
      <div class="slide" style="background-color: green;"></div>
      <div class="slide" style="background-color: yellow;"></div>
    </div>
  </div>
</body>
</html>


<!-- 올바른 예시 1 : 자동으로 변경되는 콘텐츠를 제어할 수 있는 경우
    사용자가 슬라이드쇼를 일시 정지하거나 다시 시작할 수 있는 버튼을 제공하여 자동으로 변경되는 콘텐츠를 제어 가능.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Auto-changing Content</title>
  <style>
    #slider {
      width: 100%;
      height: 200px;
      overflow: hidden;
      position: relative;
    }
    #slides {
      display: flex;
      width: 400%;
      transition: transform 1s;
    }
    .slide {
      width: 100%;
      height: 200px;
    }
    .control-buttons {
      position: absolute;
      top: 10px;
      right: 10px;
      z-index: 10;
    }
  </style>
</head>
<body>
  <div id="slider">
    <div id="slides">
      <div class="slide" style="background-color: red;"></div>
      <div class="slide" style="background-color: blue;"></div>
      <div class="slide" style="background-color: green;"></div>
      <div class="slide" style="background-color: yellow;"></div>
    </div>
    <div class="control-buttons">
      <button onclick="pauseSlides()">Pause</button>
      <button onclick="resumeSlides()">Resume</button>
    </div>
  </div>

  <script>
    let currentIndex = 0;
    let slides = document.getElementById('slides');
    let totalSlides = slides.children.length;
    let interval;

    function showSlide(index) {
      slides.style.transform = 'translateX(' + (-100 * index) + '%)';
    }

    function nextSlide() {
      currentIndex = (currentIndex + 1) % totalSlides;
      showSlide(currentIndex);
    }

    function startSlides() {
      interval = setInterval(nextSlide, 2000);
    }

    function pauseSlides() {
      clearInterval(interval);
    }

    function resumeSlides() {
      startSlides();
    }

    window.onload = function() {
      startSlides();
    }
  </script>
</body>
</html>
```

**검수 방법**
- 콘텐츠의 자동 변환을 멈추거나 일시 정지할 수 있는 옵션이 제공되는지 확인하였습니까?     
- 다양한 시나리오에서 제어 기능이 올바르게 작동하는지 테스트하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 자동으로 변경되는 콘텐츠 제어 기능의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 제어 기능과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 자동으로 변경되는 콘텐츠 제어 기능이 올바르게 작동하고 접근 가능한지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 제어 스크립트와 HTML 구조를 검사하고, 모든 기능이 올바르게 구현되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 자동으로 변경되는 콘텐츠 제어 기능을 사용하는 데 어려움이 없는지 피드백을 받았습니까?    


#### 6.3.1. (깜빡임과 번쩍임 사용 제한) 초당 3~50회 주기로 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.
> 초당 3~50회 주기로 깜빡이거나 번쩍이는 콘텐츠는 사용자가 발작을 경험할 수 있는 위험을 증가시키므로 피해야 한다. 대신, 깜빡임을 줄이거나 제거하고, 다른 시각적 효과로 대체해야 한다.   
WCAG 2.2 Guidelines : [Three Flashes or Below Threshold](https://www.w3.org/TR/WCAG22/#three-flashes-or-below-threshold){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 초당 3~50회 주기로 깜빡이는 콘텐츠 
     blink 애니메이션이 초당 10회 깜빡이도록 설정되어 있어 접근성 문제를 일으킬 수 있음
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Blinking Content</title>
  <style>
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }
    .blink {
      animation: blink 0.1s infinite;
    }
  </style>
</head>
<body>
  <div class="blink">This content blinks rapidly!</div>
</body>
</html>


<!-- 올바른 예시 1 : 깜빡임을 제거한 콘텐츠
    깜빡임 대신 배경색이 부드럽게 전환되도록 설정하여 안전하게 시각적 주의를 끌 수 있는경우.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Non-Blinking Content</title>
  <style>
    .highlight {
      background-color: yellow;
      transition: background-color 0.5s ease;
    }
    .highlight:hover {
      background-color: orange;
    }
  </style>
</head>
<body>
  <div class="highlight">This content changes color smoothly!</div>
</body>
</html>
```

**검수 방법**
- 모든 콘텐츠를 확인하여 초당 3~50회 주기로 깜빡이거나 번쩍이는 요소가 있는지 검사하였습니까?     
- 깜빡임이 있는 콘텐츠를 다른 시각적 효과로 대체했는지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 깜빡임과 번쩍임 문제를 평가하였습니까?     
- WAVE 도구를 사용하여 깜빡임 관련 접근성 문제를 검사하였습니까?     
- 브라우저의 개발자 도구를 사용하여 애니메이션 및 전환 효과를 검사하고, 깜빡임이 없는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 깜빡임이나 번쩍임이 발생하지 않는지 피드백을 받았습니까?    


#### 6.4.4. (고정된 참조 위치 정보) 전자출판문서 형식의 웹 페이지는 각페이지로 이동할 수 있는 기능이 있어야 하고, 서식이나 플랫폼에 상관없이 참조 위치 정보를 일관되게 제공ㆍ유지해야 한다.
> 전자출판문서 형식의 웹 페이지는 각 페이지로 이동할 수 있는 기능을 제공해야 한다. 또한, 서식이나 플랫폼에 상관없이 참조 위치 정보를 일관되게 제공·유지하여 사용자가 문서 내에서 일관된 경험을 할 수 있도록 해야 한다.   
WCAG 2.2 Guidelines : [Navigable](https://www.w3.org/TR/WCAG22/#navigable){: target="_blank"}
[EPUB Accessibility Guidelines](https://www.w3.org/TR/epub-a11y-11/){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 페이지 이동 기능이 없는 경우 
    페이지 이동 기능이 제공되지 않아 사용자가 문서 내에서 쉽게 탐색 불가능
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document without Navigation</title>
</head>
<body>
  <div id="content">
    <h1>Chapter 1</h1>
    <p>Content of chapter 1...</p>
    <h1>Chapter 2</h1>
    <p>Content of chapter 2...</p>
  </div>
</body>
</html>


<!-- 올바른 예시 1 : 페이지 이동 기능이 있는 경우
    내비게이션 링크를 제공하여 사용자가 각 챕터로 쉽게 이동.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document with Navigation</title>
</head>
<body>
  <nav>
    <ul>
      <li><a href="#chapter1">Chapter 1</a></li>
      <li><a href="#chapter2">Chapter 2</a></li>
      <li><a href="#chapter3">Chapter 3</a></li>
    </ul>
  </nav>
  <div id="content">
    <h1 id="chapter1">Chapter 1</h1>
    <p>Content of chapter 1...</p>
    <h1 id="chapter2">Chapter 2</h1>
    <p>Content of chapter 2...</p>
    <h1 id="chapter3">Chapter 3</h1>
    <p>Content of chapter 3...</p>
  </div>
</body>
</html>


<!-- 올바른 예시 2 : 일관된 참조 위치 정보 제공
    id 속성을 사용하여 페이지를 구분하고, 내비게이션 링크를 통해 각 페이지로 이동할 수 있도록 합니다. 각 페이지는 :target CSS 선택자를 사용하여 참조 위치가 일관되게 유지.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document with Consistent Reference</title>
  <style>
    .page {
      display: none;
    }
    .page:target {
      display: block;
    }
  </style>
</head>
<body>
  <nav>
    <ul>
      <li><a href="#page1">Page 1</a></li>
      <li><a href="#page2">Page 2</a></li>
      <li><a href="#page3">Page 3</a></li>
    </ul>
  </nav>
  <div id="content">
    <div id="page1" class="page">
      <h1>Page 1</h1>
      <p>Content of page 1...</p>
    </div>
    <div id="page2" class="page">
      <h1>Page 2</h1>
      <p>Content of page 2...</p>
    </div>
    <div id="page3" class="page">
      <h1>Page 3</h1>
      <p>Content of page 3...</p>
    </div>
  </div>
</body>
</html>
```

**검수 방법**
- 내비게이션 링크를 클릭하여 각 페이지로 이동할 수 있는지 확인하였습니까?     
- 모든 페이지가 일관된 참조 위치를 유지하고 있는지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 내비게이션 기능의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 내비게이션과 참조 위치 정보와 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 내비게이션 링크와 참조 위치가 올바르게 작동하는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 HTML 구조와 CSS 스타일을 검사하고, 모든 기능이 올바르게 구현되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 내비게이션 기능과 참조 위치 정보 제공에 어려움이 없는지 피드백을 받았습니까?    


#### 6.5.1. (단일 포인터 입력 지원) 다중 포인터 또는 경로기반 동작을 통한 입력은 단일 포인터 입력으로도 조작할 수 있어야 한다.
> 웹 애플리케이션은 다중 포인터 또는 경로 기반 동작을 포함한 입력 방식을 사용할 때, 단일 포인터 입력으로도 동일한 작업을 수행할 수 있도록 지원해야 한다. 이는 사용자가 한 손가락만으로도 모든 기능을 이용할 수 있게 하여 접근성을 높입.   
WCAG 2.2 Guidelines : [Pointer Gestures](https://www.w3.org/TR/WCAG22/#pointer-gestures){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 다중 포인터 입력만 지원하는 경우 
    다중 포인터 입력(예: 두 손가락으로 줌)을 지원하지만, 단일 포인터 입력에 대한 대체 방법이 미제공
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Multi-pointer Input Only</title>
  <style>
    #image {
      width: 300px;
      height: 200px;
      background: url('image.jpg') no-repeat;
      background-size: cover;
    }
  </style>
</head>
<body>
  <div id="image"></div>
  <script>
    const image = document.getElementById('image');
    image.addEventListener('touchstart', function(event) {
      if (event.touches.length > 1) {
        // Handle multi-touch zoom or pan
      }
    });
  </script>
</body>
</html>


<!-- 올바른 예시 1 : 단일 포인터 입력을 지원하는 경우
    단일 포인터 입력(예: 마우스를 통한 드래그)을 지원하여 모든 사용자가 이미지를 조작할 수 있도록 제공.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Single Pointer Input Supported</title>
  <style>
    #image {
      width: 300px;
      height: 200px;
      background: url('image.jpg') no-repeat;
      background-size: cover;
    }
  </style>
</head>
<body>
  <div id="image"></div>
  <script>
    const image = document.getElementById('image');
    let isDragging = false;
    let startX, startY;

    // Multi-pointer input (e.g., zoom)
    image.addEventListener('touchstart', function(event) {
      if (event.touches.length > 1) {
        // Handle multi-touch zoom or pan
      }
    });

    // Single pointer input (e.g., drag)
    image.addEventListener('mousedown', function(event) {
      isDragging = true;
      startX = event.pageX - image.offsetLeft;
      startY = event.pageY - image.offsetTop;
    });

    document.addEventListener('mousemove', function(event) {
      if (isDragging) {
        image.style.left = `${event.pageX - startX}px`;
        image.style.top = `${event.pageY - startY}px`;
      }
    });

    document.addEventListener('mouseup', function() {
      isDragging = false;
    });
  </script>
</body>
</html>
```

**검수 방법**
- 터치스크린, 마우스, 스타일러스 등 다양한 입력 장치를 사용하여 웹 애플리케이션의 모든 기능이 단일 포인터 입력으로 작동하는지 확인하였습니까?     
- 다중 포인터 입력이 필요한 기능이 단일 포인터 입력으로도 수행될 수 있는지 테스트하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 포인터 입력 지원의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 포인터 입력과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 단일 포인터 입력이 올바르게 작동하고 접근 가능한지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 입력 이벤트 리스너와 스크립트를 검사하고, 모든 기능이 단일 포인터 입력으로도 조작 가능하게 구현되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 단일 포인터 입력으로 모든 기능을 사용하는 데 어려움이 없는지 피드백을 받았습니까?    


#### 6.5.2. (포인터 입력 취소) 단일 포인터 입력으로 실행되는 기능은 취소할 수 있어야 한다.
> 단일 포인터 입력으로 실행되는 기능은 사용자가 쉽게 취소할 수 있어야 한다. 이를 통해 사용자는 실수로 실행된 동작을 되돌릴 수 있으며, 웹 애플리케이션을 더 편리하게 사용할 수 있다.   
WCAG 2.2 Guidelines : [Pointer Cancellation](https://www.w3.org/TR/WCAG22/#pointer-cancellation){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 포인터 입력 취소 기능이 없는 경우 
    사용자가 삭제 버튼을 클릭하면 즉시 동작이 실행되며, 이를 취소할 수 있는 방법이 미제공
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Uncancelable Action</title>
</head>
<body>
  <button id="deleteButton">Delete</button>
  <script>
    document.getElementById('deleteButton').addEventListener('click', function() {
      alert('Item deleted');
    });
  </script>
</body>
</html>


<!-- 올바른 예시 1 : 포인터 입력 취소 기능이 있는 경우
    삭제 버튼을 클릭하면 확인 대화 상자가 나타나며, 사용자가 동작을 취소할 수 있는 옵션을 제공.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Cancelable Action</title>
</head>
<body>
  <button id="deleteButton">Delete</button>
  <div id="confirmationDialog" style="display:none;">
    <p>Are you sure you want to delete this item?</p>
    <button id="confirmDelete">Yes</button>
    <button id="cancelDelete">No</button>
  </div>
  <script>
    document.getElementById('deleteButton').addEventListener('click', function() {
      document.getElementById('confirmationDialog').style.display = 'block';
    });

    document.getElementById('confirmDelete').addEventListener('click', function() {
      alert('Item deleted');
      document.getElementById('confirmationDialog').style.display = 'none';
    });

    document.getElementById('cancelDelete').addEventListener('click', function() {
      document.getElementById('confirmationDialog').style.display = 'none';
    });
  </script>
</body>
</html>
```

**검수 방법**
- 단일 포인터 입력(예: 마우스 클릭, 터치)을 통해 실행되는 모든 기능이 취소 가능한지 확인하였습니까?     
- 실행된 동작을 쉽게 취소할 수 있는지 테스트하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 포인터 입력 취소 기능의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 포인터 입력과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 포인터 입력 취소 기능이 올바르게 작동하고 접근 가능한지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 이벤트 리스너와 스크립트를 검사하고, 모든 기능이 취소 가능하게 구현되었는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 포인터 입력 취소 기능을 사용하는 데 어려움이 없는지 피드백을 받았습니까?    


#### 6.5.3. (레이블과 네임) 텍스트 또는 텍스트 이미지가 포함된 레이블이 있는 사용자 인터페이스 구성요소는 네임에 시각적으로 표시되는 해당 텍스트를 포함해야 한다.
> 텍스트 또는 텍스트 이미지를 포함한 레이블이 있는 사용자 인터페이스 구성 요소는 네임에 시각적으로 표시되는 해당 텍스트를 포함해야 한다. 이는 사용자 인터페이스의 일관성을 유지하고, 보조 기술이 정확하게 정보를 전달할 수 있도록 보장해야 한다.   
WCAG 2.2 Guidelines : [Label in Name](https://www.w3.org/TR/WCAG22/#label-in-name){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 레이블과 네임이 일치하지 않는 경우 
    시각적으로 "Find:"가 표시되지만, 스크린 리더는 "Search"라는 네임을 읽게 되어 일관성이 없음
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Label and Name Example</title>
</head>
<body>
  <label for="search">Find:</label>
  <input type="text" id="search" aria-label="Search">
</body>
</html>


<!-- 올바른 예시 1 : 레이블과 네임이 일치하는 경우
    시각적으로 표시되는 텍스트 "Search:"와 스크린 리더가 읽는 네임 "Search"가 일치.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Label and Name Example</title>
</head>
<body>
  <label for="search">Search:</label>
  <input type="text" id="search" aria-label="Search">
</body>
</html>
```

**검수 방법**
- UI 요소의 시각적 레이블과 네임이 일치하는지 확인하였습니까?     
- HTML 소스 코드를 확인하여 aria-label 또는 aria-labelledby 속성이 올바르게 설정되었는지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 레이블과 네임의 일치성을 평가하였습니까?     
- WAVE 도구를 사용하여 레이블과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 레이블과 네임이 일치하는지 확인하였습니까?     
- 스크린 리더로 각 UI 요소를 탐색하며 시각적으로 표시된 텍스트와 네임이 일치하는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 HTML 구조와 접근성 속성을 검사하고, 레이블과 네임이 일치하는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 레이블과 네임의 일치성에 대한 피드백을 받았습니까?    



#### 6.5.4. (동작기반 작동) 동작기반으로 작동하는 기능은 사용자 인터페이스 구성요소로 조작할 수 있고, 동작기반 기능을 비활성화할 수 있어야 한다.
> 동작기반으로 작동하는 기능은 사용자 인터페이스 구성 요소로도 조작할 수 있어야 하며, 사용자가 이러한 기능을 비활성화할 수 있는 옵션을 제공해야 한다. 이를 통해 다양한 사용자가 동일한 기능을 접근하고 사용할 수 있도록 보장한다.   
WCAG 2.2 Guidelines : [Motion Actuation](https://www.w3.org/TR/WCAG22/#motion-actuation){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 동작기반 기능만 제공하는 경우 
    기기를 흔드는 동작으로만 기능이 작동하며, 다른 대체 방법이 미제공
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Motion-Based Functionality</title>
  <script>
    window.addEventListener('devicemotion', function(event) {
      if (event.acceleration.x > 2) {
        alert('Motion detected!');
      }
    });
  </script>
</head>
<body>
  <p>Shake your device to trigger an action.</p>
</body>
</html>


<!-- 올바른 예시 1 : 사용자 인터페이스 구성 요소와 비활성화 옵션을 제공하는 경우
    사용자가 기기를 흔드는 동작과 버튼 클릭을 통해 동일한 기능을 사용할 수 있으며, 동작기반 기능을 비활성화할 수 있는 옵션을 제공.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Motion-Based Functionality with UI Controls</title>
  <style>
    #disableMotion {
      margin-top: 20px;
    }
  </style>
  <script>
    let motionEnabled = true;

    function handleMotion(event) {
      if (motionEnabled && event.acceleration.x > 2) {
        alert('Motion detected!');
      }
    }

    window.addEventListener('devicemotion', handleMotion);

    function toggleMotion() {
      motionEnabled = !motionEnabled;
      document.getElementById('motionStatus').textContent = motionEnabled ? 'enabled' : 'disabled';
    }
  </script>
</head>
<body>
  <p>Shake your device to trigger an action or click the button below.</p>
  <button onclick="alert('Button clicked!')">Trigger Action</button>
  <div id="disableMotion">
    <button onclick="toggleMotion()">Toggle Motion Detection</button>
    <p>Motion detection is currently <span id="motionStatus">enabled</span>.</p>
  </div>
</body>
</html>
```

**검수 방법**
- 동작기반 기능이 사용자 인터페이스 구성 요소(예: 버튼 클릭)를 통해 조작될 수 있는지 확인하였습니까?     
- 동작기반 기능을 비활성화할 수 있는 옵션이 제공되는지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 동작기반 기능의 접근성을 평가하였습니까?     
- WAVE 도구를 사용하여 동작기반 기능과 관련된 접근성 문제를 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 동작기반 기능이 올바르게 작동하고 접근 가능한지 확인하였습니까?     
- 스크린 리더를 사용하여 비활성화 옵션이 제대로 작동하는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 이벤트 리스너와 스크립트를 검사하고, 동작기반 기능이 사용자 인터페이스 구성 요소로 조작될 수 있는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 동작기반 기능과 비활성화 옵션을 사용하는 데 어려움이 없는지 피드백을 받았습니까?    



### 이해의 용이성 (Understandable)

#### 7.1.1. (기본 언어 표시) 주로 사용하는 언어를 명시해야 한다. 
> 주로 사용하는 언어를 명시하여, 브라우저와 보조 기술이 페이지의 언어를 올바르게 인식하도록 적절한 설정을 적용함으로서 사용자 경험과 접근성을 크게 향상시킨다.   
WCAG 2.2 Guidelines : [Language of Page](https://www.w3.org/TR/WCAG22/#language-of-page){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 기본 언어가 명시되지 않은 경우
    페이지의 기본 언어가 명시되지 않아 브라우저와 보조 기술이 언어를 인식할 수 없다.   
-->
<!DOCTYPE html>
<html>
<head>
  <title>Example Page</title>
</head>
<body>
  <h1>Welcome to our website</h1>
  <p>This is a sample paragraph.</p>
</body>
</html>


<!-- 잘못된 예시 2 : 다국어 콘텐츠가 포함된 경우 
    일부 콘텐츠가 스페인어로 되어 있지만 언어가 명시되지 않았음
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Multilingual Page</title>
</head>
<body>
  <h1>Welcome to our website</h1>
  <p>Bienvenido a nuestro sitio web</p>
</body>
</html>



<!-- 올바른 예시 1 : 기본 언어를 명시한 경우
    lang 속성을 사용하여 페이지의 기본 언어를 영어(en)로 명시.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Multilingual Page</title>
</head>
<body>
  <h1>Welcome to our website</h1>
  <p>Bienvenido a nuestro sitio web</p>
</body>
</html>


<!-- 올바른 예시 2 : 다국어 콘텐츠가 포함된 경우 
    lang="es" 속성을 사용하여 스페인어 콘텐츠를 명시.
-->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Multilingual Page</title>
</head>
<body>
  <h1>Welcome to our website</h1>
  <p lang="es">Bienvenido a nuestro sitio web</p>
</body>
</html>
```

**검수 방법**
- HTML 문서의 &lt;html&gt; 태그에 lang 속성이 올바르게 설정되어 있는지 확인하였습니까?     
- 다국어 콘텐츠가 포함된 경우, 해당 콘텐츠의 lang 속성이 올바르게 설정되어 있는지 확인하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 페이지의 언어 설정이 올바른지 평가하였습니까?     
- WAVE 도구를 사용하여 페이지의 접근성을 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 페이지의 언어가 올바르게 인식되는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 HTML 구조를 검사하고, 언어 속성이 올바르게 설정되었는지 확인하였습니까?     
- Google Search Console과 같은 도구를 사용하여 페이지의 언어 설정이 검색 엔진에 올바르게 인식되는지 확인하습니까?    


#### 7.2.1. (사용자 요구에 따른 실행) 사용자가 의도하지 않은 기능(새 창, 초점에 의한 맥락 변화 등)은 실행되지 않아야 한다. 
> 사용자가 의도하지 않은 기능이 실행되지 않도록 하려면, 사용자 인터페이스 요소가 예상치 못한 방식으로 동작하지 않도록 해야 하고, 특히 새 창 열기, 자동 포커스 변경 등의 동작은 사용자의 명시적인 동작이나 선택에 의해서만 이루어져야 한다.   
WCAG 2.2 Guidelines : [On Focus](https://www.w3.org/TR/WCAG22/#on-focus){: target="_blank"}
WCAG 2.2 Guidelines : [On Input](https://www.w3.org/TR/WCAG22/#on-input){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 의도하지 않은 새 창 열기(사전 안내 미제공)
    사용자가 클릭할 때 새 창이 열리지만 새 창이 열리는 사전안내가 없어 사용자에게 혼란을 줄 수 있다   
-->
<a href="https://uxkm.io" target="_blank">UXKM</a>

<!-- 잘못된 예시 2 : 의도하지 않은 포커스 변화 
    사용자가 username 필드에 포커스를 줄 때 자동으로 password 필드로 포커스가 이동하여 혼란을 줄 수 있다
-->
<input type="text" id="username" onfocus="document.getElementById('password').focus();">
<input type="password" id="password">



<!-- 올바른 예시 1 : 의도하지 않은 새 창 열기(사전 안내 제공) -->
<a href="https://uxkm.io" target="_blank" title="새 창 열림">UXKM</a>

<!-- 올바른 예시 2 : 의도하지 않은 포커스 변화 방지 
    사용자가 입력 필드 사이를 자유롭게 이동할 수 있도록 자동 포커스 이동을 제거
-->
<label for="username">Username:</label>
<input type="text" id="username" name="username">

<label for="password">Password:</label>
<input type="password" id="password" name="password">
```

**검수 방법**
- 페이지의 링크를 클릭하여 새 창이 열리지 않는지 확인하였습니까?     
- 입력 필드와 상호작용할 때 의도하지 않은 포커스 변화가 발생하지 않는지 테스트하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 의도하지 않은 동작이 없는지 평가하였습니까?     
- WAVE 도구를 사용하여 페이지의 접근성을 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 상호작용 시 의도하지 않은 기능이 실행되지 않는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 이벤트 핸들러와 스크립트를 검사하고, 의도하지 않은 동작이 발생하지 않는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 의도하지 않은 기능이 실행되지 않는지 피드백을 받았습니까?    


#### 7.2.2. (찾기 쉬운 도움 정보) 도움 정보가 제공되는 경우, 각 페이지에서 동일한 상대적인 순서로 접근할 수 있어야 한다.
> 도움 정보가 제공되는 경우, 모든 페이지에서 동일한 위치와 접근 방법으로 제공되어야 하고, 사용자는 페이지마다 도움 정보를 찾는 데 혼동을 겪지 않고, 일관된 사용자 경험을 제공받을 수 있음.   
WCAG 2.2 Guidelines : [Consistent Navigation](https://www.w3.org/TR/WCAG22/#consistent-navigation){: target="_blank"}
WCAG 2.2 Guidelines : [Consistent Identification](https://www.w3.org/TR/WCAG22/#consistent-identification){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 일관되지 않은 도움 정보 위치
    페이지마다 도움 정보의 위치가 달라 사용자가 찾기 어려움이 있음 
-->
<!-- Page 1 -->
<div id="header">
  <a href="help.html">Help</a>
</div>
<!-- Page 2 -->
<div id="footer">
  <a href="help.html">Help</a>
</div>


<!-- 올바른 예시 1 : 일관된 도움 정보 위치 
    모든 페이지의 헤더 내에서 동일한 위치에 도움 정보를 제공하여 사용자가 쉽게 찾을 수 있다
-->
<!-- Page 1 -->
<div id="header">
  <nav>
    <a href="home.html">Home</a>
    <a href="about.html">About</a>
    <a href="help.html">Help</a>
  </nav>
</div>
<!-- Page 2 -->
<div id="header">
  <nav>
    <a href="home.html">Home</a>
    <a href="about.html">About</a>
    <a href="help.html">Help</a>
  </nav>
</div>


<!-- 올바른 예시 2 : 일관된 도움 정보 위치와 접근성 향상
    모든 페이지에서 동일한 헤더 파일을 포함시켜 도움 정보의 위치를 일관되게 유지. 또한 aria-label 속성을 사용하여 접근성을 향상
-->
<!-- Header include (header.html) -->
<div id="header">
  <nav>
    <a href="home.html">Home</a>
    <a href="about.html">About</a>
    <a href="help.html" aria-label="Help page">Help</a>
  </nav>
</div>

<!-- Page 1 -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Page 1</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <!-- Include header -->
  <div id="header-container">
    <?php include 'header.html'; ?>
  </div>
  <main>
    <h1>Welcome to Page 1</h1>
    <!-- Page content -->
  </main>
</body>
</html>

<!-- Page 2 -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Page 2</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <!-- Include header -->
  <div id="header-container">
    <?php include 'header.html'; ?>
  </div>
  <main>
    <h1>Welcome to Page 2</h1>
    <!-- Page content -->
  </main>
</body>
</html>
```

**검수 방법**
- 여러 페이지를 탐색하며 도움 정보가 동일한 위치에 있는지 확인하였습니까?     
- 도움 정보를 클릭하여 올바른 도움말 페이지로 이동하는지 테스트하였습니까?     
- Axe와 같은 접근성 검사 도구를 사용하여 도움 정보의 일관성을 평가하였습니까?     
- WAVE 도구를 사용하여 도움 정보의 접근성을 검사하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 도움 정보가 각 페이지에서 동일한 방법으로 접근되는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 HTML 구조를 검사하고, 도움 정보가 동일한 위치에 일관되게 제공되는지 확인하였습니까?     
- 다양한 사용자가 웹 사이트를 탐색하며 도움 정보를 찾는 데 어려움이 없는지 피드백을 받았습니까?    



#### 7.3.1. (오류 정정) 입력 오류를 정정할 수 있는 방법을 제공해야 한다. 
> 입력 오류 정정은 사용자가 폼이나 입력 필드에서 오류를 발생시켰을 때, 이를 사용자에게 알리고 수정할 수 있는 방법을 제공하는 것을 의미한다.   
WCAG 2.2 Guidelines : [Input Assistance](https://www.w3.org/TR/WCAG22/#error-identification){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 입력 오류가 발생해도 사용자에게 알림 미제공
<form id="exampleForm">
  <label for="email">Email:</label>
  <input type="email" id="email" name="email">
  <button type="submit">Submit</button>
</form>

<!-- 잘못된 예시 2 : 폼 필드가 잘못되었을 때 시각적 피드백을 미제공
<style>
  .error {
    color: red;
    font-weight: bold;
  }
</style>
<form>
  <label for="username">Username:</label>
  <input type="text" id="username" name="username">
  <span class="error">This field is required.</span>
  <button type="submit">Submit</button>
</form>


<!-- 올바른 예시 1 : aria-describedby와 aria-live 속성을 사용하여 실시간으로 오류 메시지를 사용자에게 알립 -->
<form id="exampleForm">
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" aria-describedby="emailError">
  <span id="emailError" class="error" aria-live="polite"></span>
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById('exampleForm').addEventListener('submit', function(event) {
    var emailInput = document.getElementById('email');
    var emailError = document.getElementById('emailError');
    if (!emailInput.checkValidity()) {
      emailError.textContent = 'Please enter a valid email address.';
      emailInput.focus();
      event.preventDefault();
    } else {
      emailError.textContent = '';
    }
  });
</script>

<!-- 올바른 예시 2 : 폼 필드에 오류가 있을 때 시각적 피드백을 제공하여 사용자가 오류를 쉽게 인식하고 수정할 수 있게 함 -->
<style>
  .error {
    border: 2px solid red;
  }
</style>
<form id="exampleForm">
  <label for="username">Username:</label>
  <input type="text" id="username" name="username" aria-describedby="usernameError">
  <span id="usernameError" class="error-message" aria-live="polite"></span>
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById('exampleForm').addEventListener('submit', function(event) {
    var usernameInput = document.getElementById('username');
    var usernameError = document.getElementById('usernameError');
    if (usernameInput.value === '') {
      usernameError.textContent = 'Username is required.';
      usernameInput.classList.add('error');
      usernameInput.focus();
      event.preventDefault();
    } else {
      usernameError.textContent = '';
      usernameInput.classList.remove('error');
    }
  });
</script>
```

**검수 방법**
- HTML Validator 사용: W3C HTML Validator와 같은 도구를 사용하여 마크업 오류를 자동으로 검수하였습니까?     
- 브라우저 개발자 도구 사용: 브라우저의 개발자 도구(예: Chrome DevTools)를 사용하여 HTML 구조를 확인하였습니까?     
- 수동 검사: HTML 코드를 수동으로 검토하여 태그의 열고 닫음, 중첩 관계, 속성 선언을 확인하였습니까?     


#### 7.3.2. (레이블 제공) 사용자 입력에는 대응하는 레이블을 제공해야 한다. 
> 사용자 입력 필드에 대응하는 레이블을 제공하는 것은 입력 필드가 어떤 정보를 요구하는지 사용자에게 명확히 전달하기 위함이며, 레이블은 입력 필드와 시각적으로 또는 프로그래밍 방식으로 연결되어야 한다.   
WCAG 2.2 Guidelines : [2.5.3 Label in Name](https://www.w3.org/TR/WCAG22/#label-in-name){: target="_blank"}
<!-- https://aoa.gitbook.io/skymimo/aoa-2018/tips/role-application -->

```sh
<!-- 잘못된 예시 1 : 입력 필드에 레이블 미제공
<input type="text" id="username">

<!-- 올바른 예시 1 : 입력 필드와 레이블을 연결 레이블 for 속성 + input id 연결 -->
<label for="username">Username:</label>
<input type="text" id="username" name="username">
```

**검수 방법**
- 입력 필드 옆에 레이블이 있는지 검토하였는가?     
- 레이블을 클릭하면 해당 입력 필드로 포커스가 이동하는지 확인하였습니까?     
- Axe, WAVE와 같은 접근성 검사 도구를 사용하여 레이블이 올바르게 제공되었는지 확인하였습니까?     
- 브라우저의 개발자 도구를 사용하여 HTML 구조를 확인하고, 입력 필드와 레이블이 적절히 연결되었는지 확인하였습니까?     
- NVDA, JAWS와 같은 스크린 리더를 사용하여 레이블이 입력 필드와 연결되어 올바르게 읽히는지 확인하였습니까?     


#### 7.3.3. (접근 가능한 인증) 인증 과정은 인지 기능 테스트에만 의존해서는 안 된다.  
> 접근 가능한 인증은 사용자의 인지 기능에만 의존하지 않는 인증 방법을 제공하는 것을 의미한다. 다양한 인증 방법을 제공하여 모든 사용자가 쉽게 인증 절차를 완료할 수 있도록 해야 한다.    
WCAG 2.2 Guidelines : [Accessible Authentication](https://www.w3.org/TR/WCAG22/#accessible-authentication-minimum){: target="_blank"}
Web Authentication : [An API for accessing Public Key Credentials](https://www.w3.org/TR/webauthn-2/){: target="_blank"}

인증방식의 예)
- 브라우저가 아이디/비밀번호를 저장할 수 있도록 마크업된 서식   
- 공개인증(OAuth: Open Authorization)을 통한 제3자 인증방식   
- 신체(얼굴, 지문 등)나 물건(휴대폰, USB 등)을 이용한 인증   
- 사용자 자신에게 익숙하여 별도의 인지적인 노력을 필요로 하지 않는 개인정보(이름, 이메일주소, 전화번호 등) 확인을 통한 인증   

```sh
<!-- 잘못된 예시 1 : 인지 기능에 의존하는 인증 - 사용자가 수학 문제를 풀어야 인증할 수 있어 인지 기능에 과도하게 의존
<form id="captchaForm">
  <label for="captcha">Please solve the following equation: 3 + 4 = ?</label>
  <input type="text" id="captcha" name="captcha">
  <button type="submit">Submit</button>
</form>


<!-- 올바른 예시 1 : 다양한 인증 방법 제공 - 사용자가 비밀번호 외에도 OTP(One-Time Password)를 사용하여 인증할 수 있는 방법을 제공 -->
<form id="authForm">
  <label for="username">Username:</label>
  <input type="text" id="username" name="username">

  <label for="password">Password:</label>
  <input type="password" id="password" name="password">

  <p>If you prefer, you can use an alternative method for authentication:</p>
  <button type="button" onclick="sendOtp()">Send OTP to my phone</button>

  <label for="otp" class="visually-hidden">Enter the OTP received:</label>
  <input type="text" id="otp" name="otp">

  <button type="submit">Submit</button>
</form>

<script>
  function sendOtp() {
    // Simulate sending OTP
    alert('OTP sent to your registered phone number.');
  }
</script>


<!-- 올바른 예시 2 : 생체 인식 및 보안 키 사용 - WebAuthn API를 사용하여 생체 인식 또는 보안 키를 통한 인증 방법을 제공 -->
<form id="webauthnForm">
  <label for="username">Username:</label>
  <input type="text" id="username" name="username">

  <button type="button" onclick="authenticate()">Authenticate using WebAuthn</button>

  <button type="submit">Submit</button>
</form>

<script>
  async function authenticate() {
    // Example of WebAuthn API usage
    try {
      const publicKey = {/* PublicKeyCredentialRequestOptions */};
      const credential = await navigator.credentials.get({publicKey});
      // Process the credential response
      alert('Authentication successful');
    } catch (err) {
      alert('Authentication failed: ' + err);
    }
  }
</script>
```

**검수 방법**
- 다양한 인증 방법이 제공되는지 확인하였는가?   
- 모든 인증 방법이 작동하는지 테스트하였는가?   
- Axe와 같은 접근성 검사 도구를 사용하여 인증 절차의 접근성을 평가하였는가?   
- WAVE 도구를 사용하여 인증 절차의 접근성을 검사하였는가?   
- NVDA, JAWS와 같은 스크린 리더를 사용하여 인증 절차가 올바르게 안내되고 실행되는지 확인하였는가?   
- 인지 기능에 제한이 있는 사용자, 시각 장애인, 청각 장애인 등 다양한 사용자가 인증 절차를 테스트하고 피드백을 제공받았는가?   
- 브라우저의 개발자 도구를 사용하여 HTML 구조와 스크립트를 검사하고, 다양한 인증 방법이 올바르게 구현되었는지 확인하였는가?   


#### 7.3.4. (반복 입력 정보) 반복되는 입력 정보는 자동 입력 또는 선택 입력할 수 있어야 한다.   
> 반복되는 입력 정보를 자동 입력 또는 선택 입력할 수 있게 함으로써 사용자의 편의성을 높이고 입력 오류를 줄일 수 있다. 이는 자동 완성, 드롭다운 목록, 브라우저의 자동 완성 기능 등을 통해 구현할 수 있다.    
WCAG 2.2 Guidelines : [1.4.10 Reflow](https://www.w3.org/TR/WCAG22/#reflow){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : 사용자가 동일한 주소를 반복적으로 입력
<form id="shippingForm">
  <label for="address">Shipping Address:</label>
  <input type="text" id="address" name="address">
  
  <label for="billingAddress">Billing Address:</label>
  <input type="text" id="billingAddress" name="billingAddress">
  
  <button type="submit">Submit</button>
</form>

<!-- 잘못된 예시 2 : 사용자가 국가명을 직접 입력
<form id="countryForm">
  <label for="country">Country:</label>
  <input type="text" id="country" name="country">
  
  <button type="submit">Submit</button>
</form>


<!-- 올바른 예시 1 : "Billing address is the same as shipping address" 체크박스를 선택하면 배송 주소를 자동으로 청구 주소에 복사 -->
<form id="shippingForm">
  <label for="address">Shipping Address:</label>
  <input type="text" id="address" name="address" autocomplete="shipping street-address">
  
  <label>
    <input type="checkbox" id="sameAddress" onclick="copyAddress()"> Billing address is the same as shipping address
  </label>
  
  <label for="billingAddress">Billing Address:</label>
  <input type="text" id="billingAddress" name="billingAddress" autocomplete="billing street-address">
  
  <button type="submit">Submit</button>
</form>

<script>
  function copyAddress() {
    if (document.getElementById('sameAddress').checked) {
      document.getElementById('billingAddress').value = document.getElementById('address').value;
    } else {
      document.getElementById('billingAddress').value = '';
    }
  }
</script>

<!-- 올바른 예시 2 : 드롭다운 목록을 사용하여 사용자가 국가를 선택 -->
<form id="countryForm">
  <label for="country">Country:</label>
  <select id="country" name="country">
    <option value="USA">United States</option>
    <option value="CAN">Canada</option>
    <option value="MEX">Mexico</option>
    <!-- More options can be added here -->
  </select>
  
  <button type="submit">Submit</button>
</form>
```

**검수 방법**
- 자동 입력 또는 선택 입력 기능이 제대로 작동하는지 확인하였는가?   
- 사용자가 반복 입력 정보를 쉽게 입력할 수 있는지 테스트하였는가?   
- Axe, WAVE와 같은 접근성 검사 도구를 사용하여 자동 입력 기능이 접근성을 저해하지 않는지 확인하였는가?   
- NVDA, JAWS와 같은 스크린 리더를 사용하여 자동 입력 또는 선택 입력 기능이 올바르게 안내되고 실행되는지 확인하였는가?   
- 브라우저의 개발자 도구를 사용하여 HTML 구조와 스크립트를 검사하고, 자동 입력 또는 선택 입력 기능이 올바르게 구현되었는지 확인하였는가?   
- 인지 기능에 제한이 있는 사용자, 시각 장애인, 청각 장애인 등 다양한 사용자가 자동 입력 또는 선택 입력 기능을 테스트하고 피드백을 제공하였는가?   


### 견고성 (Robust)

#### 8.1.1. (마크업 오류 방지) 마크업 언어의 요소는 열고 닫음, 중첩 관계 및 속성 선언에 오류가 없어야 한다. 
> HTML 마크업 언어에서 요소는 열고 닫아야 하며, 중첩 관계 및 속성 선언이 정확해야 한다. 이를 통해 문서의 구조를 올바르게 유지하고, 브라우저가 페이지를 정확하게 렌더링할 수 있도록 한다.   
[요소 중첩 | UKKM](https://uxkm.io/publishing/html/02-blockInline/05-element_nesting#gsc.tab=0){: target="_blank"}
HTML5 스펙 문서:[HTML5 Specification](https://html.spec.whatwg.org/multipage/){: target="_blank"}

```sh
<!-- 잘못된 예시 1 : <p> 태그가 닫히지 않아 마크업 오류가 발생
<p>Welcome to our website

<!-- 잘못된 예시 2 :  태그의 중첩이 잘못되어 있는 경우 
<div>
  <p>This is a paragraph.
  <div>This is inside a div.</p>
</div>

<!-- 올바른 예시 1 : 태그를 열고 닫는 마크업 -->
<p>Welcome to our website</p>

<!-- 올바른 예시 2 : 태그의 중첩을 올바르게 하여 구조를 유지 -->
<div>
  <p>This is a paragraph.</p>
  <div>This is inside a div.</div>
</div>
```

**검수 방법**
- HTML Validator 사용: W3C HTML Validator와 같은 도구를 사용하여 마크업 오류를 자동으로 검수하였습니까?     
- 브라우저 개발자 도구 사용: 브라우저의 개발자 도구(예: Chrome DevTools)를 사용하여 HTML 구조를 확인하였습니까?     
- 수동 검사: HTML 코드를 수동으로 검토하여 태그의 열고 닫음, 중첩 관계, 속성 선언을 확인하였습니까?     


#### 8.2.1. (웹 애플리케이션 접근성 준수) 콘텐츠에 포함된 웹 애플리케이션은 접근성이 있어야 한다. 
> 웹사이트, 도구, 기술이 장애를 가진 사람들도 포함하여 모든 사용자에게 접근 가능하도록 설계되는 것을 의미한다.    
웹 콘텐츠 접근성 지침(WCAG) 개요 : [WAI](https://www.w3.org/WAI/standards-guidelines/wcag/){: target="_blank"}      
WCAG 2.2 Guidelines : [WCAG22](https://www.w3.org/TR/WCAG22/){: target="_blank"}   

```sh
<!-- 잘못된 예시 1 : 버튼에 대체 텍스트가 없어 스크린 리더 사용자에게 혼란을 줄 수 있는 경우 
<button onclick="submitForm()">Submit</button>

<!-- 잘못된 예시 2 : 버튼의 상태 변화(예: 메뉴 열림/닫힘)에 대한 정보를 미제공 한 경우 
<button onclick="toggleMenu()">Menu</button>

<!-- 올바른 예시 1 : aria-label 속성을 사용하여 스크린 리더 사용자에게 버튼의 용도를 설명 -->
<button onclick="submitForm()" aria-label="Submit form">Submit</button>

<!-- 올바른 예시 2 : aria-expanded와 aria-controls 속성을 사용하여 버튼 상태와 관련된 정보를 제공 -->
<button onclick="toggleMenu()" aria-expanded="false" aria-controls="menu">Menu</button>
<nav id="menu" hidden>
  <!-- Menu content -->
</nav>

<script>
  function toggleMenu() {
    var button = document.querySelector('button');
    var menu = document.getElementById('menu');
    var expanded = button.getAttribute('aria-expanded') === 'true' || false;
    
    button.setAttribute('aria-expanded', !expanded);
    menu.hidden = expanded;
  }
</script>
```

**검수 방법**
- 자동화 도구 사용: 접근성 자동화 검사 도구(예: Axe, WAVE)를 사용하여 페이지를 분석하고 문제점을 발견하였습니까?     
- 스크린 리더 테스트: NVDA, JAWS와 같은 스크린 리더를 사용하여 웹 애플리케이션이 제대로 읽히는지 확인하였습니까?     
- 키보드 네비게이션 테스트: 마우스 없이 키보드만으로 웹 애플리케이션을 사용할 수 있는지 확인하였습니까?     
- 색 대비 검사: 텍스트와 배경 색상의 대비가 충분한지 확인하였습니까?     
- 수동 검사: WCAG 지침을 참고하여 수동으로 접근성을 검토하였습니까?     





#### 웹 접근성 요약 보고서
<table>
<thead>
<tr>
<th scope="col">지침(14개)</th><th scope="col">검사항목(33개)</th><th scope="col">준수 여부</th>
</tr>
</thead>
<tbody>
<tr>
<td>5.1. 대체 텍스트</td><td>5.1.1. (적절한 대체 텍스트 제공) 텍스트 아닌 콘텐츠는 그 의미나 용도를 인식할 수 있도록 대체 텍스트를 제공해야 한다.</td><td></td>
</tr>
<tr>
<td>5.2. 멀티미디어 대체수단</td><td>5.2.1. (자막 제공) 멀티미디어 콘텐츠에는 자막, 대본 또는 수어를 제공해야 한다.</td><td></td>
</tr>
<tr>
<td>5.3. 적응성</td><td>5.3.1. (표의 구성) 표는 이해하기 쉽게 구성해야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>5.3.2. (콘텐츠의 선형구조) 콘텐츠는 논리적인 순서로 제공해야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>5.3.3. (명확한 지시사항 제공) 지시사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td>5.4. 명료성</td><td>5.4.1. (색에 무관한 콘텐츠 인식) 콘텐츠는 색에 관계없이 인식될 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>5.4.2. (자동 재생 금지) 자동으로 소리가 재생되지 않아야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>5.4.3. (텍스트 콘텐츠의 명도 대비) 텍스트 콘텐츠와 배경 간의 명도대비는 4.5 대 1 이상이어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>5.4.4. (콘텐츠 간의 구분) 이웃한 콘텐츠는 구별될 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td>6.1. 입력장치 접근성</td><td>6.1.1. (키보드 사용 보장) 모든 기능은 키보드만으로도 사용할 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.1.2. (초점 이동과 표시) 키보드에 의한 초점은 논리적으로 이동해야 하며, 시각적으로 구별할 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.1.3. (조작 가능) 사용자 입력 및 콘트롤은 조작 가능하도록 제공되어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.1.4. (문자 단축키) 문자 단축키는 오동작으로 인한 오류를 방지하여야 한다.</td><td></td>
</tr>
<tr>
<td>6.2. 충분한 시간 제공</td><td>6.2.1. (응답시간 조절) 시간제한이 있는 콘텐츠는 응답시간을 조절할 수 있어야 한다.</td><td></td> 
</tr>
<tr>
<td></td><td>6.2.2. (정지 기능 제공) 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td>6.3. 광과민성 발작 예방</td><td>6.3.1. (깜빡임과 번쩍임 사용 제한) 초당 3~50회 주기로 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.</td><td></td>
</tr>
<tr>
<td>6.4 쉬운 내비게이션</td><td>6.4.1. (반복 영역 건너뛰기) 콘텐츠의 반복되는 영역은 건너뛸 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.4.2. (제목 제공) 페이지, 프레임, 콘텐츠 블록에는 적절한 제목을 제공해야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.4.3. (적절한 링크 텍스트) 링크 텍스트는 용도나 목적을 이해할 수 있도록 제공해야 한다.</td><td></td> 
</tr>
<tr>
<td></td><td>6.4.4. (고정된 참조 위치 정보) 전자출판문서 형식의 웹 페이지는 각 페이지로 이동할 수 있는 기능이 있어야 하고, 서식이나 플랫폼에 상관없이 참조 위치 정보를 일관되게 제공ㆍ유지해야 한다.</td><td></td>
</tr>
<tr>
<td>6.5. 입력 방식</td><td>6.5.1. (단일 포인터 입력 지원) 다중 포인터 또는 경로기반 동작을 통한 입력은 단일 포인터 입력으로도 조작할 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.5.2. (포인터 입력 취소) 단일 포인터 입력으로 실행되는 기능은 취소할 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.5.3. (레이블과 네임) 텍스트 또는 텍스트 이미지가 포함된 레이블이 있는 사용자 인터페이스 구성요소는 네임에 시각적으로 표시되는 해당 텍스트를 포함해야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>6.5.4. (동작기반 작동) 동작기반으로 작동하는 기능은 사용자 인터페이스 구성요소로 조작할 수 있고, 동작기반 기능을 비활성화할 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td>7.1. 가독성</td><td>7.1.1. (기본 언어 표시) 주로 사용하는 언어를 명시해야 한다.</td><td></td>
</tr>
<tr>
<td>7.2. 예측 가능성</td><td>7.2.1. (사용자 요구에 따른 실행) 사용자가 의도하지 않은 기능(새 창, 초점에 의한 맥락 변화 등)은 실행되지 않아야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>7.2.2. (찾기 쉬운 도움 정보) 도움 정보가 제공되는 경우, 각 페이지에서 동일한 상대적인 순서로 접근할 수 있어야 한다.</td><td></td>
</tr>
<tr>
<td>7.3. 입력 도움</td><td>7.3.1. (오류 정정) 입력 오류를 정정할 수 있는 방법을 제공해야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>7.3.2. (레이블 제공) 사용자 입력에는 대응하는 레이블을 제공해야 한다.</td><td></td>
</tr>
<tr>
<td></td><td>7.3.3. (접근 가능한 인증) 인증 과정은 인지 기능 테스트에만 의존해서는 안 된다.</td><td></td>  
</tr>
<tr>
<td></td><td>7.3.4. (반복 입력 정보) 반복되는 입력 정보는 자동 입력 또는 선택 입력할 수 있어야 한다.</td><td></td>  
</tr>
<tr>
<td>8.1. 문법 준수</td><td>8.1.1. (마크업 오류 방지) 마크업 언어의 요소는 열고 닫음, 중첩 관계 및 속성 선언에 오류가 없어야 한다.</td><td></td>
</tr>
<tr>
<td>8.2. 웹 애플리케이션 접근성</td><td>8.2.1. (웹 애플리케이션 접근성 준수) 콘텐츠에 포함된 웹 애플리케이션은 접근성이 있어야 한다.</td><td></td>
</tr>
</tbody>
</table>

### 참조
- [W3C WCAG 1.0](https://www.w3.org/TR/WCAG10/){: target="_blank"}
- [W3C WCAG 2.0](https://www.w3.org/TR/WCAG20/){: target="_blank"}
- [W3C WCAG 2.1](https://www.w3.org/TR/WCAG21/){: target="_blank"}
- [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/){: target="_blank"}
- [W3C WCAG 3.0 Draft](https://www.w3.org/TR/2021/WD-wcag-3.0-20210121/){: target="_blank"}
- [W3C WCAG 2.1 한국어](http://www.kwacc.or.kr/WAI/wcag21/){: target="_blank"}
- [W3C Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/){: target="_blank"}
- [W3C WCAG2 ko](https://www.w3.org/WAI/standards-guidelines/ko#wcag2){: target="_blank"}
- [W3C Accessibility Guidelines Working Group](https://www.w3.org/WAI/GL/){: target="_blank"}
- [W3C Techniques for WCAG 2.1](https://www.w3.org/WAI/WCAG21/Techniques/){: target="_blank"}
- [W3C W3C 접근성의 4가지 원칙](https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head){: target="_blank"}
- [MDN 웹 컨텐츠 접근성 지침 이해하기](https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG){: target="_blank"}
- [MDN 접근성이란?](https://developer.mozilla.org/ko/docs/Learn/Accessibility/What_is_accessibility#accessibility_guidelines_and_the_law){: target="_blank"}
- [NULI WCAG 2.2에서 변경된 사항](https://nuli.navercorp.com/community/article/1133181){: target="_blank"}
- [brunch WCAG 2.2 작업 초안](https://brunch.co.kr/@snclab/55){: target="_blank"}
- [GITBOOK WCAG 2.1](https://a11y.gitbook.io/wcag/international-standards){: target="_blank"}
- [WAI 문서로 접근성 이해하기](https://iyu88.github.io//a11y/2023/12/24/web-accessibility-1.html){: target="_blank"}
- [deque blog WCAG 2.1](https://www.deque.com/blog/wcag-2-1-what-is-next-for-accessibility-guidelines/){: target="_blank"}
- [웹접근성 국가표준 개정 소개](https://seculayerlab.tistory.com/m/48){: target="_blank"}
- [한국형 웹 콘텐츠 접근성 지침 2.2](https://www.samsungfashion.com/webacc.do){: target="_blank"}
- [AOA GITBOOK](https://aoa.gitbook.io/skymimo/undefined){: target="_blank"}




