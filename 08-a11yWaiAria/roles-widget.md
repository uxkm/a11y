# WAI-ARIA 역할

## Widget Roles (위젯 역할)
> **Widget Roles**은 다른 역할을 정의하는 데 사용되는 개념적 역할입니다. 이러한 역할들은 웹 페이지에 직접 사용되지 않으며, 구체적인 역할을 정의하고 이들 간의 관계를 설명하고,        
웹 접근성을 높이는 데 중요한 역할을 합니다. 올바르게 이해하고 사용하여 웹 콘텐츠의 접근성을 개선할 수 있습니다.

### **1. button (버튼 역할)**    
사용자가 클릭하여 특정 동작을 수행할 수 있는 UI 요소입니다.   
button 역할은 웹 페이지에서 다양한 형태로 사용될 수 있으며, 각 상황에 맞게 구현 방식이 다를 수 있습니다. 중요한 것은 각 버튼의 역할을 명확히 하여 접근성을 보장하고, aria 속성을 사용하여 보조 기술이 버튼의 상태와 기능을 올바르게 이해할 수 있도록 돕는 것입니다.   
아래에 여러 가지 button 역할의 상세 예시를 제공합니다.   
[W3C ARIA button](https://www.w3.org/TR/wai-aria-1.2/#button){: target="_blank"}   
[MDN ARIA button](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role){: target="_blank"}   

**사용 시 주의사항**   
- aria-pressed 속성을 사용하여 상태를 나타낼 수 있습니다.   
- 시멘틱 마크업이 아닌 요소로 제공한 경우 tabindex="0"을 사용하여 키보드로 접근 가능하게 설정해야 합니다.

**상속된 상태 및 속성**   
- aria-pressed:토글 버튼으로 정의합니다. 이 값은 단추의 상태를 설명합니다.    
- aria-expanded:현재 확장되었는지 또는 축소되었는지를 나타냅니다.    


**기본 버튼**
가장 일반적인 버튼으로, 사용자가 클릭하여 특정 동작을 수행할 수 있습니다.    
```sh
<div role="button">저장</div>
<button type="button">저장</button>
```

**링크로 구현된 버튼**
div 요소를 버튼처럼 동작하게 만드는 예시입니다. 이 경우 role="button"을 추가하여 보조 기술이 이를 버튼으로 인식하게 해야 하며, 키보드 접근성을 위해 tabindex="0"과 클릭 이벤트를 처리하는 스크립트를 추가해야 합니다.    
```sh
<a href="submit-form" role="button" class="btn">Submit</a>
<a href="submit-form" class="btn">Submit</a>
```

**디비전 요소로 구현된 버튼**
스타일링된 링크를 버튼처럼 동작하게 만듭니다. role="button"을 추가하여 보조 기술이 이를 버튼으로 인식하게 합니다.    
```sh
<div role="button" tabindex="0" onclick="alert('Button clicked!')">
  Click Me
</div>

<button onclick="alert('Button clicked!')">Click Me</button>
```

**비활성화된 버튼**
사용자가 상호작용할 수 없는 비활성화된 버튼을 나타냅니다. aria-disabled="true" 속성을 추가하여 접근성을 높입니다.    
```sh
<div role="button" aria-disabled="true" disabled tabindex="0">
  Submit
</div>

<button type="button" disabled>Submit</button>
```

**토글 버튼**
사용자가 누를 때 상태가 변경되는 버튼입니다. 상태를 명확히 전달하기 위해 aria-pressed 속성을 사용합니다.    
```sh
<div role="button" aria-pressed="false" tabindex="0" onclick="toggleButton(this)">
  Toggle
</div>

<script>
  function toggleButton(button) {
    var pressed = button.getAttribute('aria-pressed') === 'true';
    button.setAttribute('aria-pressed', !pressed);
  }
</script>

<button aria-pressed="false" onclick="toggleButton(this)">
  Toggle
</button>
```

**확장/축소 버튼**
요소를 확장하거나 축소하는 버튼입니다. 상태를 전달하기 위해 aria-expanded 속성을 사용합니다.   
```sh
<button type="button" aria-expanded="false" aria-controls="details" onclick="toggleDetails(this)">
  Show Details
</button>
<div id="details" style="display: none;">
  <!-- 숨겨진 내용 -->
  More details here...
</div>

<script>
  function toggleDetails(button) {
    var expanded = button.getAttribute('aria-expanded') === 'true';
    button.setAttribute('aria-expanded', !expanded);
    document.getElementById('details').style.display = expanded ? 'none' : 'block';
  }
</script>
```

**이미지 버튼**
이미지로 구현된 버튼입니다. 시각적인 설명이 부족할 수 있으므로 aria-label 속성을 추가하여 접근성을 보장합니다.   
```sh
<button type="button" aria-label="Search">
  <img src="search-icon.png" alt="">
</button>
```

**커스텀 스타일 버튼**
다양한 CSS 스타일링을 적용한 커스텀 버튼으로, 외관을 다양하게 변경할 수 있습니다.   
```sh
<button type="button" class="custom-button">Custom Button</button>

<style>
  .custom-button {
    background-color: #4CAF50;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  .custom-button:hover {
    background-color: #45a049;
  }
</style>
```

**상태가 있는 아코디언 버튼**
아코디언 UI를 구현하는 버튼입니다. 아코디언 패널을 열거나 닫을 때 버튼 상태를 aria-expanded 속성으로 표시합니다.   
```sh
<button type="button" aria-expanded="false" aria-controls="accordion1" onclick="toggleAccordion(this)">
  Section 1
</button>
<div id="accordion1" style="display: none;">
  <p>Accordion content...</p>
</div>

<script>
  function toggleAccordion(button) {
    var expanded = button.getAttribute('aria-expanded') === 'true';
    button.setAttribute('aria-expanded', !expanded);
    document.getElementById(button.getAttribute('aria-controls')).style.display = expanded ? 'none' : 'block';
  }
</script>
```

### **2. checkbox (체크박스 역할)**    
체크박스는 사용자가 선택하거나 선택 해제할 수 있는 항목입니다.      
[W3C ARIA checkbox](https://www.w3.org/TR/wai-aria-1.2/#checkbox){: target="_blank"}   
[MDN ARIA checkbox](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/checkbox_role){: target="_blank"}   

**사용 시 주의사항**   
- aria-checked 속성을 통해 체크박스의 상태를 명확히 지정해야 합니다 (true, false, mixed).   
- 시멘틱 요소를 사용하지 않는경우 체크박스가 포커스를 받을 수 있도록 tabindex="0"를 추가해야 합니다.

**상속된 상태 및 속성**   
- aria-checked: 체크박스의 현재 상태를 나타냅니다.    



다음 역할은 독립형 사용자 인터페이스 위젯 또는 더 큰 복합 위젯의 일부로 작동합니다.
button
checkbox
gridcell
link
menuitem
menuitemcheckbox
menuitemradio
option
progressbar
radio
scrollbar
searchbox
separator (when focusable)
slider
spinbutton
switch
tab
tabpanel
textbox
treeitem

다음 역할은 복합 사용자 인터페이스 위젯 역할을 합니다. 이러한 역할은 일반적으로 포함된 다른 위젯을 관리하는 컨테이너 역할을 합니다.
combobox
grid
listbox
menu
menubar
radiogroup
tablist
tree
treegrid

## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  