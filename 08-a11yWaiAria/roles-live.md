# WAI-ARIA 역할

## Live Region Roles (라이브 영역 역할)
> **Live Region Roles**는 웹 페이지에서 콘텐츠가 동적으로 변경될 때, 보조 기술이 이를 즉시 사용자에게 알리도록 도와주는 ARIA 역할입니다. 이러한 역할들은 사용자에게 실시간으로 중요한 업데이트나 변화가 발생했음을 알리는 데 사용되며, 페이지 새로 고침 없이도 정보를 실시간으로 전달할 수 있습니다.   
[W3C ARIA Live Region Roles](https://www.w3.org/TR/wai-aria-1.2/#live_region_roles){: target="_blank"}   


### **1. alert 역할**    
alert 역할은 웹 페이지에서 중요한 메시지를 즉시 사용자에게 전달하는 데 사용됩니다. alert 역할은 경고나 중요한 정보와 같은 긴급한 메시지를 사용자에게 알리며, 보조 기술은 이 역할이 적용된 콘텐츠를 즉시 읽어 사용자에게 전달합니다. alert는 사용자에게 방해가 될 수 있으므로, 매우 신중하게 사용해야 합니다.   
[W3C ARIA alert](https://www.w3.org/TR/wai-aria-1.2/#alert){: target="_blank"}   
[MDN ARIA alert](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/alert_role){: target="_blank"}   

**기본 설명**  
- alert 역할은 사용자가 즉시 인지해야 하는 중요한 메시지를 전달합니다. 예를 들어, 오류 메시지나 중요한 상태 변경을 알리는 데 사용됩니다.    
- 이 역할이 적용된 콘텐츠는 페이지가 새로 고침되거나 콘텐츠가 동적으로 변경될 때 보조 기술이 즉시 사용자에게 알리도록 설계되어 있습니다.    
- alert는 일반적으로 자동으로 읽혀야 하는 메시지에 사용되며, 사용자의 직접적인 상호작용을 요구하지 않습니다.    

**사용 시 주의사항**   
- 즉시 사용자에게 전달되어야 하는 정보에 사용: alert 역할은 사용자에게 즉시 전달되어야 하는 중요한 정보에 사용해야 합니다. 이 역할을 남용하면 사용자가 중요한 정보와 일반적인 정보 사이를 구분하기 어려워질 수 있습니다.   
- 상호작용이 없는 메시지에 사용: alert는 일반적으로 사용자의 응답이나 상호작용이 필요하지 않은 메시지에 사용됩니다. 사용자의 직접적인 응답을 요구하는 경우에는 alertdialog 역할을 사용하는 것이 더 적합할 수 있습니다.
- 자동으로 읽히는 메시지에 적합: 이 역할이 적용된 콘텐츠는 보조 기술에 의해 자동으로 읽히므로, 사용자가 다른 작업을 하던 중에도 즉시 메시지를 인식할 수 있도록 합니다.

**상속된 상태 및 속성**   
- alert 역할 자체는 추가적인 상태나 속성을 필요로 하지 않습니다. aria-live 속성은 assertive로 설정된 상태로 암묵적으로 적용되며, 보조 기술이 메시지를 즉시 사용자에게 전달하게 됩니다.    


**기본 alert 역할 사용 예시**
이 예시는 세션이 만료되었음을 사용자에게 알리는 메시지를 나타냅니다. alert 역할이 적용되어, 보조 기술이 이 메시지를 즉시 사용자에게 전달합니다.   
```sh
<div role="alert">
  Your session has expired. Please log in again.
</div>
```

**동적으로 생성된 alert 예시**
이 예시는 폼 제출 실패 시 사용자에게 경고를 표시하는 동적 alert 메시지를 나타냅니다. 자바스크립트를 통해 alert 메시지가 표시되면 보조 기술이 이를 즉시 사용자에게 전달합니다.    
```sh
<div id="alertBox" role="alert" style="display:none;">
  Form submission failed. Please try again.
</div>

<script>
  // Simulate an error
  document.getElementById('alertBox').style.display = 'block';
</script>
```

**폼 필드 유효성 검사 alert 예시**
이 예시는 사용자가 잘못된 이메일 주소를 입력했을 때 경고 메시지를 표시하는 alert를 포함합니다. 제출하려는 폼의 이메일 입력이 유효하지 않은 경우, alert 역할을 가진 경고 메시지가 표시되고, 보조 기술이 이를 사용자에게 즉시 전달합니다.    
```sh
<form>
  <label for="email">Email:</label>
  <input type="email" id="email" required>
  <div role="alert" id="emailAlert" style="color:red; display:none;">
    Please enter a valid email address.
  </div>
  <button type="submit">Submit</button>
</form>

<script>
  document.querySelector('form').addEventListener('submit', function(event) {
    const emailInput = document.getElementById('email');
    const emailAlert = document.getElementById('emailAlert');
    if (!emailInput.checkValidity()) {
      event.preventDefault();
      emailAlert.style.display = 'block';
    }
  });
</script>
```

### **2. log 역할**    
log 역할은 동적으로 추가되는 텍스트 정보를 사용자에게 실시간으로 전달하는 데 사용됩니다. 이 역할은 채팅 로그, 시스템 로그, 활동 피드 등과 같이 지속적으로 업데이트되는 정보를 포함한 콘텐츠 영역에 적용됩니다. 보조 기술은 log 역할이 적용된 영역에서 새로운 정보가 추가될 때마다 이를 사용자에게 알립니다.   
[W3C ARIA log](https://www.w3.org/TR/wai-aria-1.2/#log){: target="_blank"}   
[MDN ARIA log](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/log_role){: target="_blank"}   

**기본 설명**  
- log 역할은 동적으로 업데이트되는 텍스트 정보를 사용자에게 전달하는 데 사용됩니다. 이 역할은 로그 메시지나 활동 피드, 채팅 메시지와 같은 실시간 업데이트가 중요한 콘텐츠에 적합합니다.    
- 보조 기술은 log 역할이 적용된 영역에서 텍스트가 추가되거나 변경될 때 이를 사용자에게 읽어줍니다.    
- log 역할은 aria-live 속성의 polite 값을 암묵적으로 사용하여, 사용자 작업을 방해하지 않고 업데이트를 전달합니다.    

**사용 시 주의사항**   
- 실시간으로 중요한 정보를 전달: log 역할은 지속적으로 업데이트되는 중요한 정보를 전달하는 데 사용됩니다. 이는 사용자가 실시간으로 이벤트나 상태 변경을 인지하는 데 도움을 줍니다.   
- aria-live 속성의 적절한 사용: log 역할은 기본적으로 aria-live="polite"로 설정되어 있어, 새로운 정보가 추가되더라도 사용자 작업을 방해하지 않고 자연스럽게 업데이트를 전달합니다. 그러나 더 중요한 메시지의 경우, aria-live="assertive"를 설정하여 즉시 전달될 수 있습니다.
- 과도한 사용 자제: log 역할이 적용된 영역에서 너무 빈번하게 업데이트가 발생하면 사용자에게 과도한 알림이 전달되어 오히려 방해가 될 수 있습니다. 중요하고 필요한 정보에만 사용하도록 주의해야 합니다.

**상속된 상태 및 속성**   
- aria-live: log 역할은 기본적으로 aria-live="polite"로 설정되며, 새로운 정보가 사용자에게 자연스럽게 전달됩니다.    
- aria-atomic: 전체 콘텐츠가 업데이트될 때 전체 영역을 다시 읽을지, 아니면 변경된 부분만 읽을지 결정할 수 있습니다.    
- aria-relevant: additions, removals, text 등과 같은 업데이트 유형을 제어하여, 보조 기술이 어떤 종류의 변경 사항에 대해 사용자에게 알릴지 설정할 수 있습니다.    


**기본 log 역할 사용 예시**
이 예시는 사용자의 로그인 활동을 기록하는 로그를 나타냅니다. 보조 기술은 log 역할이 적용된 이 영역에서 새로운 정보가 추가될 때마다 이를 사용자에게 전달합니다.     
```sh
<div role="log" aria-live="polite">
  <p>User logged in at 12:00 PM.</p>
</div>
```

**동적으로 업데이트되는 log 예시**
이 예시는 채팅 애플리케이션의 로그를 나타내며, 새로운 메시지가 추가될 때마다 로그가 업데이트됩니다. log 역할은 사용자가 이전 메시지와 새로운 메시지를 쉽게 구분할 수 있도록 도와줍니다.    
```sh
<div role="log" aria-live="polite" id="chatLog">
  <p>12:01 PM: User1: Hello!</p>
</div>

<script>
  function addChatMessage(message) {
    const log = document.getElementById('chatLog');
    const newMessage = document.createElement('p');
    newMessage.textContent = message;
    log.appendChild(newMessage);
  }

  // Simulating a new chat message
  addChatMessage('12:02 PM: User2: Hi there!');
</script>
```

**시스템 로그 예시**
이 예시는 시스템 로그를 기록하는 영역을 나타냅니다. 시스템 상태가 변경되면 로그가 동적으로 업데이트되며, 보조 기술은 사용자가 이 새로운 정보를 놓치지 않도록 전달합니다.    
```sh
<div role="log" aria-live="polite" id="systemLog">
  <p>System started at 12:00 PM.</p>
</div>

<script>
  function addSystemLogEntry(entry) {
    const log = document.getElementById('systemLog');
    const newEntry = document.createElement('p');
    newEntry.textContent = entry;
    log.appendChild(newEntry);
  }

  // Simulating a new system log entry
  addSystemLogEntry('12:05 PM: System check completed.');
</script>
```

### **3. marquee 역할**    
marquee 역할은 연속적으로 움직이는 텍스트나 다른 콘텐츠를 나타내는 데 사용됩니다. 이 역할은 텍스트가 자동으로 스크롤되거나 움직이는 상황에서, 보조 기술이 이 동적 콘텐츠를 올바르게 전달하도록 합니다. marquee 역할은 웹 애플리케이션에서 시각적으로 강조되거나 지속적으로 변화하는 정보를 제공하는 경우에 사용됩니다. 그러나 이 역할을 사용할 때는 사용자의 경험을 해치지 않도록 신중하게 고려해야 합니다.   
[W3C ARIA marquee](https://www.w3.org/TR/wai-aria-1.2/#marquee){: target="_blank"}   
[MDN ARIA marquee](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/marquee_role){: target="_blank"}   

**기본 설명**  
- marquee 역할은 연속적으로 스크롤되거나 이동하는 텍스트나 콘텐츠를 정의합니다. 이러한 콘텐츠는 일반적으로 주식 시장 표시줄, 뉴스 헤드라인, 광고 등과 같이 반복적이거나 끊임없이 업데이트되는 정보를 제공하는 데 사용됩니다.    
- 이 역할을 사용하면 보조 기술이 움직이는 텍스트를 인식하고, 사용자가 중요한 콘텐츠를 놓치지 않도록 도와줍니다.    

**사용 시 주의사항**   
- 정보의 중요성: marquee 역할은 중요한 정보가 반복적으로 표시되거나 사용자가 놓쳐서는 안 되는 정보를 전달할 때 사용됩니다. 사용자는 이 정보를 자동으로 전달받아야 하며, 중요한 내용을 놓치지 않도록 해야 합니다.   
- 과도한 사용 자제: marquee는 사용자에게 방해가 될 수 있는 요소로 간주될 수 있으므로, 필요한 곳에만 제한적으로 사용해야 합니다. 지나치게 많은 움직이는 텍스트는 사용자 경험을 해칠 수 있습니다.   
- 접근성 고려: 스크롤되는 텍스트는 일부 사용자가 읽기 어려울 수 있으므로, marquee를 사용할 때는 콘텐츠가 충분히 읽기 쉽게 디자인되어야 합니다. 보조 기술이 이 콘텐츠를 읽을 수 있도록 aria-live 속성을 설정할 수도 있습니다.   
- (정지 기능 제공) 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.   

**상속된 상태 및 속성**   
- aria-live: marquee 역할은 동적으로 업데이트되는 콘텐츠이므로, aria-live="polite" 또는 assertive"를 사용하여 보조 기술이 이 콘텐츠를 어떻게 전달할지 설정할 수 있습니다.    
- aria-atomic: 전체 콘텐츠가 업데이트될 때 전체 영역을 다시 읽을지, 아니면 변경된 부분만 읽을지 결정할 수 있습니다.    
- aria-relevant: 보조 기술이 어떤 종류의 변경 사항(예: additions, removals, text)에 대해 사용자에게 알릴지 제어할 수 있습니다.    


**기본 marquee 역할 사용 예시**
이 예시는 뉴스 헤드라인을 연속적으로 스크롤하는 marquee를 나타냅니다. 보조 기술은 이 동적인 콘텐츠를 인식하고, 사용자가 이 중요한 정보를 놓치지 않도록 전달합니다.   
```sh
<div role="marquee">
  Breaking News: Market hits record high today.
</div>
```

**수평으로 스크롤되는 텍스트 예시**
이 예시는 웹 페이지 상단에 표시되는 스크롤링 환영 메시지를 구현한 것입니다. marquee 역할을 사용해, 사용자가 이 중요한 메시지를 시각적으로 인식하지 못하더라도 보조 기술이 이를 전달하도록 설정합니다.    
```sh
<div role="marquee" style="white-space: nowrap; overflow: hidden; width: 100%;">
  <p style="display: inline-block; animation: marquee 10s linear infinite;">
    Welcome to our website! Enjoy our latest updates and features.
  </p>
</div>

<style>
  @keyframes marquee {
    from { transform: translateX(100%); }
    to { transform: translateX(-100%); }
  }
</style>
```

**지속적으로 업데이트되는 주식 정보 예시**
이 예시는 주식 시장 정보를 지속적으로 업데이트하여 스크롤하는 marquee를 구현한 것입니다. 보조 기술은 이 콘텐츠를 인식하고, 사용자가 중요한 정보를 놓치지 않도록 돕습니다.    
```sh
<div role="marquee" style="white-space: nowrap; overflow: hidden; width: 100%;">
  <p style="display: inline-block; animation: stockmarquee 15s linear infinite;">
    AAPL: 150.25 (+1.25%) | TSLA: 720.50 (-2.10%) | AMZN: 3300.00 (+0.50%)
  </p>
</div>

<style>
  @keyframes stockmarquee {
    from { transform: translateX(100%); }
    to { transform: translateX(-100%); }
  }
</style>
```

### **4. status 역할**    
status 역할은 사용자에게 페이지 내의 특정 상태나 프로세스의 결과를 전달하는 데 사용됩니다. 이 역할은 경고처럼 즉각적인 주의를 요구하지 않지만, 사용자에게 중요한 상태 정보를 제공해야 하는 경우에 적합합니다. status 역할은 사용자에게 방해가 되지 않도록 자연스럽게 정보를 전달합니다.   
[W3C ARIA status](https://www.w3.org/TR/wai-aria-1.2/#status){: target="_blank"}   
[MDN ARIA status](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/status_role){: target="_blank"}   

**기본 설명**  
- status 역할은 웹 페이지에서 사용자가 알고 있어야 하는 상태 정보나 결과를 나타냅니다. 이는 사용자 작업의 성공 또는 실패를 알리거나, 특정 프로세스의 상태를 전달하는 데 사용됩니다.    
- status 역할이 적용된 콘텐츠는 aria-live 속성의 polite 값이 기본적으로 적용되어, 사용자 작업을 방해하지 않고 자연스럽게 상태 정보를 전달합니다.    
- 이 역할은 일반적으로 메시지나 알림을 사용자에게 표시할 때 사용되며, 중요한 정보가 사용자에게 적절히 전달되도록 합니다.    

**사용 시 주의사항**   
- 사용자 작업의 결과를 알리기 위해 사용: status 역할은 사용자가 수행한 작업의 결과나 특정 프로세스의 상태를 전달하는 데 적합합니다. 예를 들어, 폼 제출, 데이터 저장, 파일 업로드 등의 결과를 사용자에게 알릴 때 사용됩니다.   
- 중요하지만 비긴급한 정보에 적합: status 역할은 사용자에게 중요한 정보를 전달하지만, 즉각적인 주의를 요구하지 않습니다. 경고나 오류 메시지와 같은 긴급한 상황에는 alert 역할을 사용하는 것이 더 적합합니다.   
- 사용자 경험에 방해되지 않도록 설계: status 역할은 보조 기술이 정보를 전달할 때 사용자의 현재 작업을 방해하지 않도록 자연스럽게 작동해야 합니다. 따라서, 이 역할이 적용된 영역은 사용자 경험을 해치지 않도록 신중하게 디자인되어야 합니다.    

**상속된 상태 및 속성**   
- alert 역할 자체는 추가적인 상태나 속성을 필요로 하지 않습니다. aria-live 속성은 assertive로 설정된 상태로 암묵적으로 적용되며, 보조 기술이 메시지를 즉시 사용자에게 전달하게 됩니다.    


**기본 status 역할 사용 예시**
이 예시는 사용자가 변경한 내용을 성공적으로 저장했음을 알리는 상태 메시지를 나타냅니다. status 역할이 적용되어, 보조 기술이 이 정보를 사용자에게 자연스럽게 전달합니다.   
```sh
<div role="status">
  Your changes have been saved successfully.
</div>
```

**폼 제출 후의 상태 메시지 예시**
이 예시는 사용자가 폼을 제출한 후 성공적으로 제출되었음을 알리는 상태 메시지를 나타냅니다. status 역할이 적용된 이 영역에 메시지가 표시되며, 보조 기술이 이를 사용자에게 전달합니다.    
```sh
<form id="contactForm">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>
  <button type="submit">Submit</button>
</form>
<div role="status" id="formStatus"></div>

<script>
  document.getElementById('contactForm').addEventListener('submit', function(event) {
    event.preventDefault();
    document.getElementById('formStatus').textContent = "Form submitted successfully!";
  });
</script>
```

**파일 업로드 상태 예시**
이 예시는 파일 업로드가 진행 중임을 알리고, 완료되면 성공 메시지를 표시하는 상태 영역을 나타냅니다. status 역할을 사용하여 보조 기술이 업로드 상태를 사용자에게 자연스럽게 전달합니다.    
```sh
<div id="uploadStatus" role="status">
  Uploading file...
</div>

<script>
  // Simulating a file upload process
  setTimeout(() => {
    document.getElementById('uploadStatus').textContent = "File uploaded successfully!";
  }, 3000);
</script>
```

### **5. timer 역할**    
timer 역할은 웹 애플리케이션에서 특정 작업이나 이벤트의 남은 시간을 사용자에게 알리는 데 사용됩니다. 이 역할은 특히 세션 타임아웃, 시험 시간, 또는 다른 시간 제한이 있는 작업을 수행할 때 사용자에게 남은 시간을 명확하게 전달하는 데 유용합니다. timer 역할을 사용하면 보조 기술이 시간을 지속적으로 업데이트하여 사용자가 시간에 민감한 작업을 수행하는 동안 남은 시간을 명확하게 인지할 수 있도록 돕습니다..   
[W3C ARIA timer](https://www.w3.org/TR/wai-aria-1.2/#timer){: target="_blank"}   
[MDN ARIA timer](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/timer_role){: target="_blank"}   

**기본 설명**  
- timer 역할은 제한된 시간이 있는 작업의 남은 시간을 표시하거나 특정 시간 경과를 알리는 데 사용됩니다. 예를 들어, 온라인 시험, 세션 타임아웃 경고, 쿠키 설정 시간 등의 상황에서 사용할 수 있습니다.    
- timer 역할은 보조 기술이 시간을 지속적으로 업데이트하여 사용자에게 정보를 제공하도록 설계되었습니다. 이는 사용자가 시간에 민감한 작업을 수행하는 동안 남은 시간을 명확하게 인지할 수 있도록 돕습니다.    

**사용 시 주의사항**   
- 시간에 민감한 작업에 사용: timer 역할은 사용자가 시간 제한이 있는 작업을 수행할 때, 남은 시간을 명확히 인지할 수 있도록 돕습니다. 시험 시간, 온라인 거래 타임아웃 등 중요한 시간 제한 상황에 적합합니다.   
- aria-live 속성의 사용: timer 역할은 기본적으로 aria-live 속성을 사용해 시간이 업데이트될 때 보조 기술이 이를 즉시 사용자에게 전달할 수 있도록 해야 합니다. 일반적으로 aria-live="assertive" 속성을 사용해 즉각적인 알림이 가능하도록 설정합니다.   
- 명확한 시간 표시: 타이머의 시간이 변경될 때 보조 기술이 올바르게 업데이트된 정보를 전달할 수 있도록, 타이머의 텍스트가 명확하고 일관되게 표시되어야 합니다.    

**상속된 상태 및 속성**   
- aria-live: timer 역할은 aria-live="assertive"로 설정되어 보조 기술이 시간을 사용자에게 즉시 전달하도록 설계되어 있습니다.    
- aria-atomic: 전체 타이머 콘텐츠가 업데이트될 때 전체 영역을 다시 읽을지, 아니면 변경된 부분만 읽을지 결정할 수 있습니다.    
- aria-relevant: 보조 기술이 타이머의 업데이트를 사용자에게 어떻게 전달할지 제어합니다 (예: additions, text 등).    


**기본 timer 역할 사용 예시**
이 예시는 사용자가 인지해야 하는 남은 시간을 표시하는 기본 timer 역할을 나타냅니다. aria-live="assertive" 속성을 사용해 보조 기술이 시간을 사용자에게 즉시 알리도록 설정했습니다.   
```sh
<div role="timer" aria-live="assertive">
  Time left: 10 minutes
</div>
```

**동적으로 업데이트되는 타이머 예시**
이 예시는 60초 카운트다운 타이머를 구현한 것입니다. 매초 남은 시간이 업데이트되며, 보조 기술이 이 정보를 사용자에게 전달합니다. 시간이 다 되면 "Time's up!" 메시지가 표시됩니다.    
```sh
<div role="timer" aria-live="assertive" id="countdownTimer">
  Time left: 60 seconds
</div>

<script>
  let timeLeft = 60;
  const timerElement = document.getElementById('countdownTimer');

  const timerInterval = setInterval(() => {
    timeLeft--;
    timerElement.textContent = `Time left: ${timeLeft} seconds`;

    if (timeLeft <= 0) {
      clearInterval(timerInterval);
      timerElement.textContent = "Time's up!";
    }
  }, 1000);
</script>
```

**세션 타임아웃 경고 예시**
이 예시는 사용자 세션이 만료되기까지 남은 시간을 표시하는 타이머를 구현한 것입니다. 시간이 다가올수록 보조 기술이 이 정보를 실시간으로 사용자에게 전달합니다.    
```sh
<div role="timer" aria-live="assertive" id="sessionTimer">
  Session expires in: 5 minutes
</div>

<script>
  let sessionTimeLeft = 300; // 5 minutes in seconds
  const sessionTimerElement = document.getElementById('sessionTimer');

  const sessionTimerInterval = setInterval(() => {
    sessionTimeLeft--;
    const minutes = Math.floor(sessionTimeLeft / 60);
    const seconds = sessionTimeLeft % 60;
    sessionTimerElement.textContent = `Session expires in: ${minutes}:${seconds < 10 ? '0' : ''}${seconds} minutes`;

    if (sessionTimeLeft <= 0) {
      clearInterval(sessionTimerInterval);
      sessionTimerElement.textContent = "Session expired.";
    }
  }, 1000);
</script>
```

다음 역할은 라이브 지역이며 라이브 지역 특성에 의해 수정될 수 있습니다.

alert
log
marquee
status
timer



## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
   