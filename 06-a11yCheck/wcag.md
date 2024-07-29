## 접근성 체크리스트

**웹 콘텐츠 접근성**
> 웹 콘텐츠를 시각 장애, 저시력 장애, 청각 장애, 지체 장애, 학습 장애, 지적 장애, 뇌병변 장애, 광과민성 증후 등 다양한 장애를 가진 사용자들이 쉽게 접근할 수 있도록 구축하는 방법에는 몇 가지 중요한 원칙과 지침이 있습니다. 이러한 원칙과 지침은 장애인 사용자가 비장애인 사용자와 동등하게 인터넷을 이용할 수 있도록 돕기 위해 설계되었습니다.   
kwcag 2.1 과 2.2 기준 접근성은 크게 세 가지 주요 구성 요소로 나눌 수 있습니다.    
원칙 (Principles), 지침 (Guidelines), 검사 항목 (Requirements). 원칙은 4 가지 기본 원칙에 기초혀며,    
kwcag 2.1 원칙을 구현하기 위해 13개의 지침을 따라야 하고, 각 지침의 준수 여부를 확인하기 위해 24개의 검사 항목을 마련해야 합니다.    
kwcag 2.2 원칙을 구현하기 위해 14개의 지침을 따라야 하고, 각 지침의 준수 여부를 확인하기 위해 33개의 검사 항목을 마련해야 합니다.    
검사 항목은 구체적인 테스트 가능한 기준을 제공하여 웹사이트가 원칙 및 지침을 준수하고 있는지 확인하는 데 사용됩니다.   
지능정보화기본법 시행규칙 일부개정령(안) 입법예고에 따라 '24.9.1부터 심사기준이 변경되며 이에따라 kwcag 2.2 기준으로 체크리스트를 제공합니다.

### 5. 인식의 용이성 (Perceivable)

#### 5.1.1. (적절한 대체 텍스트 제공) 텍스트 아닌 콘텐츠는 그 의미나 용도를 인식할 수 있도록 대체 텍스트를 제공해야 한다.
> 모든 이미지에는 대체 텍스트를 제공하여야 합니다. 이는 시각 장애인 사용자가 스크린 리더를 통해 이미지의 내용을 이해할 수 있도록 도와줍니다.   
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
> 동영상 및 오디오 콘텐츠에는 자막, 대체 텍스트, 오디오 설명 등을 제공해야 합니다.   
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
- 비디오 플레이어에서 자막이 정상적으로 표시되가?    
- 오디오 설명이 포함된 경우 자막, 대본 또는 수어를 제공하는가?   

#### 5.3.1. (표의 구성) 표는 이해하기 쉽게 구성해야 한다.
> 표는 데이터를 체계적으로 정리하고, 쉽게 이해할 수 있도록 구성해야 합니다.   
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
> 콘텐츠는 논리적인 순서로 제공되어야 합니다.    
모든 사용자가 콘텐츠를 쉽게 탐색하고 이해할 수 있게 합니다.    
논리적인 순서는 시각적으로나 코드 구조적으로나 일관되어야 합니다.   
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
> 웹 콘텐츠나 사용자 인터페이스를 설계할 때, 지시사항이나 안내는 특정 감각적 특성(모양, 크기, 위치, 방향, 색, 소리 등)에 의존하지 않고 명확히 전달되어야 합니다. 즉, 색상에만 의존하여 정보를 전달하는 것이 아니라 텍스트나 다른 시각적 단서도 함께 제공해야 합니다.    
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
- 지시사항이 색상, 위치, 모양 등에 의존하지 않고 텍스트로 명확하게 제공되는지 확인하였는가?    
- 지시사항이 색상이나 소리 이외에도 텍스트로 제공되었는지 확인하였는가?     


#### 5.4.1. (색에 무관한 콘텐츠 인식) 콘텐츠는 색에 관계없이 인식될 수 있어야 한다.
> 콘텐츠는 색에 관계없이 인식될 수 있어야 합니다. 이는 색상에 의존하는 정보 전달을 피해야 하며, 색상만으로는 정보를 전달하지 않도록 합니다.   
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
- 스크린 리더로 콘텐츠를 확인하여 모든 정보가 전달되었는가?   

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
> 웹 페이지에서 보이는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 충분한 대비를 제공하여, 저시력장애인, 색각장애인, 고령자 등도 콘텐츠를 인식할 수 있도록 제공해야 한다.    
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
> 웹 페이지에서 보이는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 충분한 대비를 제공하여, 저시력장애인, 색각장애인, 고령자 등도 콘텐츠를 인식할 수 있도록 제공해야 한다.    
다만, 로고, 장식목적의 콘텐츠, 마우스나 키보드를 활용하여 초점을 받았을 때 명도 대비가 커지는 콘텐츠 등은 예외로 한다.    
WCAG 2.2 Guidelines : [1.4.3 Contrast (Minimum)](https://www.w3.org/TR/WCAG22/#visual-presentation){: target="_blank"}   

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
> 웹 접근성에서 키보드 사용 보장이란 모든 기능이 키보드만으로도 사용할 수 있어야 한다는 것을 의미합니다. 이는 시각 장애나 지체 장애가 있는 사용자들이 마우스를 사용할 수 없는 경우에도 웹 페이지의 모든 기능을 사용할 수 있도록 하기 위함입니다. 키보드 네비게이션, 폼 요소의 접근성, 인터랙티브 요소의 포커스 등이 포함됩니다.    
WCAG 2.2 Guidelines : [2.1.1 Keyboard](https://www.w3.org/TR/WCAG22/#keyboard){: target="_blank"}   

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


#### 6.1.2. (초점 이동과 표시) 키보드에 의한 초점은 논리적으로 이동해야 하며, 시각적으로 구별할 수 있어야 한다.

#### 6.1.3. (조작 가능) 사용자 입력 및 콘트롤은 조작 가능하도록 제공되어야 한다.

#### 6.1.4 (문자 단축키) 문자 단축키는 오동작으로 인한 오류를 방지하여야 한다.

#### 6.2.1. (응답시간 조절) 시간제한이 있는 콘텐츠는 응답시간을 조절할 수 있어야 한다.

#### 6.2.2. (정지 기능 제공) 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.

#### 6.3.1. (깜빡임과 번쩍임 사용 제한) 초당 3~50회 주기로 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.

#### 6.4.4. (고정된 참조 위치 정보) 전자출판문서 형식의 웹 페이지는 각페이지로 이동할 수 있는 기능이 있어야 하고, 서식이나 플랫폼에 상관없이 참조 위치 정보를 일관되게 제공ㆍ유지해야 한다.

#### 6.5.1. (단일 포인터 입력 지원) 다중 포인터 또는 경로기반 동작을 통한 입력은 단일 포인터 입력으로도 조작할 수 있어야 한다.

#### 6.5.2. (포인터 입력 취소) 단일 포인터 입력으로 실행되는 기능은 취소할 수 있어야 한다.

#### 6.5.3. (레이블과 네임) 텍스트 또는 텍스트 이미지가 포함된 레이블이 있는 사용자 인터페이스 구성요소는 네임에 시각적으로 표시되는 해당 텍스트를 포함해야 한다.

#### 6.5.4. (동작기반 작동) 동작기반으로 작동하는 기능은 사용자 인터페이스 구성요소로 조작할 수 있고, 동작기반 기능을 비활성화할 수 있어야 한다.


### 이해의 용이성 (Understandable)

#### 7.1.1. (기본 언어 표시) 주로 사용하는 언어를 명시해야 한다. 

#### 7.2.1. (사용자 요구에 따른 실행) 사용자가 의도하지 않은 기능(새 창, 초점에 의한 맥락 변화 등)은 실행되지 않아야 한다. 

#### 7.2.2. (찾기 쉬운 도움 정보) 도움 정보가 제공되는 경우, 각 페이지에서 동일한 상대적인 순서로 접근할 수 있어야 한다.

#### 7.3.1. (오류 정정) 입력 오류를 정정할 수 있는 방법을 제공해야 한다. 
> 입력 오류 정정은 사용자가 폼이나 입력 필드에서 오류를 발생시켰을 때, 이를 사용자에게 알리고 수정할 수 있는 방법을 제공하는 것을 의미합니다.   
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

#### 7.3.3. (접근 가능한 인증) 인증 과정은 인지 기능 테스트에만 의존해서는 안 된다.  

#### 7.3.4. (반복 입력 정보) 반복되는 입력 정보는 자동 입력 또는 선택 입력할 수 있어야 한다.   


### 견고성 (Robust)

#### 8.1.1. (마크업 오류 방지) 마크업 언어의 요소는 열고 닫음, 중첩 관계 및 속성 선언에 오류가 없어야 한다. 
> HTML 마크업 언어에서 요소는 열고 닫아야 하며, 중첩 관계 및 속성 선언이 정확해야 합니다. 이를 통해 문서의 구조를 올바르게 유지하고, 브라우저가 페이지를 정확하게 렌더링할 수 있도록 합니다.   
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
> 웹사이트, 도구, 기술이 장애를 가진 사람들도 포함하여 모든 사용자에게 접근 가능하도록 설계되는 것을 의미합니다.    
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




