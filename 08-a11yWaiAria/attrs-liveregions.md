# WAI-ARIA 상태 및 속성
> WAI-ARIA 상태 및 속성은 웹 애플리케이션의 접근성을 향상시키기 위해 HTML 요소에 추가적인 의미와 기능을 부여하는 메커니즘입니다. 이 섹션에서는 다양한 WAI-ARIA 속성과 상태를 설명하고, 이를 위젯, 라이브 리전, 드래그 앤 드롭, 관계 관련 기능에 적용하는 방법을 다룹니다.    
이 속성과 상태들은 WAI-ARIA가 웹 애플리케이션의 접근성을 강화하기 위해 제공하는 중요한 도구입니다. 이들을 적절하게 사용하면 시각적 장애를 가진 사용자도 웹 콘텐츠와 상호작용할 수 있으며, 동적인 콘텐츠 변경 사항을 쉽게 인지할 수 있습니다. 이를 통해 웹 접근성을 크게 개선할 수 있습니다.   

## Live Region Attributes (라이브 리전 속성)
> Live Region 속성은 웹 접근성에서 중요한 역할을 합니다. 특히, 화면 판독기(screen reader)를 사용하는 사용자에게 동적인 콘텐츠 업데이트를 효율적으로 알리는 데 사용됩니다. 이러한 속성들은 DOM이 변경되었을 때 페이지 전체를 새로고침하지 않고도 업데이트된 내용을 사용자에게 전달할 수 있도록 도와줍니다.    
[WAI-ARIA Live Region Attributes](https://www.w3.org/TR/wai-aria-1.2/#live_region_roles){: target="_blank"}   
[MDN: ARIA Live Regions](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions){: target="_blank"}   

**주요 Live Region 속성**   
1. **aria-live**: 이 속성은 특정 요소 내에서 콘텐츠가 변경될 때 사용자에게 그 변경사항을 알릴지 여부와 그 방식(긴급도)을 지정합니다. 주요 값으로는 off, polite, assertive가 있습니다.   
    - **off**: 변경된 내용을 알리지 않습니다.   
    - **assertive**: 즉각적으로 콘텐츠 변경을 알립니다.    
    - **polite**: 콘텐츠 변경이 발생하면 다른 사용자 작업이 끝난 후에 알립니다.   
2. **aria-atomic**: 이 속성은 aria-live 속성과 함께 사용되며, true로 설정하면 변경된 요소의 전체 콘텐츠를 알리고, false로 설정하면 변경된 부분만 알립니다.      
3. **aria-relevant**: 이 속성은 어떤 종류의 변경이 사용자에게 알릴지 설정합니다. 값으로는 additions, removals, text, all 등이 있습니다.   
4. **aria-busy**: 이 속성은 특정 영역이 아직 업데이트 중임을 나타냅니다. 사용자가 이 영역을 인터랙션하기 전에 작업이 완료될 때까지 기다리도록 합니다.   
   
**추천하는 활용 방법**
1. **aria-live**   
- aria-live 속성은 화면 리더가 특정 요소의 내용이 변경될 때 이를 사용자에게 알리도록 지시합니다. 이 속성은 실시간으로 업데이트되는 콘텐츠에 주로 사용됩니다.   
- 활용 추천: 실시간으로 변화하는 콘텐츠(예: 채팅 메시지, 알림 배너, 실시간 업데이트)에서 aria-live="polite" 또는 aria-live="assertive"를 사용해 사용자에게 적절한 시점에 변경 사항을 알리도록 설정합니다. "polite"는 중요한 정보가 아니거나, 방해하지 않고 알리고자 할 때 사용하고, "assertive"는 중요한 정보로 즉시 알릴 필요가 있을 때 사용합니다.   
2. **aria-atomic**   
- aria-atomic 속성은 특정 요소의 일부 내용이 변경될 때 전체 요소를 화면 리더가 다시 읽어줄지 여부를 결정합니다.   
- 활용 추천: 요소의 일부 변경 사항이 전체 의미에 영향을 줄 때 aria-atomic="true"를 사용합니다. 예를 들어, 알림 메시지의 일부가 변경되었을 때, 사용자가 그 전체를 다시 읽을 필요가 있다면 이 속성을 적용해 전체 내용을 재알림하도록 할 수 있습니다.    
3. **aria-relevant**   
- aria-relevant 속성은 aria-live 영역 내에서 화면 리더가 어떤 유형의 변경 사항을 사용자에게 알릴지 결정합니다. 이 속성은 추가, 삭제, 텍스트 변경 등을 포함합니다.   
- 활용 추천: 예를 들어, 요소에 새로운 정보가 추가되거나 삭제될 때만 알리고자 한다면 aria-relevant="additions removals"를 설정합니다. 실시간으로 변경되는 데이터 중에서 특정한 변경 사항만 사용자가 알 수 있도록 제한할 수 있습니다.    
4. **aria-busy**    
- aria-busy 속성은 현재 요소나 해당 요소 내의 콘텐츠가 로딩 중임을 나타냅니다. 이 속성을 사용하면 화면 리더는 콘텐츠가 완전히 로딩될 때까지 사용자가 이를 상호작용하지 않도록 합니다.    
- 활용 추천: 복잡한 콘텐츠가 로딩 중일 때, 예를 들어 동적인 리스트나 데이터 테이블이 완전히 로딩될 때까지 aria-busy="true"를 설정하여 사용자가 불완전한 정보와 상호작용하지 않도록 합니다. 로딩이 완료되면 aria-busy="false"로 설정합니다.    
5. **결론**   
- aria-live 속성이 다양한 상황에서 가장 자주 사용될 가능성이 높습니다. 실시간으로 콘텐츠가 업데이트되는 상황에서 유용하며, 적절한 알림을 통해 사용자 경험을 향상시킬 수 있습니다.   
- aria-busy 역시 복잡한 동적 콘텐츠를 다룰 때 매우 중요한 속성입니다. 콘텐츠가 로딩 중인 경우 사용자가 혼란을 겪지 않도록 보호할 수 있습니다.    
- 상황에 맞게 이 속성들을 조합하여 사용하면 웹 접근성을 크게 개선할 수 있습니다.   

### **1. aria-atomic (property)**    
aria-atomic 속성은 WAI-ARIA(Accessible Rich Internet Applications)의 속성 중 하나로, live region 내에서 콘텐츠가 변경될 때 스크린 리더가 사용자에게 전체 내용을 읽어줄지, 아니면 변경된 부분만 읽어줄지를 제어합니다. aria-atomic 속성을 적절히 사용하여 웹 접근성을 높일 수 있습니다.   
[WAI-ARIA 1.2 Specification (aria-atomic)](https://www.w3.org/TR/wai-aria-1.2/#aria-atomic){: target="_blank"}   
[MDN Web Docs (aria-atomic)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-atomic){: target="_blank"}   

**aria-atomic 속성 값**  
- **true**: 요소 내에서 콘텐츠가 변경될 때 스크린 리더가 전체 요소의 내용을 읽어줍니다.   
- **false (기본값)**: 변경된 부분만 스크린 리더가 읽어줍니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, p, section, article 등 대부분의 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: alert, status, log, marquee, timer 등 live region과 관련된 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **적절한 사용 환경**: 모든 콘텐츠를 읽어주는 것이 사용자의 경험을 향상시킬 때만 aria-atomic="true"를 사용해야 합니다. 불필요하게 전체 내용을 읽는 것은 오히려 사용자의 혼란을 야기할 수 있습니다.
- **성능 이슈**: aria-atomic="true"는 스크린 리더가 전체 요소를 다시 읽게 만들기 때문에, 복잡하거나 큰 콘텐츠에서는 성능 이슈를 유발할 수 있습니다.    


**잘못된 예시**
사용자가 날씨에 대한 추가 정보(기온)을 듣기 위해 aria-atomic="true"가 필요하지 않음에도 불구하고, 전체 내용을 다시 읽게 됩니다. 단순히 추가된 정보만 전달하는 것이 더 바람직합니다.    
```sh
<div aria-live="polite" aria-atomic="true">
  <p>현재 날씨: 맑음</p>
</div>
<script>
  setTimeout(() => {
    document.querySelector('div').innerHTML = '<p>현재 날씨: 맑음, 기온: 25도</p>';
  }, 2000);
</script>
```

**올바른 예시**
이 경우 aria-atomic="false"가 적절합니다. 사용자는 변동된 부분(기온)을 듣기만 하면 되기 때문에 전체 내용을 다시 듣지 않아도 됩니다.    
```sh
<div aria-live="polite" aria-atomic="false">
  <p>현재 날씨: <span id="weather">맑음</span>, 기온: <span id="temperature">22도</span></p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('temperature').textContent = '25도';
  }, 2000);
</script>
```

**aria-atomic="true" 사용 예시 - 사용자가 전체 업데이트된 정보를 필요로 할 때:**
전체 상태를 다시 읽어주는 것이 적절할 때 사용합니다.    
```sh
<div aria-live="assertive" aria-atomic="true">
  <p>현재 작업 상태: <span id="status">대기 중</span></p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('status').textContent = '완료됨';
  }, 3000);
</script>
```

**aria-atomic="false" 사용 예시 - 일부 정보만 업데이트되었을 때**
새 메시지만 전달되는 것이 목적이므로, 변경된 부분만 알립니다.    
```sh
<div aria-live="polite" aria-atomic="false">
  <p>새 메시지: <span id="message">메시지가 없습니다.</span></p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('message').textContent = '새로운 메시지가 도착했습니다.';
  }, 2000);
</script>
```

**시멘틱 구조의 예시**
이 구조에서는 서버 상태의 모든 변화를 사용자에게 알리는 것이 중요하기 때문에 aria-atomic="true"가 적절합니다. 스크린 리더는 전체 상태를 다시 읽어줍니다.    
```sh
<article role="log" aria-live="polite" aria-atomic="true">
  <header>
    <h2>업데이트 로그</h2>
  </header>
  <div id="log-content">
    <p>서버 상태: 안정적</p>
  </div>
</article>
<script>
  setTimeout(() => {
    document.getElementById('log-content').innerHTML = '<p>서버 상태: 연결 끊김, 자동 복구 시도 중</p>';
  }, 5000);
</script>
```

### **2. aria-busy (state)**    
aria-busy는 WAI-ARIA(Accessible Rich Internet Applications)에서 정의된 상태(state) 속성 중 하나로, 특정 요소가 아직 콘텐츠를 로드하거나 처리 중임을 나타냅니다. 이 속성은 사용자가 해당 영역을 상호작용하려 할 때, 작업이 완료되지 않았음을 알리기 위해 사용됩니다. 주로 AJAX 요청이나 비동기적인 작업이 수행되는 동안 사용됩니다. aria-busy 속성을 적절하게 활용하여 웹 접근성을 높일 수 있습니다.   
[WAI-ARIA 1.2 Specification (aria-busy)](https://www.w3.org/TR/wai-aria-1.2/#aria-busy){: target="_blank"}   
[MDN Web Docs (aria-busy)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-busy){: target="_blank"}   

**aria-busy 속성 값**  
- **true**: 요소가 아직 로딩 중이거나 처리 중임을 나타냅니다. 스크린 리더는 이 상태를 감지하여 사용자가 해당 요소와 상호작용하는 것을 방지하거나 주의를 줄 수 있습니다.    
- **false (기본값)**: 요소가 현재 로딩 중이 아님을 나타냅니다. 작업이 완료되어 사용자와 상호작용할 준비가 되었음을 의미합니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, section, article, form, table, ul 등 거의 모든 HTML 요소에서 사용 가능.   
- **연관된 역할**: region, alert, dialog, status, log 등 다양한 ARIA 역할과 함께 사용될 수 있습니다.    

**사용 시 주의사항**   
- **작업 상태 표시**: aria-busy="true"를 설정한 후, 해당 작업이 완료되면 반드시 aria-busy="false"로 업데이트해야 합니다. 그렇지 않으면 사용자가 해당 요소를 계속 바쁘다고 인식하게 되어 접근성에 문제가 생길 수 있습니다.
- **동작 완료 시점**: 비동기 작업이 완료되면 반드시 aria-busy 속성을 false로 설정하여 화면 판독기가 이 정보를 인식할 수 있도록 해야 합니다.    


**잘못된 예시**
작업이 완료된 후에도 aria-busy="true" 상태가 유지되어, 사용자는 계속해서 요소가 바쁘다고 인식하게 됩니다.    
```sh
<div id="content" aria-busy="true">
  <p>데이터를 로드 중입니다...</p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('content').innerHTML = '<p>데이터 로드 완료.</p>';
    // aria-busy="false"로 설정하는 것을 잊음
  }, 3000);
</script>
```

**올바른 예시**
작업이 완료되면 aria-busy를 false로 설정하여 화면 판독기가 사용자가 이 영역과 상호작용할 수 있음을 알 수 있도록 합니다.    
```sh
<div id="content" aria-busy="true">
  <p>데이터를 로드 중입니다...</p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('content').innerHTML = '<p>데이터 로드 완료.</p>';
    document.getElementById('content').setAttribute('aria-busy', 'false');
  }, 3000);
</script>
```

**페이지 섹션이 로드 중일 때**
대시보드가 로드 중일 때 aria-busy="true"를 설정하고, 로드가 완료되면 false로 변경합니다.    
```sh
<section id="dashboard" aria-busy="true">
  <p>대시보드를 로드 중입니다...</p>
</section>
<script>
  // 예를 들어, AJAX 호출 완료 후
  setTimeout(() => {
    document.getElementById('dashboard').innerHTML = '<p>대시보드 로드 완료.</p>';
    document.getElementById('dashboard').setAttribute('aria-busy', 'false');
  }, 4000);
</script>
```

**비동기 데이터 업데이트 예시**
비동기적으로 데이터를 갱신하는 동안 aria-busy="true"를 설정하고, 갱신이 완료되면 false로 변경합니다.    
```sh
<div id="data-section" aria-busy="true">
  <p>데이터를 갱신 중입니다...</p>
</div>
<script>
  // 데이터 갱신 완료 시
  setTimeout(() => {
    document.getElementById('data-section').innerHTML = '<p>데이터 갱신 완료.</p>';
    document.getElementById('data-section').setAttribute('aria-busy', 'false');
  }, 2000);
</script>
```

**시멘틱 구조의 예시**
업데이트 로그 섹션이 로드 중일 때 사용자가 해당 섹션이 아직 작업 중임을 알 수 있도록 aria-busy="true"를 사용합니다. 로드가 완료되면 false로 설정하여 사용자가 해당 영역을 탐색할 수 있게 합니다.    
```sh
<section role="region" aria-labelledby="updates" aria-busy="true">
  <h2 id="updates">업데이트 로그</h2>
  <div id="log">
    <p>최신 업데이트를 로드 중입니다...</p>
  </div>
</section>
<script>
  setTimeout(() => {
    document.getElementById('log').innerHTML = '<p>업데이트 로드 완료.</p>';
    document.querySelector('[role="region"]').setAttribute('aria-busy', 'false');
  }, 5000);
</script>
```

### **3. aria-live (property)**    
aria-live 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 사용되는 속성으로, 특정 영역의 콘텐츠가 동적으로 변경될 때, 스크린 리더가 사용자에게 그 변경 내용을 자동으로 알릴지 여부를 제어합니다. 이 속성은 웹 페이지에서 실시간으로 업데이트되는 콘텐츠(예: 채팅 메시지, 알림, 뉴스 피드 등)에 대한 접근성을 향상시키기 위해 사용됩니다. aria-live 속성을 효과적으로 활용하여 웹 접근성을 개선할 수 있습니다.   
[WAI-ARIA 1.2 Specification (aria-live)](https://www.w3.org/TR/wai-aria-1.2/#aria-live){: target="_blank"}   
[MDN Web Docs (aria-live)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-live){: target="_blank"}   

**aria-live 속성 값**  
- **off**: 콘텐츠가 변경되어도 스크린 리더가 사용자에게 그 변화를 알리지 않습니다. (기본값)   
- **polite**: 콘텐츠가 변경되면, 스크린 리더는 사용자가 현재 작업 중인 내용을 방해하지 않고, 다른 작업이 완료된 후에 변경 내용을 알립니다.   
- **assertive**: 콘텐츠가 변경되면, 스크린 리더가 즉시 그 변경 내용을 사용자에게 알립니다. 현재 작업 중인 내용을 방해할 수 있습니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, p, section, article 등 대부분의 HTML 요소에서 사용 가능.   
- **연관된 역할**: alert, status, log, marquee, timer 등 live region과 관련된 ARIA 역할과 함께 사용될 수 있습니다.    

**사용 시 주의사항**   
- **적절한 값 선택**: polite와 assertive의 선택은 상황에 따라 다릅니다. 일반적으로 사용자에게 중요한 정보(예: 오류 메시지)일 때는 assertive를 사용하고, 그렇지 않은 경우는 polite를 사용하는 것이 좋습니다.    
- **불필요한 알림 방지**: aria-live 속성의 남용은 사용자가 불필요한 정보로 인해 혼란스러워질 수 있으므로, 실질적으로 중요한 정보에만 이 속성을 적용해야 합니다.    


**잘못된 예시**
시계가 매초 업데이트되면서 스크린 리더가 계속해서 사용자를 방해하게 됩니다. assertive 대신 off나 polite가 적절합니다.    
```sh
<div aria-live="assertive">
  <p>현재 시각: 12:00 PM</p>
</div>
<script>
  setInterval(() => {
    document.querySelector('div p').textContent = '현재 시각: ' + new Date().toLocaleTimeString();
  }, 1000);
</script>
```

**올바른 예시**
새 메시지가 도착했을 때 polite 속성을 사용하여 스크린 리더가 다른 작업을 방해하지 않고 알림을 전달합니다.    
```sh
<div aria-live="polite">
  <p id="notification">알림이 없습니다.</p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('notification').textContent = '새 메시지가 도착했습니다.';
  }, 5000);
</script>
```

**aria-live="off" 사용 예시**
화면 판독기 사용자에게 중요하지 않은 정보의 변경사항이 있을 때 aria-live="off"를 사용합니다.    
```sh
<div aria-live="off">
  <p>이 영역의 업데이트는 화면 판독기로 알리지 않습니다.</p>
</div>
```

**aria-live="polite" 사용 예시**
날씨 정보처럼 사용자가 알아야 하지만 즉시 알릴 필요는 없는 정보에 적합합니다.    
```sh
<div aria-live="polite">
  <p id="weather-update">날씨 정보: 맑음</p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('weather-update').textContent = '날씨 정보: 흐림, 기온 20도';
  }, 3000);
</script>
```

**aria-live="assertive" 사용 예시**
즉각적인 주의가 필요한 오류 메시지나 경고에는 assertive를 사용하여 사용자에게 즉시 알립니다.    
```sh
<div aria-live="assertive">
  <p id="error-message">오류가 발생했습니다.</p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('error-message').textContent = '서버 연결 실패. 다시 시도하세요.';
  }, 2000);
</script>
```

**시멘틱 구조의 예시**
시스템 알림처럼 즉각적인 반응이 필요한 상황에서는 aria-live="assertive"를 사용합니다. 사용자는 중요한 시스템 상태 변경 사항을 즉시 인식할 수 있습니다.    
```sh
<article role="alert" aria-live="assertive">
  <header>
    <h2>시스템 알림</h2>
  </header>
  <p id="system-update">시스템 상태: 정상 운영 중</p>
</article>
<script>
  setTimeout(() => {
    document.getElementById('system-update').textContent = '시스템 상태: 긴급 유지보수 필요';
  }, 5000);
</script>
```

**키패드 응용 예시**
aria-live="assertive"사용하여 사용자가 버튼을 클릭할 때 메시지가 여기에 업데이트됩니다. aria-live="assertive"는 화면 판독기(스크린 리더) 사용자에게 즉시 메시지를 읽어주도록 합니다. 숫자 입력과 관련된 간단한 사용자 인터페이스를 구현하는 데 사용될 수 있으며, 특히 키패드를 이용한 비밀번호 입력 같은 상황에 유용할 수 있습니다.    
```sh
<div class="keypad">
    <div class="keynumber">
        <!-- 숫자 버튼 -->
        <button type="button" class="number">0</button>
        <button type="button" class="number">1</button>
        <button type="button" class="number">2</button>
        <button type="button" class="number">3</button>
        <button type="button" class="number">4</button>
        <button type="button" class="number">5</button>
        <button type="button" class="number">6</button>
        <button type="button" class="number">7</button>
        <button type="button" class="number">8</button>
        <button type="button" class="number">9</button>
        <!-- 기능 버튼 -->
        <button type="button" class="number clear">지우기</button>
        <button type="button" class="number rearr">재배열</button>
        <button type="button" class="number confirm">확인</button>
    </div>
    <p class="message" aria-live="assertive"></p>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const numbers = document.querySelectorAll('.number');
    const messageBox = document.querySelector('.message');
    let inputCount = 0;

    function updateVoiceMessage(text) {
        messageBox.textContent = text;
        messageBox.style.visibility = 'visible'; // 메시지 박스를 보이게 함
    }

    numbers.forEach(button => {
        button.addEventListener('click', function() {
            if (this.classList.contains('clear')) {
                inputCount = 0;
                updateVoiceMessage("입력이 초기화되었습니다.");
            } else if (this.classList.contains('rearr')) {
                // 여기에 재배열 로직 추가 (예제에서는 생략)
            } else if (this.classList.contains('confirm')) {
                // 여기에 확인 로직 추가 (예제에서는 생략)
                updateVoiceMessage("입력이 확인되었습니다.");
            } else {
                if(inputCount < 7) {
                    inputCount++;
                    updateVoiceMessage(`총 7자리 중 ${inputCount}번째 입력`);
                } else {
                    updateVoiceMessage("최대 입력 개수에 도달했습니다.");
                }
            }
        });
    });
});
</script>
```

### **4. aria-relevant (property)**    
aria-relevant 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 정의된 속성으로, aria-live 속성과 함께 사용됩니다. 이 속성은 live region 내에서 어떤 종류의 변경 사항이 사용자에게 전달될지를 정의합니다. 예를 들어, 요소가 추가, 제거, 또는 변경되었을 때 이를 스크린 리더가 사용자에게 어떻게 알릴지 설정하는 데 사용됩니다. aria-relevant 속성을 적절하게 활용하여 웹 접근성을 개선할 수 있습니다.   
[WAI-ARIA 1.2 Specification (aria-relevant)](https://www.w3.org/TR/wai-aria-1.2/#aria-relevant){: target="_blank"}   
[MDN Web Docs (aria-relevant)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-relevant){: target="_blank"}   

**aria-relevant 속성 값**  
- **additions**: 요소가 추가되었을 때 스크린 리더가 이를 사용자에게 알립니다.   
- **removals**: 요소가 제거되었을 때 스크린 리더가 이를 사용자에게 알립니다.   
- **text**: 요소의 텍스트가 변경되었을 때 스크린 리더가 이를 사용자에게 알립니다.   
- **all**: additions, removals, text의 모든 변경 사항을 스크린 리더가 알립니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, p, section, article 등 대부분의 HTML 요소에서 사용 가능.   
- **연관된 역할**: alert, status, log, timer, marquee 등 live region과 관련된 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **적절한 변경 사항 선택**: aria-relevant 속성 값은 페이지에서 발생하는 업데이트의 중요도에 따라 선택해야 합니다. 너무 많은 변경 사항을 알리면 사용자가 혼란스러워질 수 있으므로, 필요한 경우에만 사용합니다.    
- **aria-live 속성과의 조합**: aria-relevant는 aria-live 속성과 함께 사용될 때 의미가 있습니다. aria-live가 off로 설정된 경우, aria-relevant는 효과가 없습니다.    


**잘못된 예시**
aria-relevant="all"은 모든 변경 사항(추가, 제거, 텍스트 변경)을 알리므로, 불필요한 정보가 스크린 리더를 통해 전달될 수 있습니다. 실제로 중요한 변경 사항만 알리는 것이 좋습니다.    
```sh
<div aria-live="polite" aria-relevant="all">
  <p>알림: 새로운 메시지가 도착했습니다.</p>
  <span>추가 정보가 있습니다.</span>
</div>
<script>
  setTimeout(() => {
    document.querySelector('div').innerHTML = '<p>알림: 메시지가 삭제되었습니다.</p>';
  }, 2000);
</script>
```

**올바른 예시**
이 예시에서는 새로운 메시지가 도착했을 때만 스크린 리더가 이를 알리도록 aria-relevant="additions"를 사용했습니다. 사용자가 알아야 할 중요한 정보만 전달됩니다.    
```sh
<div aria-live="polite" aria-relevant="additions">
  <p id="notifications">알림이 없습니다.</p>
</div>
<script>
  setTimeout(() => {
    let newMessage = document.createElement('p');
    newMessage.textContent = '새로운 메시지가 도착했습니다.';
    document.getElementById('notifications').appendChild(newMessage);
  }, 3000);
</script>
```

**aria-relevant="additions" 사용 예시**
새로운 업데이트가 추가될 때만 알리도록 설정합니다.    
```sh
<div aria-live="polite" aria-relevant="additions">
  <ul id="updates">
    <li>초기 상태</li>
  </ul>
</div>
<script>
  setTimeout(() => {
    let newUpdate = document.createElement('li');
    newUpdate.textContent = '새로운 업데이트가 있습니다.';
    document.getElementById('updates').appendChild(newUpdate);
  }, 4000);
</script>
```

**aria-relevant="removals" 사용 예시**
메시지가 제거될 때만 스크린 리더가 이를 알립니다.    
```sh
<div aria-live="polite" aria-relevant="removals">
  <p id="message">이 메시지는 곧 제거됩니다.</p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('message').remove();
  }, 3000);
</script>
```

**aria-relevant="text" 사용 예시**
텍스트가 변경될 때만 알리도록 설정합니다.    
```sh
<div aria-live="polite" aria-relevant="text">
  <p id="status">현재 상태: 정상</p>
</div>
<script>
  setTimeout(() => {
    document.getElementById('status').textContent = '현재 상태: 오류 발생';
  }, 5000);
</script>
```

**aria-relevant="all" 사용 예시**
모든 변경 사항(추가, 제거, 텍스트 변경)을 사용자에게 알리도록 설정합니다.    
```sh
<div aria-live="assertive" aria-relevant="all">
  <p id="full-status">시스템 상태: 양호</p>
</div>
<script>
  setTimeout(() => {
    let statusElement = document.getElementById('full-status');
    statusElement.textContent = '시스템 상태: 경고';
    let newInfo = document.createElement('p');
    newInfo.textContent = '추가 정보: CPU 과부하';
    statusElement.parentNode.appendChild(newInfo);
  }, 6000);
</script>
```

**시멘틱 구조의 예시**
시스템 로그와 같은 영역에서 새로운 로그가 추가되거나 텍스트가 변경될 때만 스크린 리더가 이를 알리도록 설정합니다.    
```sh
<section role="log" aria-live="polite" aria-relevant="additions text">
  <header>
    <h2>시스템 로그</h2>
  </header>
  <div id="log-content">
    <p>로그를 기다리는 중...</p>
  </div>
</section>
<script>
  setTimeout(() => {
    document.getElementById('log-content').innerHTML = '<p>새로운 로그가 추가되었습니다.</p>';
  }, 4000);
</script>
```





## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  