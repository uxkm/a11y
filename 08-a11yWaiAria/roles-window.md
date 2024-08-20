# WAI-ARIA 역할

## Window Roles
> **Window Roles**는 웹 애플리케이션의 창과 같은 인터페이스 구성 요소를 정의하는 데 사용됩니다. 이 역할들은 사용자와 상호작용하는 다양한 창 요소를 나타내며, 보조 기술을 사용하는 사용자들이 창 요소를 올바르게 이해하고 사용할 수 있도록 도와줍니다.   
[W3C ARIA Window Roles](https://www.w3.org/TR/wai-aria-1.2/#window_roles){: target="_blank"}   


### **1. alertdialog 역할**    
alertdialog 역할은 사용자에게 즉각적인 주의를 요구하는 경고 메시지와 상호작용할 수 있는 대화 상자를 나타냅니다. 이 역할은 중요한 경고나 확인 요청을 포함하며, 사용자가 즉시 반응해야 하는 상황에서 사용됩니다. alertdialog는 일반적인 alert와 달리, 사용자로부터 입력을 받을 수 있는 인터랙티브 요소(예: 버튼, 텍스트 필드)를 포함할 수 있습니다.   
[W3C ARIA alertdialog](https://www.w3.org/TR/wai-aria-1.2/#alertdialog){: target="_blank"}   
[MDN ARIA alertdialog](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/alertdialog_role){: target="_blank"}   

**기본 설명**  
- alertdialog 역할은 사용자에게 중요한 메시지를 전달하고, 사용자의 응답을 요구하는 대화 상자를 정의합니다. 이 역할은 대화 상자 내에서 키보드 내비게이션을 제어하고, 보조 기술이 이 대화 상자가 사용자로부터 즉각적인 주의를 요한다는 것을 알리도록 합니다.    
- 이 역할은 모달 대화 상자로 구현되는 경우가 많으며, 대화 상자가 활성화된 동안에는 페이지의 다른 부분과 상호작용할 수 없습니다.    

**사용 시 주의사항**   
- 모달 대화 상자: alertdialog는 주로 모달 대화 상자로 사용됩니다. 사용자가 대화 상자 외의 페이지 콘텐츠와 상호작용할 수 없도록 하기 위해 aria-modal="true" 속성을 사용하는 것이 일반적입니다.   
- 포커스 관리: alertdialog가 활성화되면, 자동으로 포커스가 대화 상자로 이동하여 사용자가 키보드를 사용해 쉽게 상호작용할 수 있도록 해야 합니다. 대화 상자를 닫으면 포커스가 원래 위치로 돌아가야 합니다.
- 레이블과 설명 제공: aria-labelledby 및 aria-describedby 속성을 사용해 대화 상자의 제목과 설명을 명확히 지정하여, 보조 기술 사용자들이 대화 상자의 목적과 내용을 쉽게 이해할 수 있도록 해야 합니다.
- 적절한 키보드 내비게이션: alertdialog 내에서 키보드 탐색이 원활하게 작동하도록 해야 하며, Tab 키를 사용해 대화 상자 내의 모든 상호작용 요소를 탐색할 수 있도록 설정해야 합니다.

**상속된 상태 및 속성**   
- aria-labelledby: 대화 상자의 제목을 참조합니다.    
- aria-describedby: 대화 상자의 내용을 설명합니다.    
- aria-modal: 대화 상자가 모달인지 여부를 지정하며, 모달 대화 상자는 페이지의 나머지 부분과의 상호작용을 제한합니다.    
- aria-live: 기본적으로 aria-live="assertive" 속성을 가지며, 보조 기술이 이 대화 상자를 즉시 사용자에게 알리도록 합니다.    


**기본 alertdialog 역할 사용 예시**
이 예시는 파일 삭제를 확인하는 경고 대화 상자를 정의한 것입니다. alertdialog 역할을 사용해, 보조 기술이 이 대화 상자가 즉각적인 응답을 요구한다는 것을 알립니다. aria-labelledby 속성은 대화 상자의 제목을 참조하고, aria-describedby 속성은 대화 상자의 내용을 설명합니다.    
```sh
<div role="alertdialog" aria-labelledby="alertTitle" aria-describedby="alertDesc">
  <h2 id="alertTitle">Delete Confirmation</h2>
  <p id="alertDesc">Are you sure you want to delete this file? This action cannot be undone.</p>
  <button id="confirmDelete">Yes, delete it</button>
  <button id="cancelDelete">Cancel</button>
</div>
```

**모달 alertdialog 예시**
이 예시는 세션 타임아웃을 알리고 사용자가 세션을 연장하거나 로그아웃할 수 있는 모달 대화 상자를 구현한 것입니다. aria-modal="true" 속성은 이 대화 상자가 모달임을 지정하여, 사용자가 대화 상자 외의 페이지와 상호작용할 수 없게 합니다.    
```sh
<div role="alertdialog" aria-modal="true" aria-labelledby="alertTitle" aria-describedby="alertDesc">
  <h2 id="alertTitle">Session Timeout</h2>
  <p id="alertDesc">Your session is about to expire. Would you like to extend your session?</p>
  <button id="extendSession">Extend Session</button>
  <button id="logout">Log Out</button>
</div>
```

**자동 포커스 관리가 포함된 alertdialog 예시**
이 예시는 alertdialog가 나타날 때 자동으로 포커스를 관리하여, 대화 상자가 활성화되면 사용자가 즉시 응답할 수 있도록 합니다. tabindex="-1"은 대화 상자가 초기 포커스를 받을 수 있도록 설정합니다.    
```sh
<div role="alertdialog" aria-labelledby="alertTitle" aria-describedby="alertDesc" tabindex="-1">
  <h2 id="alertTitle">Unsaved Changes</h2>
  <p id="alertDesc">You have unsaved changes. Do you want to save them before exiting?</p>
  <button id="saveChanges">Save</button>
  <button id="discardChanges">Discard</button>
  <button id="cancelExit">Cancel</button>
</div>

<script>
  document.querySelector('[role="alertdialog"]').focus();
</script>
```

### **2. dialog 역할**    
alertdialog 역할은 사용자에게 즉각적인 주의를 요구하는 경고 메시지와 상호작용할 수 있는 대화 상자를 나타냅니다. 이 역할은 중요한 경고나 확인 요청을 포함하며, 사용자가 즉시 반응해야 하는 상황에서 사용됩니다. alertdialog는 일반적인 alert와 달리, 사용자로부터 입력을 받을 수 있는 인터랙티브 요소(예: 버튼, 텍스트 필드)를 포함할 수 있습니다.   
[W3C ARIA dialog](https://www.w3.org/TR/wai-aria-1.2/#dialog){: target="_blank"}   
[MDN ARIA dialog](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/dialog_role){: target="_blank"}   

**기본 설명**  
- dialog 역할은 웹 페이지 내에서 사용자와 상호작용할 수 있는 대화 상자를 정의합니다. 이 대화 상자는 정보를 제공하거나 입력을 요청할 수 있습니다.    
- 대화 상자는 모달(aria-modal="true")로 설정되어 페이지의 다른 부분과 상호작용을 제한하거나, 비모달로 설정되어 페이지와의 상호작용을 허용할 수 있습니다.    
- dialog 역할을 사용하면 보조 기술이 대화 상자와 관련된 정보를 적절하게 사용자에게 전달할 수 있도록 도와줍니다.    

**사용 시 주의사항**   
- 모달 대화 상자: dialog 역할은 주로 모달 대화 상자에 사용됩니다. 모달 대화 상자를 정의할 때는 aria-modal="true" 속성을 사용하여 사용자가 대화 상자 외의 페이지 콘텐츠와 상호작용할 수 없도록 해야 합니다.   
- 포커스 관리: dialog가 활성화되면, 자동으로 포커스가 대화 상자 내의 첫 번째 상호작용 요소로 이동하여 사용자가 키보드를 통해 쉽게 상호작용할 수 있도록 해야 합니다. 대화 상자가 닫히면 포커스가 원래 위치로 돌아가야 합니다.
- 레이블과 설명 제공: aria-labelledby 및 aria-describedby 속성을 사용하여 대화 상자의 제목과 설명을 명확하게 제공해야 합니다. 이는 보조 기술 사용자들이 대화 상자의 목적과 내용을 쉽게 이해할 수 있도록 돕습니다.
- 적절한 키보드 내비게이션: 대화 상자 내에서 Tab 키를 사용해 모든 상호작용 요소를 탐색할 수 있도록 설정해야 하며, Escape 키를 사용해 대화 상자를 닫을 수 있어야 합니다.

**상속된 상태 및 속성**   
- aria-labelledby: 대화 상자의 제목을 참조합니다.    
- aria-describedby: 대화 상자의 내용을 설명합니다.    
- aria-modal: 대화 상자가 모달인지 여부를 지정하며, 모달 대화 상자는 페이지의 나머지 부분과의 상호작용을 제한합니다.    


**기본 dialog 역할 사용 예시**
이 예시는 사용자 설정을 조정할 수 있는 기본 대화 상자를 정의한 것입니다. dialog 역할을 사용하여, 보조 기술이 이 요소를 대화 상자로 인식할 수 있게 했습니다. aria-labelledby 속성은 대화 상자의 제목을 참조하고, aria-describedby 속성은 대화 상자의 내용을 설명합니다.    
```sh
<div role="dialog" aria-labelledby="dialogTitle" aria-describedby="dialogDesc">
  <h2 id="dialogTitle">User Preferences</h2>
  <p id="dialogDesc">Adjust your settings below:</p>
  <label for="setting1">Enable notifications</label>
  <input type="checkbox" id="setting1">
  <button type="button">Save</button>
  <button type="button">Cancel</button>
</div>
```

**모달 dialog 예시**
이 예시는 사용자가 페이지를 벗어나기 전에 변경 사항을 저장할지 묻는 모달 대화 상자입니다. aria-modal="true" 속성은 이 대화 상자가 모달임을 나타내며, 사용자가 대화 상자가 열린 동안 다른 페이지 요소와 상호작용할 수 없도록 합니다.    
```sh
<div role="dialog" aria-modal="true" aria-labelledby="dialogTitle" aria-describedby="dialogDesc">
  <h2 id="dialogTitle">Save Changes</h2>
  <p id="dialogDesc">Do you want to save your changes before exiting?</p>
  <button type="button">Save</button>
  <button type="button">Don't Save</button>
  <button type="button">Cancel</button>
</div>
```

**비모달 dialog 예시**
이 예시는 사용자에게 도움말 정보를 제공하는 비모달 대화 상자를 나타냅니다. 이 대화 상자는 페이지의 다른 부분과 동시에 상호작용할 수 있도록 설계되어 있으며, 모달 속성이 없습니다.    
```sh
<div role="dialog" aria-labelledby="dialogTitle" aria-describedby="dialogDesc">
  <h2 id="dialogTitle">Help Information</h2>
  <p id="dialogDesc">Here is some helpful information about using this feature...</p>
  <button type="button">Close</button>
</div>
```

**자동 포커스 관리가 포함된 dialog 예시**
이 예시는 사용자가 로그인해야 하는 모달 대화 상자를 나타내며, 자동으로 포커스가 대화 상자로 이동합니다. 이로 인해 사용자는 대화 상자가 나타나자마자 키보드를 사용해 상호작용할 수 있습니다.    
```sh
<div role="dialog" aria-labelledby="dialogTitle" aria-describedby="dialogDesc" tabindex="-1">
  <h2 id="dialogTitle">Login Required</h2>
  <p id="dialogDesc">Please log in to continue.</p>
  <label for="username">Username</label>
  <input type="text" id="username" tabindex="0">
  <label for="password">Password</label>
  <input type="password" id="password">
  <button type="button">Log In</button>
  <button type="button">Cancel</button>
</div>

<script>
  document.querySelector('[role="dialog"]').focus();
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
    