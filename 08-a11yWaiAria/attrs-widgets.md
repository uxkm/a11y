# WAI-ARIA 상태 및 속성
> WAI-ARIA 상태 및 속성은 웹 애플리케이션의 접근성을 향상시키기 위해 HTML 요소에 추가적인 의미와 기능을 부여하는 메커니즘입니다. 이 섹션에서는 다양한 WAI-ARIA 속성과 상태를 설명하고, 이를 위젯, 라이브 리전, 드래그 앤 드롭, 관계 관련 기능에 적용하는 방법을 다룹니다.    
이 속성과 상태들은 WAI-ARIA가 웹 애플리케이션의 접근성을 강화하기 위해 제공하는 중요한 도구입니다. 이들을 적절하게 사용하면 시각적 장애를 가진 사용자도 웹 콘텐츠와 상호작용할 수 있으며, 동적인 콘텐츠 변경 사항을 쉽게 인지할 수 있습니다. 이를 통해 웹 접근성을 크게 개선할 수 있습니다.   

## Widget Attributes (위젯 속성)
> "Widget Attributes" (위젯 속성)은 위젯의 동작, 외관, 상호작용 방식을 정의하는 속성을 의미합니다. 위젯은 웹 애플리케이션에서 사용자와 상호작용할 수 있는 요소를 나타내며, 이들 속성은 위젯이 어떻게 표시되고 작동하는지를 결정합니다. 웹 개발에서는 이러한 속성을 사용하여 다양한 사용자 인터페이스 요소를 설정하고 제어할 수 있습니다. 특히 장애가 있는 사용자들을 위한 접근성을 개선하기 위해 중요한 역할을 합니다.    
[WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/){: target="_blank"}   
[W3C ARIA Widget Attributes](https://www.w3.org/TR/wai-aria-1.2/#attrs_widgets){: target="_blank"}   


### **1. aria-autocomplete (property)**    
aria-autocomplete 속성은 사용자가 입력한 값에 따라 시스템이 자동으로 완성하는 입력 필드의 동작을 정의합니다. 이 속성은 입력 중인 텍스트 필드에서 제공되는 자동 완성 제안을 설명하며, 사용자가 어떤 방식으로 선택할 수 있는지에 대한 정보를 제공하는 데 사용됩니다.   
[WAI-ARIA 1.2 Specification (aria-autocomplete)](https://www.w3.org/TR/wai-aria-1.2/#aria-autocomplete){: target="_blank"}   
[MDN Web Docs (aria-autocomplete)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-autocomplete){: target="_blank"}   

**aria-autocomplete 속성 값**  
- **none**: 자동 완성이 없음을 나타냅니다.   
- **inline**: 자동 완성 텍스트가 필드 내에서 즉시 채워짐을 나타냅니다.   
- **list**: 자동 완성 제안이 목록으로 제공됨을 나타냅니다.   
- **both**: 자동 완성 텍스트가 필드 내에서 채워지며, 목록으로도 제안이 제공됨을 나타냅니다.   


**연관된 HTML 태그**   
- **input**: 텍스트 입력을 받는 HTML 요소로, aria-autocomplete 속성이 자주 사용됩니다.    
- **textarea**: 여러 줄의 텍스트를 입력받는 HTML 요소로, aria-autocomplete 속성을 사용할 수 있습니다.    
- **div**: 자동 완성 제안을 표시하는 컨테이너로 사용할 수 있습니다.    

**사용 시 주의사항**   
- **적절한 사용**: aria-autocomplete는 자동 완성 기능이 활성화된 텍스트 입력 필드에만 사용해야 합니다.   
- **적절한 값 설정**: none, inline, list, both 중 상황에 맞는 값을 설정해야 합니다.   
- **보조 기술 지원**: aria-autocomplete 속성은 보조 기술(예: 스크린 리더)에서 사용자가 입력 필드의 자동 완성 동작을 이해하고 사용할 수 있도록 도움을 줍니다.   
- **키보드 접근성**: 자동 완성 제안을 키보드로 쉽게 탐색할 수 있도록 키보드 접근성을 고려해야 합니다.    


**잘못된 예시**
aria-autocomplete의 값으로 유효하지 않은 invalid-value가 사용되었습니다. 속성 값은 none, inline, list, both 중 하나여야 합니다.    
```sh
<input type="text" aria-autocomplete="invalid-value" aria-controls="suggestions">
<div id="suggestions"></div>
```

**속성값 none 활용 예시**
이 예시는 자동 완성 기능이 없는 입력 필드를 나타냅니다. aria-autocomplete="none"을 사용하여 사용자에게 자동 완성이 없음을 명확히 알립니다.    
```sh
<input type="text" aria-autocomplete="none" placeholder="Enter text here">
```

**속성값 inline 활용 예시**
aria-autocomplete="inline"은 사용자가 입력하는 동안 자동 완성된 텍스트가 입력 필드에 바로 채워지는 경우를 나타냅니다. 사용자는 즉시 입력된 내용을 볼 수 있습니다.    
```sh
<input type="text" aria-autocomplete="inline" placeholder="Search here" aria-haspopup="true" aria-expanded="false">
```

**속성값 list 활용 예시**
aria-autocomplete="list"는 사용자가 입력하는 동안 자동 완성 제안 목록이 표시됨을 나타냅니다. 사용자는 목록에서 제안을 선택할 수 있으며, aria-controls 속성으로 해당 제안 목록과의 관계를 정의합니다.    
```sh
<input type="text" aria-autocomplete="list" aria-controls="suggestions" aria-haspopup="true" aria-expanded="false">
<div id="suggestions" role="listbox">
  <div role="option">Option 1</div>
  <div role="option">Option 2</div>
  <div role="option">Option 3</div>
</div>
```

**속성값 both 활용 예시**
aria-autocomplete="both"를 사용하여 사용자가 입력하는 동안 자동 완성 제안이 나타나고, 동시에 입력 필드에 자동 완성된 텍스트가 채워집니다. aria-activedescendant 속성을 사용해 현재 활성화된 제안을 명확히 나타내고, aria-label을 통해 보조 기술이 제안 목록의 역할을 이해할 수 있도록 합니다.    
```sh
<input type="text" aria-autocomplete="both" aria-controls="suggestions" aria-haspopup="true" aria-expanded="false" aria-activedescendant="suggestion1">
<div id="suggestions" role="listbox" aria-label="Search suggestions">
  <div id="suggestion1" role="option">Apple</div>
  <div id="suggestion2" role="option">Banana</div>
  <div id="suggestion3" role="option">Cherry</div>
</div>
```

**부가 활용 예시**
이 예시에서는 사용자가 도시 이름을 입력할 때 자동 완성 제안을 제공합니다. aria-autocomplete="list"를 사용해 사용자가 선택할 수 있는 제안 목록을 제공합니다. 각 제안은 role="option"으로 지정되어 있으며, 입력 필드와 제안 목록은 aria-controls로 연결됩니다.    
```sh
<input type="text" aria-autocomplete="list" aria-controls="city-suggestions" placeholder="Enter city">
<div id="city-suggestions" role="listbox">
  <div role="option">New York</div>
  <div role="option">Los Angeles</div>
  <div role="option">Chicago</div>
</div>
```

### **2. aria-checked (state)**    
aria-checked는 ARIA(Accessible Rich Internet Applications)에서 사용하는 상태(state) 속성으로, 주로 체크박스, 라디오 버튼, 토글 버튼과 같은 선택 가능한 UI 요소에 적용됩니다. 이 속성은 보조 기술(예: 스크린 리더)에 요소의 체크 상태를 전달하며, 요소가 선택되었는지, 선택되지 않았는지, 또는 혼합 상태(mixed)인지를 명확하게 나타냅니다.   
[WAI-ARIA 1.2 Specification (aria-checked)](https://www.w3.org/TR/wai-aria-1.2/#aria-checked){: target="_blank"}   
[MDN Web Docs (aria-checked)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-checked){: target="_blank"}   

**aria-checked 속성 값**  
- **true**: 요소가 선택되었음을 나타냅니다.    
- **false**: 요소가 선택되지 않았음을 나타냅니다.    
- **mixed**: 체크박스가 일부만 선택된 상태를 나타냅니다(예: 트리 구조에서 일부 하위 항목만 선택된 경우).    
- **(기본값) 없음**: 속성이 없거나 설정되지 않은 경우, 보조 기술은 체크 상태를 특정할 수 없습니다.        


**연관된 HTML 태그**   
- **input type="checkbox"**: 체크박스 입력 필드.   
- **input type="radio"**: 라디오 버튼 입력 필드.   
- **div role="checkbox"**: 체크박스 역할을 하는 div 요소.   
- **button**: 토글 버튼으로 사용될 수 있는 HTML 요소.    

**사용 시 주의사항**   
- **정확한 상태 반영**: aria-checked 속성 값은 요소의 실제 상태와 일치해야 합니다. 예를 들어, 체크박스가 선택되지 않은 경우에는 aria-checked="false"로 설정해야 합니다.   
- **동적 업데이트**: 요소의 상태가 변경될 때마다 aria-checked 속성을 동적으로 업데이트해야 보조 기술이 이를 올바르게 인식할 수 있습니다.   
- **지원하지 않는 요소에 적용 시 주의**: 기본적으로 체크 가능한 요소(예: input type="checkbox")가 아닌 경우 role 속성을 사용해 해당 요소가 체크 가능한 것으로 인식되도록 해야 합니다.       


**잘못된 예시**
aria-checked는 토글 버튼에서 사용될 수 있지만, 이 경우 role="checkbox" 또는 role="switch"를 추가하여 버튼이 체크 가능함을 명확히 해야 합니다.    
```sh
<button aria-checked="true">Toggle Button</button>
```

**올바른 예시**
이 예시는 토글 버튼에서 role="switch"와 aria-checked를 함께 사용하여 버튼이 활성화된 상태임을 보조 기술에 명확하게 전달합니다.    
```sh
<button role="switch" aria-checked="true">Toggle Button</button>
```

**기본 체크박스 예시**
이 체크박스는 기본적으로 선택되지 않은 상태입니다. aria-checked="false" 속성으로 이 상태를 보조 기술에 전달합니다.    
```sh
<input type="checkbox" id="agree" aria-checked="false">
<label for="agree">I agree to the terms and conditions</label>
```

**동적 체크박스 예시**
이 예시는 커스텀 체크박스로, div 요소에 role="checkbox"를 설정하고 aria-checked 속성을 사용해 체크 상태를 보조 기술에 알립니다. 클릭 시 체크 상태가 반전되도록 설정되어 있습니다.    
```sh
<div role="checkbox" aria-checked="true" tabindex="0" id="customCheckbox">Subscribe to newsletter</div>

<script>
document.getElementById('customCheckbox').addEventListener('click', function() {
    var checked = this.getAttribute('aria-checked') === 'true';
    this.setAttribute('aria-checked', !checked);
});
</script>
```

**혼합 상태(mixed) 예시**
이 예시는 혼합 상태를 나타내는 체크박스를 구현한 것입니다. 예를 들어, 사용자가 트리 구조의 일부 항목만 선택했을 때 전체 선택 체크박스에 혼합 상태(aria-checked="mixed")를 표시할 수 있습니다.    
```sh
<div role="checkbox" aria-checked="mixed" tabindex="0">Select all items</div>
```

**부가 활용 예시**
이 예시는 라디오 버튼을 커스텀 방식으로 구현한 것입니다. 사용자가 하나의 옵션을 선택하면 다른 옵션의 aria-checked 속성이 false로 변경되어 하나의 라디오 버튼만 선택되도록 합니다.    
```sh
<div role="radio" aria-checked="false" tabindex="0" id="option1">Option 1</div>
<div role="radio" aria-checked="true" tabindex="0" id="option2">Option 2</div>

<script>
document.getElementById('option1').addEventListener('click', function() {
    this.setAttribute('aria-checked', 'true');
    document.getElementById('option2').setAttribute('aria-checked', 'false');
});
document.getElementById('option2').addEventListener('click', function() {
    this.setAttribute('aria-checked', 'true');
    document.getElementById('option1').setAttribute('aria-checked', 'false');
});
</script>
```

### **3. aria-disabled (state)**    
aria-disabled 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 상태(state) 속성으로, 사용자 인터페이스(UI) 요소가 비활성화되었음을 보조 기술(예: 스크린 리더)에 전달합니다. 이 속성은 요소가 현재 상호작용할 수 없거나 사용할 수 없는 상태임을 나타냅니다. 비활성화된 요소는 시각적으로 표시될 수 있지만, 사용자와의 상호작용은 차단됩니다.
기본적으로 비활성화 기능을 제공하지 않는 요소에 aria-disabled를 사용하는 것이 적절하며, 이미 disabled 속성을 지원하는 요소에서는 그 속성을 사용하는 것이 좋습니다.       
[WAI-ARIA 1.2 Specification (aria-disabled)](https://www.w3.org/TR/wai-aria-1.2/#aria-disabled){: target="_blank"}   
[MDN Web Docs (aria-disabled)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-disabled){: target="_blank"}   

**aria-checked 속성 값**  
- true: 요소가 비활성화되어 있음을 나타냅니다. 사용자는 해당 요소와 상호작용할 수 없습니다.   
- false: 요소가 활성화되어 있음을 나타냅니다. 사용자는 해당 요소와 상호작용할 수 있습니다. (기본적으로 false 값은 설정하지 않음)        


**연관된 HTML 태그**   
- **button**: 버튼 요소.   
- **input**: 입력 필드 요소.   
- **select**: 드롭다운 메뉴 요소.   
- **a**: 링크 요소 (종종 사용자가 클릭할 수 없는 상태를 표현할 때 사용).    

**사용 시 주의사항**   
- **적용 대상 요소**: aria-disabled는 대부분의 상호작용 가능한 UI 요소에 사용할 수 있습니다. 그러나, 본래 비활성화 기능을 지원하는 HTML 요소(예: button, input)에서는 기본 HTML 속성인 disabled를 사용하는 것이 권장됩니다.
- **시각적 표현과 일치**: aria-disabled="true"로 설정된 요소는 시각적으로도 비활성화된 상태임을 명확히 해야 합니다(예: 흐릿한 색상 처리).
- **키보드 접근성**: aria-disabled를 사용하면 해당 요소는 포커스를 받을 수 없습니다. 키보드 내비게이션 시 이러한 요소를 건너뛸 수 있도록 해야 합니다.
- **상호작용 차단**: 비활성화된 요소는 클릭이나 입력과 같은 상호작용을 완전히 차단해야 하며, 이벤트 리스너도 작동하지 않도록 처리해야 합니다.       


**잘못된 예시**
본래 비활성화 기능을 지원하는 HTML 요소에서는 aria-disabled 대신 HTML disabled 속성을 사용하는 것이 더 적절합니다.    
```sh
<input type="text" aria-disabled="true">
```

**올바른 예시**
본래 비활성화 기능을 지원하는 input 요소에서는 HTML disabled 속성을 사용하는 것이 적절합니다. 이 속성은 자동으로 보조 기술과 시각적 표현을 처리합니다.    
```sh
<input type="text" disabled>
```

**기본 버튼 예시**
이 버튼은 aria-disabled="true"로 설정되어 있으며, 사용자는 이 버튼과 상호작용할 수 없습니다. 스크린 리더는 이 상태를 사용자가 인식할 수 있도록 안내합니다.    
```sh
<button aria-disabled="true">Submit</button>
```

**커스텀 버튼 예시**
이 예시는 div 요소를 버튼으로 사용하고 있으며, aria-disabled="true"를 통해 이 요소가 비활성화 상태임을 나타냅니다. 시각적으로도 회색으로 표시하여 비활성화 상태를 표현하고 있습니다.    
```sh
<div role="button" aria-disabled="true" tabindex="0" style="color: grey;">Custom Button</div>
```

**비활성화된 링크 예시**
이 링크는 aria-disabled="true"로 설정되어 있으며, pointer-events: none을 사용해 클릭을 차단하고, 회색으로 표시하여 비활성화 상태를 시각적으로도 표현하고 있습니다.    
```sh
<a href="#" aria-disabled="true" style="pointer-events: none; color: grey;">Disabled Link</a>
```

**동적 상태 변경 예시**
이 예시는 버튼이 aria-disabled="true"로 설정된 상태에서 클릭 이벤트를 감지하여 경고 메시지를 표시합니다. 이처럼 동적 상호작용에서 비활성화 상태를 반영해야 합니다.    
```sh
<button id="dynamicButton" aria-disabled="true">Click Me</button>

<script>
document.getElementById('dynamicButton').addEventListener('click', function() {
    if (this.getAttribute('aria-disabled') === 'true') {
        alert('Button is disabled');
    } else {
        // Perform the action
    }
});
</script>
```

**부가 활용 예시**
이 예시는 select 요소가 비활성화된 상태임을 나타냅니다. 사용자는 드롭다운 메뉴를 열거나 선택할 수 없습니다.    
```sh
<select aria-disabled="true">
  <option>Option 1</option>
  <option>Option 2</option>
</select>
```

### **4. aria-errormessage (property)**    
aria-errormessage 속성은 입력 오류에 대한 사용자 정의 오류 메시지를 보조 기술(예: 스크린 리더)에 연결하는 데 사용되는 ARIA(Property) 속성입니다. 이 속성은 사용자에게 제공되는 오류 메시지의 내용을 지정하며, 보조 기술이 해당 오류 메시지를 사용자에게 읽어줄 수 있도록 합니다.       
aria-errormessage 속성은 주로 폼 필드와 같이 사용자 입력이 필요한 요소에서 사용되며, 사용자가 잘못된 값을 입력했을 때 제공되는 오류 메시지와 연동됩니다. 이 속성은 오류 메시지가 표시될 때 aria-invalid="true" 속성과 함께 사용해야 합니다.       
[WAI-ARIA 1.2 Specification (aria-errormessage)](https://www.w3.org/TR/wai-aria-1.2/#aria-errormessage){: target="_blank"}   
[MDN Web Docs (aria-errormessage)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-errormessage){: target="_blank"}   

**aria-errormessage 속성 값**    
aria-errormessage 속성의 값은 사용자에게 표시될 오류 메시지를 포함하고 있는 요소의 ID를 참조합니다. 이 값은 해당 오류 메시지 요소와 입력 필드를 연결하며, 보조 기술이 사용자가 입력 오류를 발생시켰을 때 해당 메시지를 읽어줄 수 있도록 합니다.   
- **값의 형식**: aria-errormessage의 값은 반드시 오류 메시지를 포함하는 요소의 ID여야 합니다.   
- **예시 값**: "emailError", "passwordError", "usernameError"        


**연관된 HTML 태그**   
- **input**: 입력 필드 요소.   
- **textarea**: 여러 줄의 텍스트를 입력받는 HTML 요소.   
- **select**: 드롭다운 메뉴 요소.   
- **form**: 폼 요소 내의 다양한 입력 필드와 함께 사용.     

**사용 시 주의사항**   
- **aria-invalid와 함께 사용**: aria-errormessage 속성은 오류 상태를 나타내는 aria-invalid="true" 속성과 함께 사용해야 합니다. 이 속성이 없다면 오류 메시지는 비활성 상태로 인식될 수 있습니다.   
- **명확한 오류 메시지 ID 연결**: aria-errormessage 속성의 값은 오류 메시지를 포함하는 요소의 ID를 가리켜야 합니다. 이 메시지는 사용자가 쉽게 이해할 수 있도록 명확하고 간결하게 작성해야 합니다.   
- **동적 업데이트**: 입력 필드의 상태가 변경되어 오류 메시지가 업데이트될 경우, 보조 기술이 이를 인식할 수 있도록 aria-errormessage 속성의 값을 동적으로 업데이트해야 합니다.       


**잘못된 예시**
오류 메시지 div 요소와 input 필드 사이에 aria-errormessage 속성이 사용되지 않았습니다. 이로 인해 보조 기술이 오류 메시지를 사용자에게 전달하지 못할 수 있습니다.    
```sh
<form>
  <label for="phone">Phone:</label>
  <input type="text" id="phone" aria-invalid="true">
  <div style="color: red;">Please enter a valid phone number.</div>
</form>
```

**올바른 예시**
이 예시는 오류 메시지가 aria-errormessage 속성을 통해 input 필드와 올바르게 연결된 상황을 보여줍니다. 보조 기술은 이 설정을 통해 사용자에게 오류 메시지를 적절히 전달할 수 있습니다.    
```sh
<form>
  <label for="phone">Phone:</label>
  <input type="text" id="phone" aria-invalid="true" aria-errormessage="phoneError">
  <div id="phoneError" style="color: red;">Please enter a valid phone number.</div>
</form>
```

**기본 오류 메시지 예시**
이 예시는 사용자가 잘못된 이메일 주소를 입력했을 때 표시되는 오류 메시지를 구현한 것입니다. aria-errormessage 속성은 오류 메시지가 포함된 div 요소의 ID를 참조하며, aria-invalid="true" 속성과 함께 사용됩니다.    
```sh
<form>
  <label for="email">Email:</label>
  <input type="email" id="email" aria-invalid="true" aria-errormessage="emailError">
  <div id="emailError" style="color: red; display: block;">Please enter a valid email address.</div>
</form>
```

**동적 오류 메시지 및 초점 이동 예시**
이 예시는 사용자가 폼을 제출할 때 입력 필드에 오류가 있으면 동적으로 오류 메시지를 표시하고, 오류가 발생한 필드로 초점을 이동하는 방법을 보여줍니다. aria-errormessage 속성은 오류 메시지가 포함된 요소와 연결되어 있으며, aria-invalid 속성은 사용자의 입력 상태에 따라 동적으로 업데이트됩니다. 첫 번째 오류가 발생한 필드로 초점이 이동하여 사용자가 쉽게 오류를 수정할 수 있도록 도와줍니다.    
```sh
<form id="userForm">
  <label for="username">Username:</label>
  <input type="text" id="username" aria-errormessage="usernameError" aria-invalid="false">
  <div id="usernameError" style="color: red; display: none;">Username is required.</div>
  
  <label for="email">Email:</label>
  <input type="email" id="email" aria-errormessage="emailError" aria-invalid="false">
  <div id="emailError" style="color: red; display: none;">Please enter a valid email address.</div>
  
  <button type="submit">Submit</button>
</form>

<script>
document.getElementById('userForm').addEventListener('submit', function(event) {
    var username = document.getElementById('username');
    var email = document.getElementById('email');
    var usernameError = document.getElementById('usernameError');
    var emailError = document.getElementById('emailError');
    var isValid = true;

    // Reset previous states
    username.setAttribute('aria-invalid', 'false');
    email.setAttribute('aria-invalid', 'false');
    usernameError.style.display = 'none';
    emailError.style.display = 'none';

    // Check username
    if (username.value.trim() === '') {
        username.setAttribute('aria-invalid', 'true');
        usernameError.style.display = 'block';
        username.focus();
        isValid = false;
    }

    // Check email
    if (email.value.trim() === '') {
        email.setAttribute('aria-invalid', 'true');
        emailError.style.display = 'block';
        if (isValid) {
            email.focus();
        }
        isValid = false;
    }

    // Prevent form submission if there are errors
    if (!isValid) {
        event.preventDefault();
    }
});
</script>
```

**부가 활용 예시**
이 예시는 비밀번호 필드에 대한 오류 메시지를 표시하는 상황을 보여줍니다. aria-errormessage 속성은 사용자에게 비밀번호 길이에 대한 구체적인 오류 메시지를 전달합니다.    
```sh
<form>
  <label for="password">Password:</label>
  <input type="password" id="password" aria-invalid="true" aria-errormessage="passwordError">
  <div id="passwordError" style="color: red; display: block;">Password must be at least 8 characters long.</div>
</form>
```

### **5. aria-expanded (state)**    
aria-expanded 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 상태(state) 속성으로, 사용자가 상호작용할 수 있는 UI 요소(예: 버튼, 링크, 메뉴)가 확장되었는지 또는 축소되었는지를 보조 기술(예: 스크린 리더)에 전달합니다. 이 속성은 주로 드롭다운 메뉴, 아코디언 패널, 트리 구조 등에서 사용되며, 사용자에게 현재 해당 요소의 상태를 명확하게 전달하는 역할을 합니다.       
[WAI-ARIA 1.2 Specification (aria-expanded)](https://www.w3.org/TR/wai-aria-1.2/#aria-expanded){: target="_blank"}   
[MDN Web Docs (aria-expanded)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-expanded){: target="_blank"}   

**aria-expanded 상태 값**    
- **true**: 요소가 확장된 상태임을 나타냅니다.    
- **false**: 요소가 축소된 상태임을 나타냅니다.   
- **(기본값) 없음**: 속성이 없거나 설정되지 않은 경우, 보조 기술은 확장/축소 상태를 인식하지 않습니다.         


**연관된 HTML 태그**   
- **button**: 확장 가능/축소 가능한 콘텐츠를 제어하는 버튼 요소.   
- **a**: 드롭다운 메뉴 또는 서브메뉴를 확장/축소하는 링크 요소.   
- **div**: 아코디언 패널이나 기타 확장 가능한 콘텐츠를 포함하는 컨테이너 요소.       

**사용 시 주의사항**   
- **명확한 상태 표시**: aria-expanded 속성은 UI 요소의 실제 상태와 항상 일치해야 합니다. 예를 들어, 드롭다운 메뉴가 열리면 aria-expanded="true"로 설정하고, 닫히면 aria-expanded="false"로 설정해야 합니다.    
- **동적 업데이트**: 사용자가 상호작용하여 요소의 상태가 변경될 때마다 aria-expanded 속성을 동적으로 업데이트해야 보조 기술이 이를 올바르게 인식할 수 있습니다.    
- **적용 대상 요소**: aria-expanded는 주로 버튼이나 링크와 같은 상호작용 가능한 요소에 사용되며, 이들이 제어하는 확장/축소 가능한 콘텐츠와 연결됩니다.       


**잘못된 예시**
이 예시에서는 aria-expanded 속성이 전혀 사용되지 않았기 때문에, 보조 기술이 콘텐츠가 확장되었는지 여부를 알 수 없습니다. 이로 인해 접근성이 떨어질 수 있습니다.    
```sh
<button>Toggle Content</button>
<div id="content">This is some content.</div>
```

**올바른 예시**
이 예시는 aria-expanded 속성을 올바르게 사용하여, 버튼이 제어하는 콘텐츠가 확장되었는지 여부를 보조 기술에 전달합니다. 사용자가 클릭할 때마다 속성이 동적으로 업데이트되어 정확한 상태를 반영합니다.    
```sh
<button aria-expanded="false" aria-controls="content">Toggle Content</button>
<div id="content" style="display: none;">This is some content.</div>

<script>
document.querySelector('button').addEventListener('click', function() {
    var content = document.getElementById('content');
    var expanded = this.getAttribute('aria-expanded') === 'true';
    this.setAttribute('aria-expanded', !expanded);
    content.style.display = expanded ? 'none' : 'block';
});
</script>
```

**기본 드롭다운 메뉴 예시**
이 예시는 버튼을 클릭하여 드롭다운 메뉴를 열고 닫을 수 있는 기본적인 드롭다운 메뉴 구현을 보여줍니다. aria-expanded 속성은 버튼이 제어하는 메뉴의 확장 상태를 명확히 나타내며, 사용자가 클릭할 때마다 동적으로 업데이트됩니다.    
```sh
<button aria-expanded="false" aria-controls="menu" id="dropdownButton">Menu</button>
<ul id="menu" style="display: none;">
  <li><a href="#">Option 1</a></li>
  <li><a href="#">Option 2</a></li>
  <li><a href="#">Option 3</a></li>
</ul>

<script>
document.getElementById('dropdownButton').addEventListener('click', function() {
    var menu = document.getElementById('menu');
    var expanded = this.getAttribute('aria-expanded') === 'true';
    this.setAttribute('aria-expanded', !expanded);
    menu.style.display = expanded ? 'none' : 'block';
});
</script>
```

**아코디언 패널 예시**
이 예시는 아코디언 패널을 구현한 예시입니다. 각 패널은 버튼으로 제어되며, aria-expanded 속성은 패널이 확장되었는지 또는 축소되었는지를 나타냅니다. 사용자가 패널을 클릭하여 상태를 변경할 때마다 aria-expanded가 동적으로 업데이트됩니다.    
```sh
<div>
  <button aria-expanded="false" aria-controls="section1" id="accordionButton1">Section 1</button>
  <div id="section1" style="display: none;">Content for section 1.</div>
  
  <button aria-expanded="false" aria-controls="section2" id="accordionButton2">Section 2</button>
  <div id="section2" style="display: none;">Content for section 2.</div>
</div>

<script>
document.querySelectorAll('button[aria-expanded]').forEach(button => {
    button.addEventListener('click', function() {
        var content = document.getElementById(this.getAttribute('aria-controls'));
        var expanded = this.getAttribute('aria-expanded') === 'true';
        this.setAttribute('aria-expanded', !expanded);
        content.style.display = expanded ? 'none' : 'block';
    });
});
</script>
```

**부가 활용 예시**
이 예시는 링크 요소를 사용하여 서브메뉴를 확장/축소하는 예시입니다. aria-expanded 속성이 링크에 적용되어, 사용자가 서브메뉴의 현재 상태를 알 수 있도록 합니다. 링크를 클릭할 때 서브메뉴의 상태가 동적으로 업데이트됩니다.    
```sh
<a href="#" aria-expanded="false" aria-controls="submenu" id="submenuLink">Submenu</a>
<ul id="submenu" style="display: none;">
  <li><a href="#">Sub Option 1</a></li>
  <li><a href="#">Sub Option 2</a></li>
</ul>

<script>
document.getElementById('submenuLink').addEventListener('click', function(event) {
    event.preventDefault();
    var submenu = document.getElementById('submenu');
    var expanded = this.getAttribute('aria-expanded') === 'true';
    this.setAttribute('aria-expanded', !expanded);
    submenu.style.display = expanded ? 'none' : 'block';
});
</script>
```

### **6. aria-haspopup (property)**    
aria-haspopup 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, UI 요소가 팝업(popup)과 같은 추가적인 인터페이스 요소를 트리거할 수 있음을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 메뉴, 대화 상자, 트리 리스트, 그리드 등의 팝업 요소가 사용자 상호작용에 의해 나타나거나 열릴 수 있음을 명확히 전달합니다.       
[WAI-ARIA 1.2 Specification (aria-haspopup)](https://www.w3.org/TR/wai-aria-1.2/#aria-haspopup){: target="_blank"}   
[MDN Web Docs (aria-haspopup)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-haspopup){: target="_blank"}   

**aria-haspopup 속성 값**    
aria-haspopup 속성은 팝업의 유형을 지정하는 다양한 값을 가질 수 있습니다.   
- **false**: 팝업이 없음을 나타냅니다.   
- **true**: 팝업 메뉴가 있음을 나타냅니다(이 값은 menu 값과 동일합니다).   
- **menu**: 팝업 메뉴가 있음을 나타냅니다.   
- **listbox**: 팝업 목록 상자가 있음을 나타냅니다.   
- **tree**: 팝업 트리뷰가 있음을 나타냅니다.   
- **grid**: 팝업 그리드가 있음을 나타냅니다.   
- **dialog**: 팝업 대화 상자가 있음을 나타냅니다.          


**연관된 HTML 태그**   
- **button**: 메뉴, 대화 상자, 그리드 등의 팝업 요소를 트리거하는 버튼 요소.
- **a**: 서브메뉴나 팝업을 트리거하는 링크 요소.
- **div**: 커스텀 위젯에서 팝업 요소를 트리거하는 컨테이너.       

**사용 시 주의사항**   
- **적절한 값 선택**: aria-haspopup 속성은 요소가 트리거하는 팝업의 유형에 따라 적절한 값을 선택해야 합니다. 예를 들어, 메뉴를 트리거하는 요소에는 aria-haspopup="menu"를 사용합니다.   
- **팝업의 명확한 표시**: 이 속성을 사용하여 보조 기술에 팝업의 존재를 알리면, 사용자가 키보드나 스크린 리더로 상호작용할 때 팝업이 나타날 수 있음을 알 수 있습니다.   
- **연관된 속성들과 함께 사용**: aria-expanded, aria-controls 등의 속성과 함께 사용하여 팝업의 상태(예: 열림/닫힘)와 관계를 명확하게 전달할 수 있습니다.       


**잘못된 예시**
이 예시에서는 aria-haspopup 속성이 전혀 사용되지 않았기 때문에, 보조 기술이 버튼이 팝업 메뉴를 트리거할 수 있는지 여부를 알 수 없습니다.    
```sh
<button>Show Options</button>
<ul>
  <li><a href="#">Option 1</a></li>
  <li><a href="#">Option 2</a></li>
  <li><a href="#">Option 3</a></li>
</ul>
```

**올바른 예시**
이 예시는 aria-haspopup="menu" 속성을 사용하여, 버튼이 팝업 메뉴를 트리거할 수 있음을 보조 기술에 전달합니다. 이로 인해 접근성이 향상되며, 사용자가 버튼과 상호작용할 때 팝업 메뉴의 존재를 인식할 수 있습니다.    
```sh
<button aria-haspopup="menu" aria-controls="optionsMenu">Show Options</button>
<ul id="optionsMenu" style="display: none;">
  <li><a href="#">Option 1</a></li>
  <li><a href="#">Option 2</a></li>
  <li><a href="#">Option 3</a></li>
</ul>

<script>
document.querySelector('button[aria-haspopup="menu"]').addEventListener('click', function() {
    var menu = document.getElementById('optionsMenu');
    menu.style.display = menu.style.display === 'none' ? 'block' : 'none';
});
</script>
```

**aria-haspopup="menu" - 팝업 메뉴 트리거 예시**
이 예시는 버튼이 팝업 메뉴를 트리거하는 기본적인 메뉴 구현을 보여줍니다. aria-haspopup="menu"는 버튼이 메뉴를 열 수 있음을 나타내며, aria-expanded 속성은 메뉴가 열려 있는지 여부를 나타냅니다.    
```sh
<button aria-haspopup="menu" aria-expanded="false" aria-controls="menu" id="menuButton">Open Menu</button>
<ul id="menu" style="display: none;">
  <li><a href="#">Option 1</a></li>
  <li><a href="#">Option 2</a></li>
  <li><a href="#">Option 3</a></li>
</ul>

<script>
document.getElementById('menuButton').addEventListener('click', function() {
    var menu = document.getElementById('menu');
    var expanded = this.getAttribute('aria-expanded') === 'true';
    this.setAttribute('aria-expanded', !expanded);
    menu.style.display = expanded ? 'none' : 'block';
});
</script>
```

**aria-haspopup="listbox" - 팝업 목록 상자 예시**
이 예시는 링크가 목록 상자(listbox)를 트리거하는 상황을 보여줍니다. aria-haspopup="listbox" 속성을 통해 링크가 팝업 목록 상자를 열 수 있음을 명확히 나타냅니다.    
```sh
<a href="#" aria-haspopup="listbox" aria-controls="dropdownList" id="dropdownLink">Select an Option</a>
<ul id="dropdownList" role="listbox" style="display: none;">
  <li role="option">Option 1</li>
  <li role="option">Option 2</li>
  <li role="option">Option 3</li>
</ul>

<script>
document.getElementById('dropdownLink').addEventListener('click', function(event) {
    event.preventDefault();
    var listbox = document.getElementById('dropdownList');
    var isVisible = listbox.style.display === 'block';
    listbox.style.display = isVisible ? 'none' : 'block';
});
</script>
```

**aria-haspopup="tree" - 팝업 트리뷰 예시**
이 예시는 버튼이 트리뷰(treeview)를 트리거하는 상황을 보여줍니다. aria-haspopup="tree" 속성을 통해 이 버튼이 트리뷰를 열 수 있음을 보조 기술에 전달합니다.    
```sh
<button aria-haspopup="tree" aria-controls="treeMenu" id="treeButton">Toggle Tree Menu</button>
<ul id="treeMenu" role="tree" style="display: none;">
  <li role="treeitem">Item 1
    <ul role="group">
      <li role="treeitem">Sub-item 1</li>
      <li role="treeitem">Sub-item 2</li>
    </ul>
  </li>
  <li role="treeitem">Item 2</li>
</ul>

<script>
document.getElementById('treeButton').addEventListener('click', function() {
    var treeMenu = document.getElementById('treeMenu');
    var isVisible = treeMenu.style.display === 'block';
    treeMenu.style.display = isVisible ? 'none' : 'block';
});
</script>
```

**aria-haspopup="grid" - 팝업 그리드 예시**
이 예시는 버튼이 팝업 그리드(grid)를 트리거하는 상황을 보여줍니다. aria-haspopup="grid" 속성을 통해 이 버튼이 그리드를 열 수 있음을 명확히 나타냅니다.    
```sh
<button aria-haspopup="grid" aria-controls="gridMenu" id="gridButton">Show Grid</button>
<table id="gridMenu" role="grid" style="display: none;">
  <tr>
    <th role="columnheader">Header 1</th>
    <th role="columnheader">Header 2</th>
  </tr>
  <tr role="row">
    <td role="gridcell">Cell 1</td>
    <td role="gridcell">Cell 2</td>
  </tr>
  <tr role="row">
    <td role="gridcell">Cell 3</td>
    <td role="gridcell">Cell 4</td>
  </tr>
</table>

<script>
document.getElementById('gridButton').addEventListener('click', function() {
    var gridMenu = document.getElementById('gridMenu');
    var isVisible = gridMenu.style.display === 'block';
    gridMenu.style.display = isVisible ? 'none' : 'block';
});
</script>
```

**aria-haspopup="dialog" - 팝업 대화 상자 예시**
이 예시는 버튼을 클릭하여 대화 상자(dialog)를 트리거하는 예시입니다. aria-haspopup="dialog"는 이 버튼이 대화 상자를 열 수 있음을 나타내며, 대화 상자가 열리면 보조 기술은 이를 인식할 수 있습니다.    
```sh
<button aria-haspopup="dialog" aria-controls="dialog" id="openDialog">Open Dialog</button>
<div id="dialog" role="dialog" style="display: none;" aria-labelledby="dialogTitle">
  <h2 id="dialogTitle">Dialog Title</h2>
  <p>This is a dialog box.</p>
  <button id="closeDialog">Close</button>
</div>

<script>
document.getElementById('openDialog').addEventListener('click', function() {
    var dialog = document.getElementById('dialog');
    dialog.style.display = 'block';
    dialog.focus();
});

document.getElementById('closeDialog').addEventListener('click', function() {
    var dialog = document.getElementById('dialog');
    dialog.style.display = 'none';
});
</script>
```

### **7. aria-hidden (state)**    
aria-hidden 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 상태(state) 속성으로, 특정 UI 요소와 그 자식 요소들이 보조 기술(예: 스크린 리더)에 의해 무시되도록 설정합니다. 이 속성은 시각적으로는 표시되지만 보조 기술에서는 무시되어야 하는 콘텐츠를 숨기거나, 반대로 화면에는 보이지 않지만 보조 기술에서 접근 가능하게 할 때 사용됩니다.       
[WAI-ARIA 1.2 Specification (aria-hidden)](https://www.w3.org/TR/wai-aria-1.2/#aria-hidden){: target="_blank"}   
[MDN Web Docs (aria-hidden)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-hidden){: target="_blank"}   

**aria-hidden 상태 값**    
- **true**: 요소가 보조 기술에 의해 무시됨을 나타냅니다.   
- **false**: 요소가 보조 기술에 의해 접근 가능함을 나타냅니다(기본값으로 간주됨).   
- **(기본값) 없음**: 속성이 없으면 요소는 보조 기술에 의해 일반적으로 접근 가능합니다.          


**연관된 HTML 태그**   
- **모든 HTML 요소에 적용 가능**: div, span, section, header, footer, button, input, img 등          

**사용 시 주의사항**   
- **콘텐츠 숨기기**: aria-hidden="true"를 사용하여 보조 기술에서 특정 콘텐츠를 숨길 때는, 해당 콘텐츠가 시각적으로는 유효하더라도 보조 기술 사용자에게 혼동을 주지 않도록 해야 합니다.   
- **중복된 콘텐츠 피하기**: 이미 다른 방식으로 제공된 콘텐츠나 보조 기술이 처리할 필요가 없는 장식적 콘텐츠에 aria-hidden="true"를 적용하여 중복되는 내용을 피할 수 있습니다.   
- **동적 상태 변경**: 특정 상황에서만 보조 기술에 의해 무시되도록 하려면, aria-hidden 상태를 동적으로 업데이트할 수 있습니다.       


**잘못된 예시**
이 예시는 aria-hidden="true" 속성을 상호작용 가능한 요소(버튼)에 적용했기 때문에, 이 버튼은 시각적으로는 보이지만 스크린 리더에서는 완전히 무시됩니다. 이는 사용자의 접근성을 해칠 수 있습니다.    
```sh
<div aria-hidden="true">
  <button>Click me</button>
</div>
```

**올바른 예시**
상호작용 가능한 요소는 일반적으로 aria-hidden을 사용하지 않습니다. 대신, 이러한 요소는 보조 기술에서도 접근 가능하도록 해야 합니다.    
```sh
<div>
  <button>Click me</button>
</div>
```

**화면에 보이는 텍스트 숨기기 예시**
이 예시는 aria-hidden="true"를 사용하여, 이 텍스트가 화면에는 보이지만 스크린 리더와 같은 보조 기술에서는 무시되도록 합니다. 이 방식은 장식적 텍스트나 중복된 정보에 유용합니다.    
```sh
<div aria-hidden="true">This text is visible on screen but hidden from screen readers.</div>
```

**대체 텍스트 제공 예시**
이 예시는 장식용 이미지를 스크린 리더에서 무시하도록 설정합니다. 이미지에 의미가 없으므로, aria-hidden="true"와 빈 alt 속성을 함께 사용하여 보조 기술이 이 이미지를 무시하도록 합니다.    
```sh
<div aria-hidden="true">
  <img src="decorative-image.jpg" alt="">
</div>
<p>This image is decorative and hidden from screen readers.</p>
```

**중복된 메뉴 항목 숨기기 예시**
이 예시는 중복된 메뉴 항목을 스크린 리더에서 숨기는 방법을 보여줍니다. aria-hidden="true"를 사용하여, 보조 기술이 중복된 항목을 무시하도록 설정합니다.    
```sh
<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li aria-hidden="true"><a href="#services">Services</a></li> <!-- Hidden from screen readers -->
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

**동적으로 요소 숨기기 예시**
이 예시는 버튼을 클릭하여 특정 콘텐츠의 가시성을 동적으로 전환하는 방법을 보여줍니다. aria-hidden 속성은 동적으로 업데이트되어 보조 기술에서 해당 요소가 무시될지 여부를 결정합니다.    
```sh
<div id="dynamicContent">This content may be hidden from screen readers.</div>
<button onclick="toggleVisibility()">Toggle Visibility</button>

<script>
function toggleVisibility() {
    var content = document.getElementById('dynamicContent');
    var isHidden = content.getAttribute('aria-hidden') === 'true';
    content.setAttribute('aria-hidden', !isHidden);
}
</script>
```

**부가 활용 예시**
이 예시는 장식용 아이콘을 aria-hidden="true"로 설정하여 스크린 리더에서 무시되도록 합니다. 스크린 리더는 별표 아이콘을 읽지 않고 "Save" 버튼만 사용자에게 전달합니다.    
```sh
<span class="icon" aria-hidden="true">★</span>
<button>Save</button>
```

### **8. aria-invalid (state)**    
aria-invalid 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 상태(state) 속성으로, 사용자 입력 필드의 현재 값이 유효하지 않음을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 폼 요소(예: 텍스트 입력, 체크박스 등)에서 사용되며, 사용자가 유효하지 않은 데이터를 입력했을 때 해당 요소에 aria-invalid 속성을 설정하여 이를 명확히 표시합니다.       
[WAI-ARIA 1.2 Specification (aria-invalid)](https://www.w3.org/TR/wai-aria-1.2/#aria-invalid){: target="_blank"}   
[MDN Web Docs (aria-invalid)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-invalid){: target="_blank"}   

**aria-invalid 상태 값**    
- **false**: 필드의 현재 값이 유효함을 나타냅니다(기본값).   
- **true**: 필드의 현재 값이 유효하지 않음을 나타냅니다.   
- **grammar**: 문법 오류가 있음을 나타냅니다(예: 텍스트에서 문법 오류가 발생한 경우).   
- **spelling**: 철자 오류가 있음을 나타냅니다(예: 텍스트에서 철자 오류가 발생한 경우).          


**연관된 HTML 태그**   
- **input**: 텍스트 입력 필드 요소.   
- **textarea**: 여러 줄의 텍스트 입력 요소.   
- **select**: 드롭다운 메뉴 요소.   
- **form**: 다양한 입력 필드를 포함하는 폼 요소.          

**사용 시 주의사항**   
- **정확한 상태 반영**: aria-invalid 속성은 필드의 실제 유효성 상태를 정확하게 반영해야 합니다. 유효하지 않은 필드에 대해 aria-invalid="true"를 설정하여 사용자가 문제를 인식할 수 있도록 해야 합니다.   
- **오류 메시지와 함께 사용**: aria-invalid 속성은 오류 메시지를 함께 제공하는 것이 일반적입니다. 이를 통해 사용자는 오류의 원인을 이해하고 수정할 수 있습니다.   
- **동적 업데이트**: 사용자가 입력을 수정하고 유효성을 검토할 때마다 aria-invalid 상태를 동적으로 업데이트하여 보조 기술이 최신 상태를 반영하도록 해야 합니다.       


**잘못된 예시**
이 예시는 aria-invalid="true" 속성이 설정된 상태에서 오류 메시지나 추가 설명이 제공되지 않기 때문에, 사용자는 필드가 왜 유효하지 않은지 이해할 수 없습니다.    
```sh
<input type="text" aria-invalid="true">
```

**올바른 예시**
이 예시는 오류 메시지를 함께 제공하여 사용자가 필드가 유효하지 않은 이유를 이해할 수 있도록 도와줍니다. aria-errormessage 속성은 오류 메시지와 필드를 연결합니다.    
```sh
<input type="text" aria-invalid="true" aria-errormessage="error1">
<div id="error1" style="color: red;">This field is required.</div>
```

**기본 입력 필드 예시**
이 예시는 사용자가 잘못된 이메일 주소를 입력했을 때 입력 필드에 aria-invalid="true"를 설정하여 유효하지 않음을 표시합니다. 오류 메시지는 aria-errormessage 속성을 통해 제공됩니다.    
```sh
<form>
  <label for="email">Email:</label>
  <input type="email" id="email" aria-invalid="true" aria-errormessage="emailError">
  <div id="emailError" style="color: red;">Please enter a valid email address.</div>
</form>
```

**동적 유효성 검사 예시**
이 예시는 사용자가 폼을 제출할 때 각 필드의 유효성을 동적으로 검사하여 aria-invalid 속성을 업데이트하는 방법을 보여줍니다. 유효하지 않은 필드에는 aria-invalid="true"가 설정되고, 이에 따른 오류 메시지가 표시됩니다.    
```sh
<form id="registrationForm">
  <label for="username">Username:</label>
  <input type="text" id="username" aria-invalid="false" aria-errormessage="usernameError">
  <div id="usernameError" style="color: red; display: none;">Username is required.</div>
  
  <label for="password">Password:</label>
  <input type="password" id="password" aria-invalid="false" aria-errormessage="passwordError">
  <div id="passwordError" style="color: red; display: none;">Password must be at least 8 characters long.</div>
  
  <button type="submit">Register</button>
</form>

<script>
document.getElementById('registrationForm').addEventListener('submit', function(event) {
    var isValid = true;

    // Username validation
    var username = document.getElementById('username');
    var usernameError = document.getElementById('usernameError');
    if (username.value.trim() === '') {
        username.setAttribute('aria-invalid', 'true');
        usernameError.style.display = 'block';
        isValid = false;
    } else {
        username.setAttribute('aria-invalid', 'false');
        usernameError.style.display = 'none';
    }

    // Password validation
    var password = document.getElementById('password');
    var passwordError = document.getElementById('passwordError');
    if (password.value.length < 8) {
        password.setAttribute('aria-invalid', 'true');
        passwordError.style.display = 'block';
        isValid = false;
    } else {
        password.setAttribute('aria-invalid', 'false');
        passwordError.style.display = 'none';
    }

    if (!isValid) {
        event.preventDefault(); // Prevent form submission if validation fails
    }
});
</script>
```

**문법 오류 예시**
이 예시는 텍스트 입력 필드에서 문법 오류가 있는 경우를 나타냅니다. aria-invalid="grammar"는 문법 오류가 있음을 나타내며, 보조 기술이 이를 사용자에게 전달할 수 있도록 합니다.    
```sh
<textarea aria-invalid="grammar" aria-errormessage="grammarError">This is an example sentence with a mistake</textarea>
<div id="grammarError" style="color: red;">There is a grammar error in your text.</div>
```

**철자 오류 예시**
이 예시는 텍스트 입력 필드에서 철자 오류가 있는 경우를 나타냅니다. aria-invalid="spelling"은 철자 오류가 있음을 나타내며, 보조 기술이 이를 사용자에게 알릴 수 있습니다.    
```sh
<textarea aria-invalid="spelling" aria-errormessage="spellingError">This is a smaple text with spelling errors.</textarea>
<div id="spellingError" style="color: red;">There are spelling errors in your text.</div>
```

**부가 활용 예시**
이 예시는 장식용 아이콘을 aria-hidden="true"로 설정하여 스크린 리더에서 무시되도록 합니다. 스크린 리더는 별표 아이콘을 읽지 않고 "Save" 버튼만 사용자에게 전달합니다.    
```sh
<select aria-invalid="false" id="countrySelect" aria-errormessage="countryError">
  <option value="">Select a country</option>
  <option value="usa">United States</option>
  <option value="canada">Canada</option>
</select>
<div id="countryError" style="color: red; display: none;">Please select a country.</div>

<script>
document.getElementById('countrySelect').addEventListener('change', function() {
    var error = document.getElementById('countryError');
    if (this.value === '') {
        this.setAttribute('aria-invalid', 'true');
        error.style.display = 'block';
    } else {
        this.setAttribute('aria-invalid', 'false');
        error.style.display = 'none';
    }
});
</script>
```

### **9. aria-label (property)**    
aria-label 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, 요소에 접근할 때 보조 기술(예: 스크린 리더)에 의해 사용자에게 읽히는 레이블을 제공하는 역할을 합니다. 이 속성은 요소에 시각적인 레이블이 없거나, 화면에 표시된 텍스트와는 다른 레이블을 제공해야 할 때 사용됩니다. 이 속성은 버튼, 입력 필드, 링크 등 다양한 요소에 사용되며, 사용자의 경험을 일관되게 유지하면서 접근성을 높이는 데 중요한 역할을 합니다.       
[WAI-ARIA 1.2 Specification (aria-label)](https://www.w3.org/TR/wai-aria-1.2/#aria-label){: target="_blank"}   
[MDN Web Docs (aria-label)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label){: target="_blank"}   

**aria-label 속성 값**    
- 문자열 값(String): 요소에 대한 대체 텍스트로, 보조 기술이 이 텍스트를 사용자에게 읽어줍니다. 예: "Submit", "Search", "Close menu".             


**연관된 HTML 태그**   
- **button**: 버튼 요소.   
- **input**: 텍스트 입력 필드 요소.   
- **a**: 링크 요소.   
- **div**, **span:** 다른 인터랙티브 요소와 함께 사용할 수 있는 컨테이너 요소.          

**사용 시 주의사항**   
- **명확한 레이블 제공**: aria-label의 값은 명확하고 간결한 텍스트로 설정되어야 하며, 요소의 목적을 이해할 수 있도록 해야 합니다.    
- **시각적 레이블과의 일관성 유지**: aria-label을 사용하는 경우, 요소에 시각적인 레이블이 없다면 스크린 리더 사용자와 시각적인 사용자 간에 일관된 경험을 제공하도록 해야 합니다.    
- **중복 레이블 피하기**: aria-label을 사용하여 레이블을 설정할 때는 중복되는 레이블이 없도록 주의해야 하며, 필요할 경우 aria-labelledby를 고려할 수 있습니다.       


**잘못된 예시**
이 버튼에는 레이블이 제공되지만, 버튼의 시각적인 요소가 전혀 없어서 시각적인 사용자들은 버튼의 목적을 알 수 없습니다. 레이블을 추가했더라도, 시각적으로도 사용자가 버튼의 기능을 인식할 수 있도록 해야 합니다.    
```sh
<button aria-label="Submit Form"></button>
```

**올바른 예시**
이 예시는 aria-label 속성을 사용해 보조 기술 사용자에게 "Submit Form"이라는 명확한 레이블을 제공하면서, 시각적인 사용자에게는 체크 아이콘을 통해 버튼의 기능을 인식할 수 있도록 설정합니다.    
```sh
<button aria-label="Submit Form">
  <span aria-hidden="true">✔</span> <!-- 시각적인 아이콘 또는 텍스트 제공 -->
</button>
```

**레이블이 없는 아이콘 버튼에 레이블 제공 예시**
이 예시는 시각적인 텍스트 레이블이 없는 아이콘 버튼에 aria-label="Close"를 추가하여, 보조 기술 사용자가 이 버튼의 목적을 이해할 수 있도록 합니다.    
```sh
<button aria-label="Close">
  <svg width="16" height="16" aria-hidden="true">
    <!-- SVG content -->
  </svg>
</button>
```

**검색 입력 필드에 레이블 제공 예시**
이 예시는 시각적인 레이블이 없고, placeholder 텍스트가 레이블 역할을 하지 않는 검색 입력 필드에 aria-label="Search"를 추가하여 보조 기술이 이 필드를 적절히 설명할 수 있도록 합니다.    
```sh
<input type="text" aria-label="Search" placeholder="Search...">
```

**링크 텍스트 대신 레이블 제공 예시**
이 예시는 링크의 시각적인 텍스트 대신, aria-label을 사용하여 더 구체적인 설명을 제공합니다. 시각적인 텍스트는 "More info"이지만, 스크린 리더 사용자에게는 "Learn more about our services"라고 읽히도록 설정되었습니다.    
```sh
<a href="#" aria-label="Learn more about our services">
  <span aria-hidden="true">More info</span>
</a>
```

**부가 활용 예시 - 가시적인 텍스트가 없는 스크린 리더 전용 레이블**
이 예시는 가시적인 텍스트가 없는 영역에 aria-label을 사용해 스크린 리더 전용 레이블을 제공합니다. 이 레이블은 "Navigation menu"로 설정되어 있어, 보조 기술 사용자가 이 영역의 목적을 이해할 수 있습니다.    
```sh
<div role="region" aria-label="Navigation menu" tabindex="0">
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</div>
```

### **10. aria-modal (property)**    
aria-modal 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, 현재 요소(일반적으로 대화 상자(dialog))가 모달 대화 상자임을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. aria-modal 속성은 대화 상자가 모달임을 보조 기술에 전달하여, 사용자가 모달이 열려 있는 동안 다른 UI 요소와 상호작용할 수 없음을 명확히 알리는 중요한 ARIA 속성입니다. 이 속성은 포커스 관리, 백그라운드 콘텐츠 비활성화 등의 기능과 함께 사용하여 모달 대화 상자가 제대로 작동하도록 해야 합니다. aria-modal 속성을 올바르게 사용하면 모달 인터페이스의 접근성을 크게 향상시킬 수 있습니다.       
[WAI-ARIA 1.2 Specification (aria-modal)](https://www.w3.org/TR/wai-aria-1.2/#aria-modal){: target="_blank"}   
[MDN Web Docs (aria-modal)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-modal){: target="_blank"}   

**aria-modal 속성 값**    
- **true**: 현재 대화 상자가 모달임을 나타냅니다.   
- **false (기본값)**: 대화 상자가 모달이 아님을 나타냅니다(보통 설정되지 않음).             


**연관된 HTML 태그**   
- **div**: 모달 대화 상자로 사용될 수 있는 컨테이너 요소.   
- **dialog**: HTML5의 대화 상자 요소(이 요소에 aria-modal을 추가해 모달로 설정 가능).   
- **section**: 특정한 컨텐츠 영역을 모달로 설정할 때 사용.          

**사용 시 주의사항**   
- **포커스 관리**: aria-modal="true"를 사용하면, 모달 대화 상자가 열려 있을 때 포커스가 모달 내부에만 머물도록 해야 합니다. 사용자가 포커스를 모달 외부로 이동할 수 없도록 보장해야 합니다.   
- **배경 요소 비활성화**: 모달 대화 상자가 열려 있을 때, 사용자는 배경에 있는 다른 UI 요소와 상호작용할 수 없어야 하며, 이 상태를 시각적으로도 명확히 표시해야 합니다.   
- **닫기 기능 제공**: 모달 대화 상자에는 닫기 버튼을 제공해야 하며, Esc 키를 통해 모달을 닫을 수 있도록 하는 것이 일반적입니다.       


**잘못된 예시**
이 예시에서는 모달 대화 상자가 aria-modal="true"로 설정되어 있지만, 포커스 관리가 전혀 이루어지지 않았습니다. 이로 인해 사용자가 포커스를 모달 외부로 이동할 수 있게 되어, 모달의 목적이 손상될 수 있습니다.    
```sh
<div role="dialog" aria-modal="true">
  <p>This is a modal dialog without focus management.</p>
</div>
```

**올바른 예시**
이 예시는 aria-modal="true"를 사용하여 포커스 관리가 제대로 된 모달 대화 상자를 구현한 것입니다. 사용자는 Esc 키를 사용해 모달을 닫을 수 있고, 모달이 닫히면 포커스가 원래 위치로 돌아갑니다.    
```sh
<div id="modalDialog" role="dialog" aria-modal="true" aria-labelledby="dialogTitle" style="display:none;">
  <h2 id="dialogTitle">Dialog Title</h2>
  <p>This modal dialog properly manages focus.</p>
  <button id="closeDialog">Close</button>
</div>

<script>
document.getElementById('closeDialog').addEventListener('click', function() {
    var modal = document.getElementById('modalDialog');
    modal.style.display = 'none';
    document.getElementById('openDialog').focus();
});

document.addEventListener('keydown', function(event) {
    var modal = document.getElementById('modalDialog');
    if (event.key === 'Escape' && modal.style.display === 'block') {
        modal.style.display = 'none';
        document.getElementById('openDialog').focus();
    }
});
</script>
```

**기본 모달 대화 상자 예시**
이 예시는 버튼을 클릭하여 모달 대화 상자를 열고, 모달 내부에서만 포커스가 유지되도록 설정한 것입니다. aria-modal="true" 속성은 대화 상자가 모달임을 명확히 나타내며, 사용자가 다른 UI 요소와 상호작용할 수 없도록 합니다.    
```sh
<button id="openModal">Open Modal</button>

<div id="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" style="display:none;">
  <h2 id="modalTitle">Modal Title</h2>
  <p>This is a modal dialog.</p>
  <button id="closeModal">Close</button>
</div>

<script>
document.getElementById('openModal').addEventListener('click', function() {
    var modal = document.getElementById('modal');
    modal.style.display = 'block';
    modal.querySelector('button').focus();
});

document.getElementById('closeModal').addEventListener('click', function() {
    var modal = document.getElementById('modal');
    modal.style.display = 'none';
    document.getElementById('openModal').focus();
});

document.addEventListener('keydown', function(event) {
    var modal = document.getElementById('modal');
    if (event.key === 'Escape' && modal.style.display === 'block') {
        modal.style.display = 'none';
        document.getElementById('openModal').focus();
    }
});
</script>
```

**다양한 콘텐츠를 포함한 모달**
이 예시는 사용자가 중요한 정보를 포함한 모달 대화 상자를 열고, 이를 확인한 후 닫는 기능을 제공합니다. 모달이 열리면 보조 기술은 aria-modal="true"를 사용해 이 상태를 인식합니다.    
```sh
<button id="launchModal">Launch Info Modal</button>

<div id="infoModal" role="dialog" aria-modal="true" aria-labelledby="infoTitle" style="display:none;">
  <h2 id="infoTitle">Information</h2>
  <p>This modal contains important information.</p>
  <button id="closeInfoModal">Got it</button>
</div>

<script>
document.getElementById('launchModal').addEventListener('click', function() {
    var modal = document.getElementById('infoModal');
    modal.style.display = 'block';
    modal.querySelector('button').focus();
});

document.getElementById('closeInfoModal').addEventListener('click', function() {
    var modal = document.getElementById('infoModal');
    modal.style.display = 'none';
    document.getElementById('launchModal').focus();
});
</script>
```

**부가 활용 예시 - 백그라운드 콘텐츠 비활성화**
이 예시는 모달이 열릴 때 백그라운드 콘텐츠를 비활성화하고, 보조 기술에서 이를 숨기는 방법을 보여줍니다. 모달이 열리면 백그라운드 콘텐츠에 aria-hidden="true"를 설정하여 사용자가 모달 외부의 다른 콘텐츠와 상호작용할 수 없도록 합니다.    
```sh
<div id="pageContent" aria-hidden="true">
  <p>This is the main page content, which will be hidden when the modal is open.</p>
</div>

<div id="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" style="display:none;">
  <h2 id="modalTitle">Modal Title</h2>
  <p>This is a modal dialog.</p>
  <button id="closeModal">Close</button>
</div>

<script>
document.getElementById('openModal').addEventListener('click', function() {
    document.getElementById('modal').style.display = 'block';
    document.getElementById('pageContent').setAttribute('aria-hidden', 'true');
});

document.getElementById('closeModal').addEventListener('click', function() {
    document.getElementById('modal').style.display = 'none';
    document.getElementById('pageContent').removeAttribute('aria-hidden');
});
</script>
```

### **11. aria-multiline (property)**    
aria-multiline 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, UI 요소(예: 텍스트 입력 필드)가 여러 줄의 텍스트를 지원하는지 여부를 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 단일 줄 입력과 여러 줄 입력을 구분할 필요가 있는 상황에서 사용됩니다. 기본적인 HTML 요소인 textarea에서는 암시적으로 적용됩니다.        
[WAI-ARIA 1.2 Specification (aria-multiline)](https://www.w3.org/TR/wai-aria-1.2/#aria-multiline){: target="_blank"}   
[MDN Web Docs (aria-multiline)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-multiline){: target="_blank"}   

**aria-multiline 속성 값**    
- **true**: 요소가 여러 줄의 텍스트를 지원함을 나타냅니다.   
- **false**: 요소가 단일 줄의 텍스트만 지원함을 나타냅니다(기본값).             


**연관된 HTML 태그**   
- **input**: 단일 줄 텍스트 입력 필드 (일반적으로 aria-multiline="false"로 설정).   
- **textarea**: 여러 줄 텍스트 입력 필드 (일반적으로 aria-multiline="true"로 설정).   
- **div role="textbox"**: 텍스트 입력이 가능한 커스텀 컨테이너.          

**사용 시 주의사항**   
- **정확한 값 설정**: aria-multiline 속성 값은 요소의 실제 동작과 일치해야 합니다. 여러 줄 입력이 가능한 경우 true, 단일 줄 입력만 가능한 경우 false로 설정합니다.   
- **보조 기술과의 호환성**: 스크린 리더 등 보조 기술은 이 속성을 통해 사용자가 입력하는 필드가 여러 줄을 지원하는지 알 수 있으므로, 올바른 사용이 중요합니다.   
- **기본 HTML 요소 고려**: textarea와 같은 기본 HTML 요소는 이미 여러 줄을 지원하므로, 추가적으로 aria-multiline 속성을 설정할 필요는 없습니다.       


**잘못된 예시**
이 예시에서는 단일 줄 텍스트 입력 필드에 aria-multiline="true"를 설정했습니다. 그러나 실제로는 단일 줄만 지원하기 때문에 이 설정은 오해를 불러일으킬 수 있습니다.    
```sh
<input type="text" aria-multiline="true" placeholder="Enter your name">
```

**올바른 예시**
이 예시는 단일 줄 텍스트 입력 필드에 aria-multiline="false"를 설정하여, 필드의 실제 동작과 일치하는 상태를 유지합니다.    
```sh
<input type="text" aria-multiline="false" placeholder="Enter your name">
```

**단일 줄 텍스트 입력 필드 예시**
이 예시는 단일 줄 텍스트 입력 필드를 나타냅니다. aria-multiline="false"로 설정되어 있으며, 보조 기술은 이 필드가 단일 줄 입력만 지원함을 인식합니다.    
```sh
<input type="text" aria-multiline="false" placeholder="Enter your name">
```

**여러 줄 텍스트 입력 필드 예시**
이 예시는 div 요소를 여러 줄 텍스트 입력 필드로 사용한 커스텀 구현입니다. aria-multiline="true"로 설정하여, 보조 기술이 이 필드가 여러 줄을 지원함을 알 수 있도록 합니다.    
```sh
<div role="textbox" aria-multiline="true" contenteditable="true" style="border: 1px solid #ccc; padding: 8px;">
  Enter your comments here...
</div>
```

**자동 줄바꿈 지원 입력 필드 예시**
이 예시는 textarea 요소를 사용한 기본적인 여러 줄 텍스트 입력 필드입니다. aria-multiline 속성은 기본적으로 true로 간주되므로, 추가 설정 없이도 보조 기술은 여러 줄 입력을 인식합니다.    
```sh
<textarea aria-multiline="true" rows="4" cols="50" placeholder="Type your message here..."></textarea>
```

**부가 활용 예시 - 여러 줄을 지원하는 커스텀 입력 필드**
이 예시는 커스텀 입력 필드에서 여러 줄을 지원하는 상황을 보여줍니다. contenteditable 속성과 함께 사용하여 사용자가 자유롭게 텍스트를 입력할 수 있도록 하며, 보조 기술은 이를 적절히 인식합니다.    
```sh
<div role="textbox" aria-multiline="true" contenteditable="true" style="border: 1px solid #ccc; padding: 8px; min-height: 100px;">
  Start typing your text here...
</div>
```

### **12. aria-multiselectable (property)**    
aria-multiselectable 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, 사용자가 여러 항목을 선택할 수 있는 UI 요소임을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 role="listbox" 또는 role="grid" 같은 요소에서 사용되며, 이 속성은 다중 선택이 가능한 상황에서만 true로 설정해야 하며, 단일 선택만 가능한 경우에는 설정하지 않는 것이 좋습니다.         
[WAI-ARIA 1.2 Specification (aria-multiselectable)](https://www.w3.org/TR/wai-aria-1.2/#aria-multiselectable){: target="_blank"}   
[MDN Web Docs (aria-multiselectable)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-multiselectable){: target="_blank"}   

**aria-multiselectable 속성 값**    
- **true**: 요소에서 다중 선택이 가능함을 나타냅니다.   
- **false**: 요소에서 다중 선택이 불가능함을 나타냅니다(기본값).             


**연관된 HTML 태그 및 역할**   
- **div role="listbox"**: 다중 선택이 가능한 리스트박스 요소.   
- **div role="grid"**: 다중 선택이 가능한 그리드 요소.   
- **ul role="tree"**: 다중 선택이 가능한 트리뷰 요소.          

**사용 시 주의사항**   
- **적절한 값 설정**: aria-multiselectable 속성은 다중 선택이 실제로 가능한 경우에만 true로 설정해야 합니다. 그렇지 않으면, 보조 기술 사용자에게 잘못된 정보를 제공할 수 있습니다.   
- **연관된 역할과 함께 사용**: 이 속성은 주로 role="listbox", role="grid", role="tree"와 같은 역할을 가진 요소에 사용됩니다. 이러한 역할과 함께 사용하여 보조 기술이 UI 요소의 다중 선택 가능 여부를 올바르게 인식할 수 있도록 합니다.    
- **사용자 상호작용 고려**: 다중 선택이 가능하도록 설정할 때는, 사용자가 Shift 키나 Ctrl(Command) 키를 사용해 여러 항목을 선택할 수 있도록 해야 합니다.       


**잘못된 예시**
이 예시는 aria-multiselectable="true"를 사용하고 있지만, 여러 개의 옵션이 없는 상황에서는 다중 선택이 불가능하므로 이 속성을 설정할 필요가 없습니다.    
```sh
<div role="listbox" aria-multiselectable="true">
  <div role="option" aria-selected="true">Option 1</div>
</div>
```

**올바른 예시**
다중 선택이 불가능한 경우, aria-multiselectable="false"로 설정하여 보조 기술이 이를 올바르게 인식하도록 합니다.    
```sh
<div role="listbox" aria-multiselectable="false">
  <div role="option" aria-selected="true">Option 1</div>
</div>
```

**다중 선택 가능한 리스트박스 예시**
이 예시는 다중 선택이 가능한 리스트박스를 구현한 것입니다. aria-multiselectable="true" 속성을 사용하여 보조 기술이 사용자가 여러 옵션을 선택할 수 있음을 알 수 있도록 합니다.    
```sh
<div role="listbox" aria-multiselectable="true">
  <div role="option" aria-selected="false">Option 1</div>
  <div role="option" aria-selected="false">Option 2</div>
  <div role="option" aria-selected="false">Option 3</div>
  <div role="option" aria-selected="false">Option 4</div>
</div>

<script>
document.querySelectorAll('[role="option"]').forEach(option => {
    option.addEventListener('click', function(event) {
        if (event.ctrlKey || event.metaKey) {
            this.setAttribute('aria-selected', this.getAttribute('aria-selected') === 'true' ? 'false' : 'true');
        } else {
            document.querySelectorAll('[role="option"]').forEach(opt => opt.setAttribute('aria-selected', 'false'));
            this.setAttribute('aria-selected', 'true');
        }
    });
});
</script>
```

**다중 선택 가능한 그리드 예시**
이 예시는 다중 선택이 가능한 그리드를 구현한 것입니다. aria-multiselectable="true" 속성을 통해 사용자가 여러 그리드 셀을 선택할 수 있음을 나타냅니다.    
```sh
<div role="grid" aria-multiselectable="true">
  <div role="row">
    <div role="gridcell" aria-selected="false">Cell 1</div>
    <div role="gridcell" aria-selected="false">Cell 2</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-selected="false">Cell 3</div>
    <div role="gridcell" aria-selected="false">Cell 4</div>
  </div>
</div>

<script>
document.querySelectorAll('[role="gridcell"]').forEach(cell => {
    cell.addEventListener('click', function(event) {
        if (event.ctrlKey || event.metaKey) {
            this.setAttribute('aria-selected', this.getAttribute('aria-selected') === 'true' ? 'false' : 'true');
        } else {
            document.querySelectorAll('[role="gridcell"]').forEach(cell => cell.setAttribute('aria-selected', 'false'));
            this.setAttribute('aria-selected', 'true');
        }
    });
});
</script>
```

**다중 선택 가능한 트리뷰 예시**
이 예시는 다중 선택이 가능한 트리뷰를 구현한 것입니다. 사용자는 aria-multiselectable="true"로 설정된 트리뷰에서 여러 항목을 선택할 수 있습니다.    
```sh
<ul role="tree" aria-multiselectable="true">
  <li role="treeitem" aria-selected="false">Item 1</li>
  <li role="treeitem" aria-selected="false">Item 2</li>
  <li role="treeitem" aria-selected="false">Item 3</li>
</ul>

<script>
document.querySelectorAll('[role="treeitem"]').forEach(item => {
    item.addEventListener('click', function(event) {
        if (event.ctrlKey || event.metaKey) {
            this.setAttribute('aria-selected', this.getAttribute('aria-selected') === 'true' ? 'false' : 'true');
        } else {
            document.querySelectorAll('[role="treeitem"]').forEach(item => item.setAttribute('aria-selected', 'false'));
            this.setAttribute('aria-selected', 'true');
        }
    });
});
</script>
```

### **13. aria-orientation (property)**    
aria-orientation 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, UI 요소의 방향(orientation)을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 슬라이더, 탭, 목록 등 방향이 중요한 UI 요소에서 사용됩니다. aria-orientation 속성은 요소가 수직(vertical) 또는 수평(horizontal) 방향으로 배열되어 있는지를 명확하게 전달합니다.         
[WAI-ARIA 1.2 Specification (aria-orientation)](https://www.w3.org/TR/wai-aria-1.2/#aria-orientation){: target="_blank"}   
[MDN Web Docs (aria-orientation)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-orientation){: target="_blank"}   

**aria-orientation 속성 값**    
- **horizontal**: 요소가 수평으로 배열되어 있음을 나타냅니다.   
- **vertical**: 요소가 수직으로 배열되어 있음을 나타냅니다.   
- **(기본값) 없음**: 기본적으로 역할에 따라 자동으로 해석됩니다. 예를 들어, role="tablist"는 기본적으로 horizontal로 간주됩니다.             


**연관된 HTML 태그 및 역할**   
- **div role="slider"**: 슬라이더 요소.   
- **div role="tablist"**: 탭 리스트 요소.   
- **div role="listbox"**: 목록 박스 요소.   
- **div role="toolbar"**: 툴바 요소.     

**사용 시 주의사항**   
- **적절한 값 설정**: aria-orientation 속성은 요소의 실제 배열 방향에 따라 정확하게 설정해야 합니다. 예를 들어, 수직으로 배열된 탭 리스트는 aria-orientation="vertical"로 설정해야 합니다.   
- **역할에 따른 기본값 이해**: 일부 역할(예: role="tablist", role="toolbar")에는 기본적으로 수평 방향이 적용됩니다. 따라서 이 경우 명시적으로 aria-orientation을 설정하지 않아도 됩니다.   
- **사용자 상호작용 고려**: 사용자가 방향에 따라 키보드 내비게이션(예: 화살표 키)을 할 때, 올바르게 설정된 aria-orientation은 보조 기술이 사용자 경험을 정확하게 전달하는 데 도움을 줍니다.       


**잘못된 예시**
이 예시는 탭이 실제로는 수평으로 배열되어 있는데도 불구하고 aria-orientation="vertical"로 설정되었습니다. 이는 보조 기술 사용자에게 잘못된 정보를 제공할 수 있습니다.    
```sh
<div role="tablist" aria-orientation="vertical">
  <button role="tab" aria-selected="true" id="tab1">Tab 1</button>
  <button role="tab" aria-selected="false" id="tab2">Tab 2</button>
</div>
```

**올바른 예시**
이 예시는 탭이 실제로 수평으로 배열되어 있으며, aria-orientation="horizontal"로 올바르게 설정되어 있습니다.    
```sh
<div role="tablist" aria-orientation="horizontal">
  <button role="tab" aria-selected="true" id="tab1">Tab 1</button>
  <button role="tab" aria-selected="false" id="tab2">Tab 2</button>
</div>
```

**수평 탭 리스트 예시**
이 예시는 수평으로 배열된 탭 리스트를 나타냅니다. aria-orientation="horizontal" 속성은 탭이 수평으로 배치되어 있음을 보조 기술에 알립니다.    
```sh
<div role="tablist" aria-orientation="horizontal">
  <button role="tab" aria-selected="true" id="tab1">Tab 1</button>
  <button role="tab" aria-selected="false" id="tab2">Tab 2</button>
  <button role="tab" aria-selected="false" id="tab3">Tab 3</button>
</div>
```

**수직 슬라이더 예시**
이 예시는 수직으로 배열된 슬라이더를 나타냅니다. aria-orientation="vertical" 속성은 슬라이더가 수직 방향으로 동작함을 보조 기술에 전달합니다.    
```sh
<div role="slider" aria-orientation="vertical" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50" tabindex="0" style="height: 200px;">
  <!-- Visual representation of the slider -->
</div>
```

**수직 목록 박스 예시**
이 예시는 수직으로 배열된 목록 박스를 나타냅니다. aria-orientation="vertical" 속성은 옵션이 수직 방향으로 배열되어 있음을 보조 기술에 알립니다.    
```sh
<div role="listbox" aria-orientation="vertical">
  <div role="option" aria-selected="false">Option 1</div>
  <div role="option" aria-selected="true">Option 2</div>
  <div role="option" aria-selected="false">Option 3</div>
</div>
```

**부가 활용 예시 - 툴바에서의 방향 설정**
이 예시는 수직으로 배열된 툴바를 나타냅니다. 툴바의 버튼들이 수직으로 배치되어 있으므로, aria-orientation="vertical" 속성을 사용해 보조 기술이 이를 인식하도록 합니다.    
```sh
<div role="toolbar" aria-orientation="vertical">
  <button>Bold</button>
  <button>Italic</button>
  <button>Underline</button>
</div>
```

### **14. aria-placeholder (property)**    
aria-placeholder 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, 사용자가 입력할 수 있는 필드에 대한 설명 또는 힌트를 보조 기술(예: 스크린 리더)에 전달하는 데 사용됩니다. 이 속성은 일반적으로 사용자가 입력을 시작하기 전에 필드에 표시되는 힌트를 나타내는 텍스트를 지정합니다. 이 속성은 일반적인 placeholder 속성과 함께 또는 특별한 경우에 사용됩니다.         
[WAI-ARIA 1.2 Specification (aria-placeholder)](https://www.w3.org/TR/wai-aria-1.2/#aria-placeholder){: target="_blank"}   
[MDN Web Docs (aria-placeholder)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-placeholder){: target="_blank"}   

**aria-placeholder 속성 값**    
- **문자열 값(String)**: 필드에 입력될 예상 값에 대한 설명이나 힌트로 사용됩니다. 예: "Enter your name", "Type your message here".             


**연관된 HTML 태그**   
- **input**: 텍스트 입력 필드 요소.   
- **textarea**: 여러 줄 텍스트 입력 필드 요소.   
- **div role="textbox"**: 텍스트 입력이 가능한 커스텀 컨테이너.     

**사용 시 주의사항**   
- **일관된 사용자 경험**: aria-placeholder 속성은 시각적인 플레이스홀더(placeholder) 텍스트와 일관되게 사용해야 하며, 시각적으로 제공되지 않은 힌트를 보조 기술 사용자에게만 제공할 때 유용합니다.   
- **기본 placeholder 속성과의 차이**: HTML5의 placeholder 속성은 시각적으로 필드에 표시되며, aria-placeholder는 보조 기술을 위한 텍스트를 제공합니다. 그러나 placeholder 속성 자체가 이미 보조 기술에서 사용되므로, 보통 aria-placeholder는 특별한 경우에만 사용됩니다.   
- **사용자 상호작용 고려**: 입력 필드가 활성화될 때 플레이스홀더 텍스트는 일반적으로 사라지므로, aria-placeholder는 필드가 비어 있을 때만 유효한 설명으로 사용됩니다.       


**잘못된 예시**
이 예시는 aria-placeholder 속성에 빈 문자열을 사용하고 있어 보조 기술이 유효한 힌트를 제공할 수 없습니다. aria-placeholder 속성 값은 유용하고 명확한 힌트를 제공해야 합니다.    
```sh
<input type="text" aria-placeholder="">
```

**올바른 예시**
이 예시는 사용자에게 입력할 내용을 명확히 설명하는 aria-placeholder 속성을 사용합니다. 보조 기술은 이 정보를 사용자에게 전달하여 입력 필드의 용도를 이해하도록 도와줍니다.    
```sh
<input type="text" aria-placeholder="Enter your email address">
```

**텍스트 입력 필드에서의 힌트 제공 예시**
이 예시는 사용자가 입력해야 할 예상 값을 설명하기 위해 aria-placeholder="Enter your full name"을 추가하여, 보조 기술이 이를 사용자에게 전달하도록 설정합니다.    
```sh
<input type="text" aria-placeholder="Enter your full name">
```

**여러 줄 텍스트 입력 필드에서의 힌트 제공 예시**
이 예시는 여러 줄 텍스트 입력 필드에서 사용자에게 제공되는 힌트를 설명하기 위해 aria-placeholder 속성을 사용합니다. 이 속성은 보조 기술 사용자에게 입력 필드에 무엇을 입력해야 하는지 설명합니다.    
```sh
<textarea aria-placeholder="Type your detailed message here"></textarea>
```

**커스텀 텍스트 입력 필드에서의 힌트 제공 예시**
이 예시는 커스텀 텍스트 입력 필드에 힌트를 제공하기 위해 aria-placeholder 속성을 사용합니다. 시각적으로는 힌트를 제공하지 않지만, 보조 기술은 사용자에게 입력 필드의 목적을 설명합니다.    
```sh
<div role="textbox" aria-placeholder="Enter your address" contenteditable="true" style="border: 1px solid #ccc; padding: 8px;">
  <!-- User's input goes here -->
</div>
```

### **15. aria-pressed (state)**    
aria-pressed 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 상태(state) 속성으로, 버튼 요소가 눌려 있는 상태(즉, 활성화된 상태)인지 여부를 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 토글 버튼(toggle button)에서 사용되며, 사용자가 버튼을 누르거나 해제할 때 해당 버튼이 활성화되었는지 또는 비활성화되었는지를 명확히 전달합니다.         
[WAI-ARIA 1.2 Specification (aria-pressed)](https://www.w3.org/TR/wai-aria-1.2/#aria-pressed){: target="_blank"}   
[MDN Web Docs (aria-pressed)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-pressed){: target="_blank"}   

**aria-pressed 속성 값**    
- **true**: 버튼이 눌려 있는 상태(활성화된 상태)임을 나타냅니다.   
- **false**: 버튼이 눌려 있지 않은 상태(비활성화된 상태)임을 나타냅니다.   
- **mixed**: 버튼이 혼합 상태에 있음을 나타냅니다. 이 값은 주로 다중 선택 가능 항목에서 사용됩니다.   
- **undefined (속성이 설정되지 않음)**: 버튼이 토글 가능하지 않거나 아직 결정되지 않은 상태임을 나타냅니다.             


**연관된 HTML 태그**   
- **button**: 토글 버튼 역할을 하는 버튼 요소.   
- **div** 또는 **span**: 커스텀 버튼 요소(적절한 role="button"과 함께 사용).     

**사용 시 주의사항**   
- **정확한 상태 반영**: aria-pressed 속성은 버튼의 실제 상태와 일치해야 합니다. 사용자가 버튼을 누를 때마다 상태를 동적으로 업데이트해야 합니다.   
- **보조 기술에 명확한 정보 제공**: aria-pressed는 보조 기술이 버튼의 현재 상태를 명확하게 전달하는 데 도움을 주므로, 올바르게 설정하는 것이 중요합니다.   
- **단일 선택과 다중 선택 구분**: 단일 선택의 경우에는 true 또는 false로 설정하고, 다중 선택에서 혼합 상태를 나타내려면 mixed 값을 사용할 수 있습니다.       


**잘못된 예시**
이 예시는 aria-pressed="true"로 설정되어 있지만, 버튼의 상태가 동적으로 변경되지 않기 때문에 사용자가 상호작용할 때 버튼의 상태가 업데이트되지 않습니다. 이로 인해 사용자는 버튼의 현재 상태를 잘못 인식할 수 있습니다.    
```sh
<button aria-pressed="true">Press me</button>
```

**올바른 예시**
이 예시는 버튼이 클릭될 때마다 aria-pressed 속성이 동적으로 업데이트되어, 보조 기술이 버튼의 현재 상태를 정확하게 전달할 수 있도록 합니다.    
```sh
<button aria-pressed="true" id="dynamicButton">Press me</button>

<script>
document.getElementById('dynamicButton').addEventListener('click', function() {
    var pressed = this.getAttribute('aria-pressed') === 'true';
    this.setAttribute('aria-pressed', !pressed);
});
</script>
```

**스타일과 함께 상태 표시 예시**
이 예시는 버튼의 상태에 따라 스타일이 변경되는 토글 버튼을 구현한 것입니다. 버튼이 눌리면 배경색과 텍스트 색상이 변경되며, aria-pressed 속성이 업데이트됩니다.    
```sh
<button aria-pressed="false" id="styledButton" style="background-color: #f0f0f0; border: 1px solid #ccc; padding: 10px;">
  <span>Subscribe</span>
</button>

<script>
document.getElementById('styledButton').addEventListener('click', function() {
    var pressed = this.getAttribute('aria-pressed') === 'true';
    this.setAttribute('aria-pressed', !pressed);
    this.style.backgroundColor = pressed ? '#f0f0f0' : '#007BFF';
    this.style.color = pressed ? '#000' : '#FFF';
});
</script>
```

**기본 토글 버튼 예시**
이 예시는 텍스트 서식 설정에서 "Bold" 기능을 위한 토글 버튼을 구현한 것입니다. aria-pressed 속성은 사용자가 버튼을 클릭할 때마다 버튼의 상태를 동적으로 업데이트하여, 버튼이 활성화(눌림) 상태인지 비활성화 상태인지 보조 기술에 알립니다.    
```sh
<button aria-pressed="false" id="toggleButton">Bold</button>

<script>
document.getElementById('toggleButton').addEventListener('click', function() {
    var pressed = this.getAttribute('aria-pressed') === 'true';
    this.setAttribute('aria-pressed', !pressed);
});
</script>
```

**커스텀 토글 버튼 예시**
이 예시는 div 요소를 사용한 커스텀 토글 버튼을 구현한 것입니다. aria-pressed 속성은 버튼의 눌림 상태를 나타내며, 사용자가 클릭할 때마다 상태가 변경됩니다.    
```sh
<div role="button" aria-pressed="false" tabindex="0" id="customToggleButton" style="padding: 8px; border: 1px solid #ccc;">
  <span>Toggle Option</span>
</div>

<script>
document.getElementById('customToggleButton').addEventListener('click', function() {
    var pressed = this.getAttribute('aria-pressed') === 'true';
    this.setAttribute('aria-pressed', !pressed);
});
</script>
```

**혼합 상태(mixed) 토글 버튼 예시**
이 예시는 "Toggle All" 버튼에서 사용되는 혼합 상태(mixed) 예시입니다. 초기 상태는 mixed로 설정되어 있으며, 사용자가 클릭할 때마다 상태가 true 또는 false로 전환됩니다.    
```sh
<button aria-pressed="mixed" id="mixedStateButton">Toggle All</button>

<script>
document.getElementById('mixedStateButton').addEventListener('click', function() {
    var pressed = this.getAttribute('aria-pressed');
    this.setAttribute('aria-pressed', pressed === 'mixed' ? 'true' : 'false');
});
</script>
```

### **16. aria-readonly (property)**    
aria-readonly 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, 특정 UI 요소(예: 입력 필드, 스피너 등)가 읽기 전용 상태임을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 읽기 전용 상태는 사용자가 해당 요소의 내용을 변경할 수 없지만, 여전히 요소의 값을 선택하고 복사할 수 있는 상태를 의미합니다. 기본 HTML 요소에서는 readonly 속성을 사용하는 것이 더 권장되지만, 커스텀 ARIA 요소에서는 aria-readonly 속성을 사용할 수 있습니다.         
[WAI-ARIA 1.2 Specification (aria-readonly)](https://www.w3.org/TR/wai-aria-1.2/#aria-readonly){: target="_blank"}   
[MDN Web Docs (aria-readonly)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-readonly){: target="_blank"}   

**aria-readonly 속성 값**       
- **true**: 요소가 읽기 전용 상태임을 나타냅니다. 사용자는 값을 수정할 수 없지만, 선택 및 복사는 가능합니다.   
- **false (기본값)**: 요소가 읽기 전용 상태가 아님을 나타냅니다. 사용자는 값을 자유롭게 수정할 수 있습니다.             


**연관된 HTML 태그 및 역할**   
- **input**: 텍스트 입력 필드 요소.  
- **textarea**: 여러 줄 텍스트 입력 필드 요소.   
- **div role="textbox"**: 텍스트 입력이 가능한 커스텀 컨테이너.   
- **div role="spinbutton"**: 스피너(숫자 증감) 요소.   

**사용 시 주의사항**   
- **적절한 역할과 함께 사용**: aria-readonly는 텍스트 입력 필드, 스피너, 또는 기타 수정 가능한 요소에서만 사용해야 합니다.   
- **정확한 상태 반영**: aria-readonly 속성 값은 요소의 실제 동작과 일치해야 합니다. 읽기 전용인 경우 true, 수정 가능하다면 false로 설정해야 합니다.   
- **기본 HTML 속성과의 차이**: aria-readonly 속성은 주로 ARIA 역할을 사용한 커스텀 요소에 사용되며, HTML의 readonly 속성과 유사하지만, HTML5 요소에서는 readonly 속성을 사용하는 것이 권장됩니다.       


**잘못된 예시**
이 예시에서는 aria-readonly="true"가 설정되었지만, 기본적으로 HTML의 readonly 속성을 사용하는 것이 더 적절합니다. HTML 요소에서는 readonly 속성을 사용하는 것이 일반적입니다.    
```sh
<input type="text" aria-readonly="true">
```

**올바른 예시**
이 예시는 기본 HTML readonly 속성을 사용하여 텍스트 입력 필드를 읽기 전용으로 설정한 예시입니다. HTML 요소에서 readonly 속성을 사용하는 것이 더 권장됩니다.    
```sh
<input type="text" readonly value="This field is read-only">
```

**읽기 전용 텍스트 입력 필드 예시**
이 예시는 사용자가 값을 변경할 수 없는 읽기 전용 텍스트 입력 필드를 나타냅니다. aria-readonly="true" 속성은 보조 기술이 이 필드가 읽기 전용임을 인식하도록 합니다.    
```sh
<input type="text" aria-readonly="true" value="This field is read-only">
```

**읽기 전용 텍스트 영역 예시**
이 예시는 사용자가 내용을 수정할 수 없는 읽기 전용 텍스트 영역을 나타냅니다. 보조 기술은 aria-readonly="true" 속성을 통해 이 상태를 인식합니다.    
```sh
<textarea aria-readonly="true">This text cannot be edited by the user.</textarea>
```

**읽기 전용 스피너 예시**
이 예시는 숫자 증감이 불가능한 읽기 전용 스피너를 나타냅니다. aria-readonly="true" 속성은 사용자가 값을 변경할 수 없음을 보조 기술에 알립니다.    
```sh
<div role="spinbutton" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100" aria-readonly="true">
  10
</div>
```

**읽기 전용 커스텀 텍스트 입력 필드 예시**
이 예시는 div 요소를 사용한 커스텀 텍스트 입력 필드로, 읽기 전용 상태를 나타냅니다. aria-readonly="true" 속성은 이 필드가 사용자가 수정할 수 없는 상태임을 보조 기술에 전달합니다.    
```sh
<div role="textbox" aria-readonly="true" contenteditable="false" style="border: 1px solid #ccc; padding: 8px;">
  This is a read-only field.
</div>
```


### **17. aria-required (property)**    
aria-required 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, 특정 UI 요소(예: 입력 필드)가 사용자가 반드시 입력해야 하는 필수 항목임을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 폼 필드에서 사용되며, 해당 필드가 제출되기 전에 반드시 값이 입력되어야 함을 나타냅니다. HTML5 required 속성과 함께 사용하여 시각적 사용자와 보조 기술 사용자 모두에게 필수성을 전달하는 것이 권장됩니다.         
[WAI-ARIA 1.2 Specification (aria-required)](https://www.w3.org/TR/wai-aria-1.2/#aria-required){: target="_blank"}   
[MDN Web Docs (aria-required)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-required){: target="_blank"}   

**aria-required 속성 값**       
- **true**: 해당 필드가 필수 입력 항목임을 나타냅니다.   
- **false (기본값)**: 해당 필드가 필수 입력 항목이 아님을 나타냅니다.             


**연관된 HTML 태그 및 역할**   
- **input**: 텍스트 입력 필드 요소.   
- **textarea**: 여러 줄 텍스트 입력 필드 요소.   
- **select**: 드롭다운 선택 필드.  
- **div role="textbox"**: 텍스트 입력이 가능한 커스텀 컨테이너.   

**사용 시 주의사항**   
- **정확한 상태 반영**: aria-required 속성 값은 필드가 실제로 필수인지 여부에 따라 정확하게 설정해야 합니다. 필수 항목에는 true로, 필수가 아닌 항목에는 설정하지 않거나 false로 설정해야 합니다.    
- **기본 HTML 속성과의 차이**: HTML5의 required 속성은 시각적으로 필수 필드를 표시하고, 폼 제출 시 브라우저에서 기본 유효성 검사를 수행합니다. aria-required는 보조 기술에만 영향을 미치며, 시각적인 표현이나 기본 브라우저 유효성 검사에 영향을 주지 않습니다.   
- **일관된 사용자 경험**: aria-required와 required 속성을 함께 사용하는 경우, 보조 기술 사용자와 시각적 사용자 모두에게 일관된 경험을 제공할 수 있습니다.       


**잘못된 예시**
이 예시에서는 aria-required="true" 속성이 설정되어 있지만, 사용자에게 필수 입력 항목이라는 시각적 표시가 없습니다. 시각적 표시를 추가해야 사용자 경험이 일관됩니다.    
```sh
<input type="text" aria-required="true">
```

**올바른 예시**
이 예시는 HTML5 required 속성과 aria-required 속성을 함께 사용하여, 시각적 사용자와 보조 기술 사용자 모두에게 필수 입력 필드임을 명확히 전달합니다.    
```sh
<input type="text" aria-required="true" placeholder="Enter your name" required>
```

**필수 입력 텍스트 필드 예시**
이 예시는 필수 텍스트 필드를 포함한 폼을 구현한 것입니다. aria-required="true"와 required 속성을 함께 사용하여 필수 필드임을 명확히 하고, 폼 제출 시 필드가 비어 있을 경우 경고 메시지를 표시합니다.    
```sh
<form id="exampleForm">
  <label for="name">Name:</label>
  <input type="text" id="name" aria-required="true" placeholder="Enter your name" required>
  <button type="submit">Submit</button>
</form>

<script>
document.getElementById('exampleForm').addEventListener('submit', function(event) {
    var nameField = document.getElementById('name');
    if (nameField.value.trim() === '') {
        event.preventDefault();
        alert('The name field is required.');
        nameField.focus();
    }
});
</script>
```

**필수 입력 텍스트 영역 예시**
이 예시는 필수 입력이 필요한 텍스트 영역을 나타냅니다. aria-required="true"와 required 속성을 함께 사용하여, 사용자가 입력하지 않으면 폼 제출 시 경고 메시지를 표시합니다.    
```sh
<form id="messageForm">
  <label for="message">Message:</label>
  <textarea id="message" aria-required="true" placeholder="Enter your message" required></textarea>
  <button type="submit">Submit</button>
</form>

<script>
document.getElementById('messageForm').addEventListener('submit', function(event) {
    var messageField = document.getElementById('message');
    if (messageField.value.trim() === '') {
        event.preventDefault();
        alert('The message field is required.');
        messageField.focus();
    }
});
</script>
```

**필수 선택 드롭다운 메뉴 예시**
이 예시는 필수 선택 필드를 포함한 드롭다운 메뉴를 구현한 것입니다. aria-required="true"와 required 속성을 함께 사용하여 필수 선택 필드임을 나타내고, 선택하지 않고 폼을 제출하려고 하면 경고 메시지를 표시합니다.    
```sh
<form id="countryForm">
  <label for="country">Country:</label>
  <select id="country" aria-required="true" required>
    <option value="">Select a country</option>
    <option value="usa">United States</option>
    <option value="canada">Canada</option>
  </select>
  <button type="submit">Submit</button>
</form>

<script>
document.getElementById('countryForm').addEventListener('submit', function(event) {
    var countrySelect = document.getElementById('country');
    if (countrySelect.value === '') {
        event.preventDefault();
        alert('Please select a country.');
        countrySelect.focus();
    }
});
</script>
```

**커스텀 텍스트 입력 필드에서 필수 입력 설정**
이 예시는 div 요소를 사용한 커스텀 텍스트 입력 필드로, 필수 입력 항목임을 나타냅니다. aria-required="true" 속성은 보조 기술이 이 필드가 필수임을 인식할 수 있도록 하며, 사용자가 입력하지 않으면 폼 제출 시 경고 메시지를 표시합니다.    
```sh
<form id="customForm">
  <label for="customTextbox">Custom Textbox:</label>
  <div id="customTextbox" role="textbox" aria-required="true" contenteditable="true" style="border: 1px solid #ccc; padding: 8px;"></div>
  <button type="submit">Submit</button>
</form>

<script>
document.getElementById('customForm').addEventListener('submit', function(event) {
    var customTextbox = document.getElementById('customTextbox');
    if (customTextbox.textContent.trim() === '') {
        event.preventDefault();
        alert('The custom textbox is required.');
        customTextbox.focus();
    }
});
</script>
```

### **18. aria-selected (state)**    
aria-selected 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 상태(state) 속성으로, 특정 UI 요소(예: 목록 항목, 탭, 그리드 셀 등)가 현재 선택된 상태인지 여부를 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 사용자가 선택할 수 있는 여러 항목 중 하나가 선택되었음을 나타낼 때 사용됩니다. 모든 선택 가능한 항목에 이 속성을 명시적으로 설정하고, 사용자 상호작용에 따라 동적으로 상태를 업데이트하는 것이 중요합니다.         
[WAI-ARIA 1.2 Specification (aria-selected)](https://www.w3.org/TR/wai-aria-1.2/#aria-selected){: target="_blank"}   
[MDN Web Docs (aria-selected)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-selected){: target="_blank"}   

**aria-selected 속성 값**       
- **true**: 요소가 현재 선택된 상태임을 나타냅니다.   
- **false (기본값)**: 요소가 선택되지 않은 상태임을 나타냅니다.
- **(기본값 없음)**: 속성이 없으면 보조 기술에서 선택 상태를 알 수 없습니다.             


**연관된 HTML 태그 및 역할**   
- **div role="listbox"**: 리스트 박스에서 선택 가능한 항목.   
- **div role="tablist"**: 탭 리스트에서 선택된 탭.   
- **div role="grid"**: 그리드에서 선택된 셀.   
- **li role="option"**: 선택 가능한 리스트 아이템.   

**사용 시 주의사항**   
- **정확한 상태 반영**: aria-selected 속성 값은 요소의 실제 선택 상태를 정확하게 반영해야 합니다. 사용자가 항목을 선택하거나 선택 해제할 때 이 상태를 동적으로 업데이트해야 합니다.   
- **연관된 역할과 함께 사용**: aria-selected 속성은 role="option", role="tab", role="row" 등 선택 가능한 역할을 가진 요소에 주로 사용됩니다.   
- **단일 선택과 다중 선택 구분**: aria-selected는 단일 선택과 다중 선택 모두에 사용할 수 있으며, 이를 통해 보조 기술이 현재 선택된 항목을 명확히 전달할 수 있습니다.       


**잘못된 예시**
이 예시에서는 aria-selected 속성이 일부 옵션에만 설정되어 있어 보조 기술이 정확한 선택 상태를 인식하기 어려울 수 있습니다. 모든 선택 가능한 항목에 aria-selected 속성을 명시적으로 설정해야 합니다.    
```sh
<div role="listbox">
  <div role="option" aria-selected="false">Option 1</div>
  <div role="option">Option 2</div> <!-- aria-selected 속성이 누락됨 -->
  <div role="option" aria-selected="true">Option 3</div>
</div>
```

**올바른 예시**
이 예시는 모든 선택 가능한 항목에 aria-selected 속성이 명시적으로 설정되어 있으며, 보조 기술이 각 항목의 선택 상태를 정확하게 인식할 수 있습니다.    
```sh
<div role="listbox">
  <div role="option" aria-selected="false">Option 1</div>
  <div role="option" aria-selected="false">Option 2</div>
  <div role="option" aria-selected="true">Option 3</div>
</div>
```

**단일 선택 리스트 박스 예시**
이 예시는 단일 선택이 가능한 리스트 박스를 나타냅니다. aria-selected="true" 속성이 설정된 항목이 현재 선택된 항목임을 나타내며, 클릭 시 선택 상태가 동적으로 업데이트됩니다.    
```sh
<div role="listbox" id="singleSelectListbox">
  <div role="option" aria-selected="true" tabindex="0">Option 1</div>
  <div role="option" aria-selected="false" tabindex="-1">Option 2</div>
  <div role="option" aria-selected="false" tabindex="-1">Option 3</div>
</div>

<script>
document.getElementById('singleSelectListbox').addEventListener('click', function(event) {
    if (event.target.getAttribute('role') === 'option') {
        const options = this.querySelectorAll('[role="option"]');
        options.forEach(option => {
            option.setAttribute('aria-selected', 'false');
            option.setAttribute('tabindex', '-1');
        });
        event.target.setAttribute('aria-selected', 'true');
        event.target.setAttribute('tabindex', '0');
        event.target.focus();
    }
});
</script>
```

**다중 선택 리스트 박스 예시**
이 예시는 다중 선택이 가능한 리스트 박스를 나타냅니다. 사용자는 여러 항목을 선택할 수 있으며, 각 항목의 aria-selected 상태는 클릭 시 동적으로 업데이트됩니다.    
```sh
<div role="listbox" id="multiSelectListbox" aria-multiselectable="true">
  <div role="option" aria-selected="true" tabindex="0">Option 1</div>
  <div role="option" aria-selected="true" tabindex="0">Option 2</div>
  <div role="option" aria-selected="false" tabindex="0">Option 3</div>
</div>

<script>
document.getElementById('multiSelectListbox').addEventListener('click', function(event) {
    if (event.target.getAttribute('role') === 'option') {
        const isSelected = event.target.getAttribute('aria-selected') === 'true';
        event.target.setAttribute('aria-selected', !isSelected);
    }
});
</script>
```

**탭 리스트에서 선택된 탭 예시**
이 예시는 탭 리스트에서 선택된 탭을 나타냅니다. 사용자가 탭을 클릭할 때, 선택된 탭이 동적으로 업데이트되며, 선택된 탭의 콘텐츠가 표시됩니다.    
```sh
<div role="tablist" id="tabListExample">
  <button role="tab" aria-selected="false" tabindex="-1">Tab 1</button>
  <button role="tab" aria-selected="true" tabindex="0">Tab 2</button>
  <button role="tab" aria-selected="false" tabindex="-1">Tab 3</button>
</div>
<div role="tabpanel">Content for Tab 2</div>

<script>
document.getElementById('tabListExample').addEventListener('click', function(event) {
    if (event.target.getAttribute('role') === 'tab') {
        const tabs = this.querySelectorAll('[role="tab"]');
        tabs.forEach(tab => {
            tab.setAttribute('aria-selected', 'false');
            tab.setAttribute('tabindex', '-1');
        });
        event.target.setAttribute('aria-selected', 'true');
        event.target.setAttribute('tabindex', '0');
        event.target.focus();
    }
});
</script>
```

**키보드 내비게이션과 함께 사용하는 예시**
이 예시는 키보드 내비게이션을 통해 항목 간의 선택 상태를 변경하는 리스트 박스를 구현한 것입니다. 사용자가 ArrowDown 및 ArrowUp 키를 사용하여 항목 간에 이동하며, aria-selected 속성이 동적으로 업데이트됩니다.    
```sh
<div role="listbox" id="keyboardListbox" tabindex="0">
  <div role="option" aria-selected="true" tabindex="0">Option 1</div>
  <div role="option" aria-selected="false" tabindex="-1">Option 2</div>
  <div role="option" aria-selected="false" tabindex="-1">Option 3</div>
</div>

<script>
document.getElementById('keyboardListbox').addEventListener('keydown', function(event) {
    const options = this.querySelectorAll('[role="option"]');
    let currentIndex = Array.from(options).findIndex(option => option.getAttribute('aria-selected') === 'true');
    
    if (event.key === 'ArrowDown') {
        currentIndex = (currentIndex + 1) % options.length;
    } else if (event.key === 'ArrowUp') {
        currentIndex = (currentIndex - 1 + options.length) % options.length;
    }
    
    options.forEach(option => {
        option.setAttribute('aria-selected', 'false');
        option.setAttribute('tabindex', '-1');
    });
    
    options[currentIndex].setAttribute('aria-selected', 'true');
    options[currentIndex].setAttribute('tabindex', '0');
    options[currentIndex].focus();
});
</script>
```

**시멘틱 마크업을 활용한 탭 리스트 예시**
이 예시는 시멘틱 마크업을 활용한 탭 리스트를 나타냅니다. 각 탭은 aria-selected 속성을 통해 현재 선택된 상태를 나타내며, 클릭 시 선택된 탭과 연관된 패널의 콘텐츠가 표시됩니다. 이 예시는 시멘틱 HTML 요소인 &lt;ul&gt;와 &lt;li&gt;를 활용하여 더 구조화된 접근성을 제공합니다.    
```sh
<ul role="tablist">
  <li role="presentation"><button role="tab" aria-selected="true" id="tab1" aria-controls="panel1">Tab 1</button></li>
  <li role="presentation"><button role="tab" aria-selected="false" id="tab2" aria-controls="panel2">Tab 2</button></li>
  <li role="presentation"><button role="tab" aria-selected="false" id="tab3" aria-controls="panel3">Tab 3</button></li>
</ul>
<div id="panel1" role="tabpanel" aria-labelledby="tab1">Content for Tab 1</div>
<div id="panel2" role="tabpanel" aria-labelledby="tab2" hidden>Content for Tab 2</div>
<div id="panel3" role="tabpanel" aria-labelledby="tab3" hidden>Content for Tab 3</div>

<script>
document.querySelectorAll('[role="tab"]').forEach(tab => {
    tab.addEventListener('click', function() {
        const tabs = document.querySelectorAll('[role="tab"]');
        const panels = document.querySelectorAll('[role="tabpanel"]');
        
        tabs.forEach(t => {
            t.setAttribute('aria-selected', 'false');
            t.setAttribute('tabindex', '-1');
        });
        
        panels.forEach(p => p.hidden = true);
        
        this.setAttribute('aria-selected', 'true');
        this.setAttribute('tabindex', '0');
        document.getElementById(this.getAttribute('aria-controls')).hidden = false;
        this.focus();
    });
});
</script>
```

### **19. aria-sort (property)**    
aria-sort 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, 테이블이나 그리드 내의 열(column)이 현재 어떤 정렬 상태인지 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 열 헤더에 적용되며, 사용자가 데이터를 오름차순 또는 내림차순으로 정렬할 수 있는 상황에서 특히 유용합니다. aria-sort 속성을 올바르게 사용하면 보조 기술이 정렬 상태를 정확하게 전달할 수 있어 접근성이 향상됩니다. 시멘틱 마크업을 활용하여 구조화된 접근성을 제공하는 것도 좋은 방법입니다.         
[WAI-ARIA 1.2 Specification (aria-sort)](https://www.w3.org/TR/wai-aria-1.2/#aria-sort){: target="_blank"}   
[MDN Web Docs (aria-sort)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-sort){: target="_blank"}   

**aria-sort 속성 값**       
- **none**: 정렬되지 않은 상태를 나타냅니다. (기본값)   
- **ascending**: 오름차순 정렬 상태임을 나타냅니다.   
- **descending**: 내림차순 정렬 상태임을 나타냅니다.   
- **other**: 정렬이 되었지만 오름차순이나 내림차순이 아닌 다른 형태의 정렬 상태임을 나타냅니다.             


**연관된 HTML 태그 및 역할**   
- **th**: 테이블 헤더 셀.   
- **div role="columnheader"**: 그리드 또는 테이블 내의 열 헤더.   

**사용 시 주의사항**   
- **정렬 상태 반영**: aria-sort 속성은 열이 실제로 정렬된 상태를 정확히 반영해야 합니다. 사용자가 열을 클릭하여 정렬 상태를 변경할 때마다 이 속성을 동적으로 업데이트해야 합니다.   
- **보조 기술 호환성**: aria-sort는 스크린 리더와 같은 보조 기술이 현재 정렬 상태를 사용자에게 전달할 수 있도록 돕습니다. 시각적으로도 정렬 상태를 표시하는 것이 중요합니다.   
- **명확한 피드백 제공**: 사용자가 열을 클릭하여 정렬 상태를 변경할 때, 시각적인 피드백(예: 화살표 아이콘)과 함께 aria-sort 속성을 업데이트하면 사용자가 정렬 상태를 더 쉽게 인식할 수 있습니다.       


**잘못된 예시**
이 예시는 aria-sort 속성이 Age 열에만 설정되어 있으며, 사용자가 실제로 정렬 상태를 변경할 수 없습니다. 모든 열에 aria-sort 속성을 적용하고, 동적으로 상태를 업데이트해야 합니다.    
```sh
<table>
  <thead>
    <tr>
      <th id="nameHeader">Name</th>
      <th id="ageHeader" aria-sort="ascending">Age</th>
      <th id="cityHeader">City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>30</td>
      <td>New York</td>
    </tr>
    <tr>
      <td>Jane</td>
      <td>25</td>
      <td>Los Angeles</td>
    </tr>
  </tbody>
</table>
```

**올바른 예시**
이 예시는 모든 열에 aria-sort 속성이 명시적으로 설정되어 있으며, 보조 기술이 각 열의 정렬 상태를 정확하게 인식할 수 있습니다.   
```sh
<table>
  <thead>
    <tr>
      <th id="nameHeader" aria-sort="ascending">Name</th>
      <th id="ageHeader" aria-sort="none">Age</th>
      <th id="cityHeader" aria-sort="none">City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>30</td>
      <td>New York</td>
    </tr>
    <tr>
      <td>Jane</td>
      <td>25</td>
      <td>Los Angeles</td>
    </tr>
  </tbody>
</table>
```

**기본 테이블의 열 정렬 상태 예시**
이 예시는 기본 테이블의 열 헤더에 aria-sort 속성을 사용하여 현재 "Name" 열이 오름차순으로 정렬된 상태임을 나타냅니다. 다른 열은 정렬되지 않은 상태로 표시됩니다.    
```sh
<table>
  <thead>
    <tr>
      <th id="nameHeader" aria-sort="ascending">Name</th>
      <th id="ageHeader" aria-sort="none">Age</th>
      <th id="cityHeader" aria-sort="none">City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>30</td>
      <td>New York</td>
    </tr>
    <tr>
      <td>Jane</td>
      <td>25</td>
      <td>Los Angeles</td>
    </tr>
  </tbody>
</table>
```

**동적으로 정렬 상태를 변경하는 테이블 예시**
이 예시는 사용자가 열 헤더를 클릭할 때마다 aria-sort 속성이 동적으로 변경되는 테이블을 구현한 것입니다. 사용자가 헤더를 클릭할 때, 열의 정렬 상태가 오름차순, 내림차순, 또는 정렬되지 않은 상태로 순환됩니다.    
```sh
<table id="sortableTable">
  <thead>
    <tr>
      <th id="nameHeader" aria-sort="none">Name</th>
      <th id="ageHeader" aria-sort="none">Age</th>
      <th id="cityHeader" aria-sort="none">City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>30</td>
      <td>New York</td>
    </tr>
    <tr>
      <td>Jane</td>
      <td>25</td>
      <td>Los Angeles</td>
    </tr>
  </tbody>
</table>

<script>
document.querySelectorAll('#sortableTable th').forEach(header => {
    header.addEventListener('click', function() {
        const currentSort = this.getAttribute('aria-sort');
        let newSort;
        
        // Toggle the sort order
        if (currentSort === 'ascending') {
            newSort = 'descending';
        } else if (currentSort === 'descending') {
            newSort = 'none';
        } else {
            newSort = 'ascending';
        }
        
        // Update the aria-sort attribute
        document.querySelectorAll('#sortableTable th').forEach(th => th.setAttribute('aria-sort', 'none'));
        this.setAttribute('aria-sort', newSort);
        
        // Example logic to sort the table data (sorting logic not implemented)
        console.log(`Sorting ${this.textContent} column in ${newSort} order.`);
    });
});
</script>
```

### **20. aria-valuemax (property)**    
aria-valuemax 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, UI 요소(예: 슬라이더, 스피너 등)에서 허용되는 최대 값을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 사용자가 값을 조정할 수 있는 컨트롤에서 사용되며, 해당 컨트롤의 범위를 명확하게 정의합니다. 시멘틱 마크업을 활용하여 구조화된 접근성을 제공하는 것도 중요한 접근 방법입니다.         
[WAI-ARIA 1.2 Specification (aria-valuemax)](https://www.w3.org/TR/wai-aria-1.2/#aria-valuemax){: target="_blank"}   
[MDN Web Docs (aria-valuemax)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-valuemax){: target="_blank"}   

**aria-valuemax 속성 값**       
- **숫자 값**: 요소가 허용하는 최대 값을 나타냅니다. 이 값은 사용자에게 전달되며, 해당 요소에서 설정할 수 있는 최대 한도를 정의합니다.             


**연관된 HTML 태그 및 역할**   
- **input type="range"**: 슬라이더.   
- **div role="slider"**: 커스텀 슬라이더.   
- **div role="spinbutton"**: 스피너(숫자 증감) 요소.   
- **progress**: 진행률 표시 요소.   

**사용 시 주의사항**   
- **일관성 유지**: aria-valuemax 속성은 UI 요소의 실제 동작과 일치해야 하며, 사용자가 설정할 수 있는 최대 값보다 높거나 낮게 설정하면 안 됩니다.   
- **기본 HTML 속성과의 조화**: HTML5 요소(예: input type="range")는 이미 최대 값을 정의할 수 있는 속성(max)을 제공합니다. 이 경우, aria-valuemax 속성은 주로 커스텀 컨트롤에 사용되며, 이러한 속성과 함께 사용하면 보조 기술 사용자에게 일관된 정보를 전달할 수 있습니다.    
- **보조 기술과의 호환성**: 이 속성은 보조 기술이 요소의 범위를 인식하도록 돕기 때문에, 특히 시각적으로 요소의 범위를 이해하기 어려운 사용자에게 유용합니다.       


**잘못된 예시**
이 예시에서는 aria-valuemax="50"으로 설정되어 있지만, aria-valuenow 값이 50을 초과하고 있습니다. 이는 사용자가 최대 값보다 높은 값을 설정할 수 있음을 잘못 전달할 수 있습니다.    
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="50" aria-valuenow="60" tabindex="0">
  60
</div>
```

**올바른 예시**
이 예시는 aria-valuemax 값이 슬라이더의 실제 최대 값과 일치하며, 현재 값이 최대 값을 초과하지 않습니다. 보조 기술은 이 정보를 사용하여 올바른 범위를 전달할 수 있습니다.   
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50" tabindex="0">
  50
</div>
```

**기본 슬라이더 예시**
이 예시는 HTML5 슬라이더 요소를 사용하여 볼륨을 조정하는 슬라이더를 나타냅니다. aria-valuemax="100" 속성은 슬라이더의 최대 값이 100임을 보조 기술에 알립니다.    
```sh
<label for="volumeSlider">Volume</label>
<input type="range" id="volumeSlider" min="0" max="100" value="50" aria-valuemax="100">
```

**커스텀 슬라이더 예시**
이 예시는 커스텀 슬라이더를 구현한 것으로, aria-valuemax="200" 속성을 사용하여 슬라이더의 최대 값을 보조 기술에 전달합니다. 사용자는 키보드 화살표 키를 사용하여 슬라이더 값을 조정할 수 있습니다.    
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="200" aria-valuenow="100" tabindex="0" style="width: 200px; background: lightgray; height: 10px; position: relative;">
  <div id="sliderThumb" style="width: 10px; height: 20px; background: blue; position: absolute; left: 50%;"></div>
</div>

<script>
document.getElementById('sliderThumb').addEventListener('keydown', function(event) {
    const slider = this.parentElement;
    let currentValue = parseInt(slider.getAttribute('aria-valuenow'));
    const minValue = parseInt(slider.getAttribute('aria-valuemin'));
    const maxValue = parseInt(slider.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowRight') {
        currentValue = Math.min(maxValue, currentValue + 10);
    } else if (event.key === 'ArrowLeft') {
        currentValue = Math.max(minValue, currentValue - 10);
    }
    
    slider.setAttribute('aria-valuenow', currentValue);
    this.style.left = `${(currentValue / maxValue) * 100}%`;
});
</script>
```

**스피너 예시**
이 예시는 스피너 컨트롤을 구현한 것으로, aria-valuemax="10" 속성을 사용하여 스피너가 허용하는 최대 값이 10임을 나타냅니다. 사용자는 화살표 키를 사용하여 값을 증감할 수 있습니다.    
```sh
<div role="spinbutton" aria-valuemin="1" aria-valuemax="10" aria-valuenow="5" tabindex="0">
  5
</div>

<script>
document.querySelector('[role="spinbutton"]').addEventListener('keydown', function(event) {
    let currentValue = parseInt(this.getAttribute('aria-valuenow'));
    const minValue = parseInt(this.getAttribute('aria-valuemin'));
    const maxValue = parseInt(this.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowUp') {
        currentValue = Math.min(maxValue, currentValue + 1);
    } else if (event.key === 'ArrowDown') {
        currentValue = Math.max(minValue, currentValue - 1);
    }
    
    this.setAttribute('aria-valuenow', currentValue);
    this.textContent = currentValue;
});
</script>
```

**시멘틱 마크업을 활용한 진행률 표시 예시**
이 예시는 파일 업로드 진행률을 나타내는 progress 요소를 사용하여 시멘틱 마크업을 구현한 것입니다. aria-valuemax="100" 속성은 진행률의 최대 값이 100임을 보조 기술에 전달합니다.    
```sh
<progress id="fileProgress" max="100" value="50" aria-valuemax="100"></progress>
<label for="fileProgress">File Upload Progress</label>
```

### **21. aria-valuemin (property)**    
aria-valuemin 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, UI 요소(예: 슬라이더, 스피너 등)에서 허용되는 최소 값을 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 주로 사용자가 값을 조정할 수 있는 컨트롤에서 사용되며, 해당 컨트롤의 범위를 명확하게 정의합니다. 시멘틱 마크업을 활용하여 구조화된 접근성을 제공하는 것도 중요한 접근 방법입니다.         
[WAI-ARIA 1.2 Specification (aria-valuemin)](https://www.w3.org/TR/wai-aria-1.2/#aria-valuemin){: target="_blank"}   
[MDN Web Docs (aria-valuemin)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-valuemin){: target="_blank"}   

**aria-valuemin 속성 값**       
- **숫자 값**: 요소가 허용하는 최소 값을 나타냅니다. 이 값은 사용자에게 전달되며, 해당 요소에서 설정할 수 있는 최대 한도를 정의합니다.             


**연관된 HTML 태그 및 역할**   
- **input type="range"**: 슬라이더.   
- **div role="slider"**: 커스텀 슬라이더.   
- **div role="spinbutton"**: 스피너(숫자 증감) 요소.   
- **progress**: 진행률 표시 요소.   

**사용 시 주의사항**   
- **일관성 유지**: aria-valuemin 속성은 UI 요소의 실제 동작과 일치해야 하며, 사용자가 설정할 수 있는 최소 값보다 높거나 낮게 설정하면 안 됩니다.   
- **기본 HTML 속성과의 조화**: HTML5 요소(예: input type="range")는 이미 최소 값을 정의할 수 있는 속성(min)을 제공합니다. 이 경우, aria-valuemin 속성은 주로 커스텀 컨트롤에 사용되며, 이러한 속성과 함께 사용하면 보조 기술 사용자에게 일관된 정보를 전달할 수 있습니다.    
- **보조 기술과의 호환성**: 이 속성은 보조 기술이 요소의 범위를 인식하도록 돕기 때문에, 특히 시각적으로 요소의 범위를 이해하기 어려운 사용자에게 유용합니다.       


**잘못된 예시**
이 예시에서는 aria-valuemin="10"으로 설정되어 있지만, aria-valuenow 값이 10보다 작습니다. 이는 사용자가 최소 값보다 낮은 값을 설정할 수 있음을 잘못 전달할 수 있습니다.    
```sh
<div role="slider" aria-valuemin="10" aria-valuemax="50" aria-valuenow="5" tabindex="0">
  5
</div>
```

**올바른 예시**
이 예시는 aria-valuemin 값이 슬라이더의 실제 최소 값과 일치하며, 현재 값이 최소 값을 초과하지 않습니다. 보조 기술은 이 정보를 사용하여 올바른 범위를 전달할 수 있습니다.   
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50" tabindex="0">
  50
</div>
```

**기본 슬라이더 예시**
이 예시는 HTML5 슬라이더 요소를 사용하여 볼륨을 조정하는 슬라이더를 나타냅니다. aria-valuemin="0" 속성은 슬라이더의 최소 값이 0임을 보조 기술에 알립니다.    
```sh
<label for="volumeSlider">Volume</label>
<input type="range" id="volumeSlider" min="0" max="100" value="50" aria-valuemax="100">
```

**커스텀 슬라이더 예시**
이 예시는 커스텀 슬라이더를 구현한 것으로, aria-valuemin="0" 속성을 사용하여 슬라이더의 최소 값을 보조 기술에 전달합니다. 사용자는 키보드 화살표 키를 사용하여 슬라이더 값을 조정할 수 있습니다.    
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="200" aria-valuenow="100" tabindex="0" style="width: 200px; background: lightgray; height: 10px; position: relative;">
  <div id="sliderThumb" style="width: 10px; height: 20px; background: blue; position: absolute; left: 50%;"></div>
</div>

<script>
document.getElementById('sliderThumb').addEventListener('keydown', function(event) {
    const slider = this.parentElement;
    let currentValue = parseInt(slider.getAttribute('aria-valuenow'));
    const minValue = parseInt(slider.getAttribute('aria-valuemin'));
    const maxValue = parseInt(slider.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowRight') {
        currentValue = Math.min(maxValue, currentValue + 10);
    } else if (event.key === 'ArrowLeft') {
        currentValue = Math.max(minValue, currentValue - 10);
    }
    
    slider.setAttribute('aria-valuenow', currentValue);
    this.style.left = `${(currentValue / maxValue) * 100}%`;
});
</script>
```

**스피너 예시**
이 예시는 스피너 컨트롤을 구현한 것으로, aria-valuemin="1" 속성을 사용하여 스피너가 허용하는 최소 값이 1임을 나타냅니다. 사용자는 화살표 키를 사용하여 값을 증감할 수 있습니다.    
```sh
<div role="spinbutton" aria-valuemin="1" aria-valuemax="10" aria-valuenow="5" tabindex="0">
  5
</div>

<script>
document.querySelector('[role="spinbutton"]').addEventListener('keydown', function(event) {
    let currentValue = parseInt(this.getAttribute('aria-valuenow'));
    const minValue = parseInt(this.getAttribute('aria-valuemin'));
    const maxValue = parseInt(this.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowUp') {
        currentValue = Math.min(maxValue, currentValue + 1);
    } else if (event.key === 'ArrowDown') {
        currentValue = Math.max(minValue, currentValue - 1);
    }
    
    this.setAttribute('aria-valuenow', currentValue);
    this.textContent = currentValue;
});
</script>
```

**시멘틱 마크업을 활용한 진행률 표시 예시**
이 예시는 파일 업로드 진행률을 나타내는 progress 요소를 사용하여 시멘틱 마크업을 구현한 것입니다. aria-valuemin="0" 속성은 진행률의 최소 값이 0임을 보조 기술에 전달합니다.    
```sh
<progress id="fileProgress" max="100" value="50" aria-valuemax="100"></progress>
<label for="fileProgress">File Upload Progress</label>
```

### **22. aria-valuenow (property)**    
aria-valuenow 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, UI 요소(예: 슬라이더, 스피너 등)에서 현재 선택된 값 또는 상태를 보조 기술(예: 스크린 리더)에 알리는 데 사용됩니다. 이 속성은 사용자가 값을 조정할 수 있는 컨트롤에서 사용되며, 해당 컨트롤의 현재 값을 명확하게 전달합니다. 시멘틱 마크업을 활용하여 구조화된 접근성을 제공하는 것도 중요한 접근 방법입니다.         
[WAI-ARIA 1.2 Specification (aria-valuenow)](https://www.w3.org/TR/wai-aria-1.2/#aria-valuenow){: target="_blank"}   
[MDN Web Docs (aria-valuenow)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-valuenow){: target="_blank"}   

**aria-valuenow 속성 값**       
- **숫자 값**: 요소의 현재 값을 나타냅니다. 이 값은 보조 기술을 통해 사용자에게 전달되며, 해당 요소의 현재 상태를 명확하게 정의합니다.             


**연관된 HTML 태그 및 역할**   
- **input type="range"**: 슬라이더.   
- **div role="slider"**: 커스텀 슬라이더.   
- **div role="spinbutton"**: 스피너(숫자 증감) 요소.   
- **progress**: 진행률 표시 요소.   

**사용 시 주의사항**   
- **정확한 값 반영**: aria-valuenow 속성은 요소의 실제 상태와 일치해야 하며, 사용자 상호작용에 따라 동적으로 업데이트되어야 합니다.   
- **기본 HTML 속성과의 조화**: HTML5 요소(예: input type="range")는 이미 현재 값을 정의할 수 있는 속성(value)을 제공합니다. 이 경우, aria-valuenow 속성은 주로 커스텀 컨트롤에 사용되며, 이러한 속성과 함께 사용하면 보조 기술 사용자에게 일관된 정보를 전달할 수 있습니다.    
- **보조 기술과의 호환성**: 이 속성은 보조 기술이 요소의 범위를 인식하도록 돕기 때문에, 특히 시각적으로 요소의 범위를 이해하기 어려운 사용자에게 유용합니다.       


**잘못된 예시**
이 예시에서는 aria-valuenow="150"으로 설정되어 있지만, 이는 aria-valuemax="100"을 초과하는 값입니다. 이는 사용자가 최대 값보다 높은 값을 설정할 수 있음을 잘못 전달할 수 있습니다.    
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="100" aria-valuenow="150" tabindex="0">
  150
</div>
```

**올바른 예시**
이 예시는 aria-valuenow 값이 슬라이더의 현재 값과 일치하며, 최대 값 또는 최소 값을 초과하지 않습니다. 보조 기술은 이 정보를 사용하여 올바른 상태를 전달할 수 있습니다.   
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50" tabindex="0">
  50
</div>
```

**기본 슬라이더 예시**
이 예시는 HTML5 슬라이더 요소를 사용하여 볼륨을 조정하는 슬라이더를 나타냅니다. aria-valuenow="50" 속성은 슬라이더의 현재 값이 50임을 보조 기술에 알립니다.    
```sh
<label for="volumeSlider">Volume</label>
<input type="range" id="volumeSlider" min="0" max="100" value="50" aria-valuenow="50">
```

**커스텀 슬라이더 예시**
이 예시는 커스텀 슬라이더를 구현한 것으로, aria-valuenow="100" 속성을 사용하여 슬라이더의 현재 값을 보조 기술에 전달합니다. 사용자는 키보드 화살표 키를 사용하여 슬라이더 값을 조정할 수 있습니다.    
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="200" aria-valuenow="100" tabindex="0" style="width: 200px; background: lightgray; height: 10px; position: relative;">
  <div id="sliderThumb" style="width: 10px; height: 20px; background: blue; position: absolute; left: 50%;"></div>
</div>

<script>
document.getElementById('sliderThumb').addEventListener('keydown', function(event) {
    const slider = this.parentElement;
    let currentValue = parseInt(slider.getAttribute('aria-valuenow'));
    const minValue = parseInt(slider.getAttribute('aria-valuemin'));
    const maxValue = parseInt(slider.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowRight') {
        currentValue = Math.min(maxValue, currentValue + 10);
    } else if (event.key === 'ArrowLeft') {
        currentValue = Math.max(minValue, currentValue - 10);
    }
    
    slider.setAttribute('aria-valuenow', currentValue);
    this.style.left = `${(currentValue / maxValue) * 100}%`;
});
</script>
```

**스피너 예시**
이 예시는 스피너 컨트롤을 구현한 것으로, aria-valuenow="5" 속성을 사용하여 스피너의 현재 값이 5임을 나타냅니다. 사용자는 화살표 키를 사용하여 값을 증감할 수 있으며, aria-valuenow 속성이 동적으로 업데이트됩니다.    
```sh
<div role="spinbutton" aria-valuemin="1" aria-valuemax="10" aria-valuenow="5" tabindex="0">
  5
</div>

<script>
document.querySelector('[role="spinbutton"]').addEventListener('keydown', function(event) {
    let currentValue = parseInt(this.getAttribute('aria-valuenow'));
    const minValue = parseInt(this.getAttribute('aria-valuemin'));
    const maxValue = parseInt(this.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowUp') {
        currentValue = Math.min(maxValue, currentValue + 1);
    } else if (event.key === 'ArrowDown') {
        currentValue = Math.max(minValue, currentValue - 1);
    }
    
    this.setAttribute('aria-valuenow', currentValue);
    this.textContent = currentValue;
});
</script>
```

**시멘틱 마크업을 활용한 진행률 표시 예시**
이 예시는 파일 업로드 진행률을 나타내는 progress 요소를 사용하여 시멘틱 마크업을 구현한 것입니다. aria-valuenow="50" 속성은 진행률의 현재 값이 50%임을 보조 기술에 전달합니다.    
```sh
<progress id="fileProgress" max="100" value="50" aria-valuenow="50"></progress>
<label for="fileProgress">File Upload Progress</label>
```

### **23. aria-valuetext (property)**    
aria-valuetext 속성은 ARIA(Accessible Rich Internet Applications)에서 사용하는 속성(Property)으로, UI 요소(예: 슬라이더, 스피너 등)에서 현재 선택된 값의 의미를 텍스트로 보조 기술(예: 스크린 리더)에 전달하는 데 사용됩니다. 이 속성은 숫자 값(aria-valuenow)을 보다 의미 있는 텍스트로 변환해 사용자에게 제공할 수 있게 합니다. 예를 들어, 슬라이더가 "50"이라는 숫자를 나타내고 있을 때, aria-valuetext를 통해 "중간"이라는 텍스트를 제공할 수 있습니다. 시멘틱 마크업을 활용하여 구조화된 접근성을 제공하는 것도 중요한 접근 방법입니다.         
[WAI-ARIA 1.2 Specification (aria-valuetext)](https://www.w3.org/TR/wai-aria-1.2/#aria-valuetext){: target="_blank"}   
[MDN Web Docs (aria-valuetext)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-valuetext){: target="_blank"}   

**aria-valuetext 속성 값**       
- **문자열 값**: 요소의 현재 값을 텍스트로 표현한 문자열. 이 문자열은 보조 기술을 통해 사용자에게 제공됩니다.             


**연관된 HTML 태그 및 역할**   
- **input type="range"**: 슬라이더.   
- **div role="slider"**: 커스텀 슬라이더.   
- **div role="spinbutton"**: 스피너(숫자 증감) 요소.   
- **progress**: 진행률 표시 요소.   

**사용 시 주의사항**   
- **숫자 값과 의미의 조화**: aria-valuetext는 aria-valuenow 속성으로 전달되는 숫자 값을 보다 의미 있는 텍스트로 변환하는 데 사용됩니다. 숫자가 직관적이지 않거나 추가 설명이 필요할 때 사용됩니다.   
- **일관된 정보 제공**: aria-valuetext를 설정할 때, 이 텍스트는 요소의 현재 값을 잘 설명해야 하며, 보조 기술 사용자에게 혼동을 주지 않도록 해야 합니다.    
- **보조 기술과의 호환성**: 이 속성은 보조 기술이 요소의 범위를 인식하도록 돕기 때문에, 특히 시각적으로 요소의 범위를 이해하기 어려운 사용자에게 유용합니다.       


**잘못된 예시**
이 예시에서는 aria-valuenow="50"과 aria-valuetext="150"이 일치하지 않습니다. 이로 인해 보조 기술 사용자가 혼란을 겪을 수 있습니다. aria-valuetext는 aria-valuenow와 의미가 일치하는 텍스트로 설정해야 합니다.    
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50" aria-valuetext="150" tabindex="0">
  50
</div>
```

**올바른 예시**
이 예시는 aria-valuenow 값이 50이고, aria-valuetext가 이를 설명하는 "Medium"으로 설정되어 있으며, 보조 기술 사용자에게 일관된 정보를 제공합니다.   
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50" aria-valuetext="Medium" tabindex="0">
  50
</div>
```

**기본 슬라이더 예시**
이 예시는 HTML5 슬라이더 요소를 사용하여 볼륨을 조정하는 슬라이더를 나타냅니다. aria-valuetext="Medium" 속성은 슬라이더의 현재 값이 50일 때, 이를 "Medium"이라는 텍스트로 설명합니다.    
```sh
<label for="volumeSlider">Volume</label>
<input type="range" id="volumeSlider" min="0" max="100" value="50" aria-valuenow="50" aria-valuetext="Medium">
```

**커스텀 슬라이더 예시**
이 예시는 커스텀 슬라이더를 구현한 것으로, aria-valuenow="100"과 함께 aria-valuetext="Halfway" 속성을 사용하여 슬라이더의 현재 값을 보조 기술에 전달합니다. 사용자가 슬라이더 값을 변경할 때, 해당 값에 대한 텍스트 설명도 동적으로 업데이트됩니다.    
```sh
<div role="slider" aria-valuemin="0" aria-valuemax="200" aria-valuenow="100" aria-valuetext="Halfway" tabindex="0" style="width: 200px; background: lightgray; height: 10px; position: relative;">
  <div id="sliderThumb" style="width: 10px; height: 20px; background: blue; position: absolute; left: 50%;"></div>
</div>

<script>
document.getElementById('sliderThumb').addEventListener('keydown', function(event) {
    const slider = this.parentElement;
    let currentValue = parseInt(slider.getAttribute('aria-valuenow'));
    const minValue = parseInt(slider.getAttribute('aria-valuemin'));
    const maxValue = parseInt(slider.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowRight') {
        currentValue = Math.min(maxValue, currentValue + 10);
    } else if (event.key === 'ArrowLeft') {
        currentValue = Math.max(minValue, currentValue - 10);
    }
    
    slider.setAttribute('aria-valuenow', currentValue);
    slider.setAttribute('aria-valuetext', currentValue === 100 ? "Halfway" : currentValue);
    this.style.left = `${(currentValue / maxValue) * 100}%`;
});
</script>
```

**스피너 예시**
이 예시는 스피너 컨트롤을 구현한 것으로, aria-valuenow="5"와 함께 aria-valuetext="Five" 속성을 사용하여 현재 값을 텍스트로 표현합니다. 사용자가 값을 변경할 때, aria-valuetext가 동적으로 업데이트됩니다.    
```sh
<div role="spinbutton" aria-valuemin="1" aria-valuemax="10" aria-valuenow="5" aria-valuetext="Five" tabindex="0">
  5
</div>

<script>
document.querySelector('[role="spinbutton"]').addEventListener('keydown', function(event) {
    let currentValue = parseInt(this.getAttribute('aria-valuenow'));
    const minValue = parseInt(this.getAttribute('aria-valuemin'));
    const maxValue = parseInt(this.getAttribute('aria-valuemax'));
    
    if (event.key === 'ArrowUp') {
        currentValue = Math.min(maxValue, currentValue + 1);
    } else if (event.key === 'ArrowDown') {
        currentValue = Math.max(minValue, currentValue - 1);
    }
    
    this.setAttribute('aria-valuenow', currentValue);
    this.setAttribute('aria-valuetext', currentValue);
    this.textContent = currentValue;
});
</script>
```

**시멘틱 마크업을 활용한 진행률 표시 예시**
이 예시는 파일 업로드 진행률을 나타내는 progress 요소를 사용하여 시멘틱 마크업을 구현한 것입니다. aria-valuetext="50 percent completed" 속성은 진행률의 현재 값을 텍스트로 설명하며, 보조 기술 사용자에게 보다 명확한 정보를 제공합니다.    
```sh
<progress id="fileProgress" max="100" value="50" aria-valuenow="50" aria-valuetext="50 percent completed"></progress>
<label for="fileProgress">File Upload Progress</label>
```





## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  