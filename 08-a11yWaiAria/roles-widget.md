# WAI-ARIA 역할

## Widget Roles (위젯 역할)
> **Widget Roles**은 다른 역할을 정의하는 데 사용되는 개념적 역할입니다. 이러한 역할들은 웹 페이지에 직접 사용되지 않으며, 구체적인 역할을 정의하고 이들 간의 관계를 설명합니다.        
웹 접근성을 높이는 데 중요한 역할을 하며, 올바르게 이해하고 사용하여 웹 콘텐츠의 접근성을 개선할 수 있습니다.

Widget Roles은 다음과 같이 구분하여 사용되고 있습니다.
1. 독립형(Standalone) Widget Roles    
   - 독립형 Widget Roles는 단일 UI 요소로서 작동하며, 사용자가 직접 상호작용할 수 있는 개별적인 요소를 의미합니다. 주요 독립형 Widget Roles는 다음과 같습니다.    
   - button, checkbox, radio, gridcell, link, menuitem, menuitemcheckbox, menuitemradio, option, progressbar, scrollbar, searchbox, separator (when focusable), slider, spinbutton, switch, tab, tabpanel, textbox, treeitem     
2. 복합형(Composite) Widget Roles    
   - 복합형 Widget Roles는 여러 개의 하위 요소를 포함하며, 상호작용할 수 있는 복잡한 UI 구성 요소를 의미합니다. 주요 복합형 Widget Roles는 다음과 같습니다.    
   - combobox, grid, listbox, menu, menubar, radiogroup, tablist, tree, treegrid     

**tab - 독립형(Standalone) Widget Roles**

### **1. button (버튼 역할)**    
사용자가 클릭하여 특정 동작을 수행할 수 있는 UI 요소입니다.   
button 역할은 웹 페이지에서 다양한 형태로 사용될 수 있으며, 각 상황에 맞게 구현 방식이 다를 수 있습니다. 중요한 것은 각 버튼의 역할을 명확히 하여 접근성을 보장하고, aria 속성을 사용하여 보조 기술이 버튼의 상태와 기능을 올바르게 이해할 수 있도록 돕는 것입니다.   
아래에 여러 가지 button 역할의 상세 예시를 제공합니다.   
[W3C ARIA button](https://www.w3.org/TR/wai-aria-1.2/#button){: target="_blank"}   
[MDN ARIA button](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role){: target="_blank"}   

**기본 설명**  
- button 역할은 사용자가 클릭하여 특정 작업을 수행할 수 있는 요소를 정의합니다.    
- HTML의 &lt;button&gt; 요소는 기본적으로 button 역할을 가지며, 접근성 및 사용자 경험 측면에서 매우 중요합니다.    
- 버튼은 텍스트, 이미지, 또는 다른 콘텐츠를 포함할 수 있으며, 보조 기술에서 이 버튼의 기능을 인식할 수 있도록 접근성 속성을 설정할 수 있습니다.    

**사용 시 주의사항**   
- 버튼을 클릭하거나 키보드를 통해 활성화할 수 있도록, button 역할을 가지는 요소는 tabindex="0"을 사용하여 키보드 접근성을 보장해야 합니다.   
- button 역할을 명시적으로 설정할 때는, 보조 기술이 이 요소를 버튼으로 인식하도록 해야 합니다.
- 토글 버튼이나 확장/축소 버튼과 같은 동적인 버튼의 경우, aria-pressed 또는 aria-expanded 속성을 사용하여 상태를 명확히 전달해야 합니다.
- 비활성화된 버튼은 disabled 속성을 사용하여 보조 기술에 의해 인식되도록 해야 하며, 시각적으로도 비활성화 상태를 명확히 나타내야 합니다.
- 버튼 내에서 이미지, 아이콘 등을 사용할 경우, 반드시 alt 속성이나 다른 접근성 속성을 통해 버튼의 기능을 설명해야 합니다.

**상속된 상태 및 속성**   
- aria-pressed: 버튼의 토글 상태를 나타냅니다. 가능한 값은 true, false, mixed입니다.    
- aria-expanded: 버튼이 제어하는 콘텐츠의 확장 상태를 나타냅니다. 가능한 값은 true 또는 false입니다.    
- aria-disabled: 버튼이 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 버튼의 레이블과 설명을 참조하는 속성입니다.    


**기본 버튼 예시**
가장 일반적인 버튼으로, 사용자가 클릭하여 특정 동작을 수행할 수 있습니다.    
```sh
// 잘못된 예시 - <div> 요소는 본래 버튼 역할을 하지 않으므로, 키보드 접근성이 부족할 수 있습니다. 이 경우 tabindex와 aria-pressed 같은 추가적인 속성이 필요/
<div role="button">저장</div>

// 올바른 예시
<div role="button" tabindex="0" aria-pressed="false">저장</div>

// (권장)시멘틱 요소 예시
<button type="button">저장</button>
```

**링크로 구현된 버튼 예시**
&lt;a&gt; 태그를 버튼처럼 스타일링하여 사용한 예시입니다. role="button"을 추가하여 보조 기술이 이를 버튼으로 인식하게 했습니다. 이와 함께, 키보드 탐색을 위한 tabindex와 클릭 이벤트 핸들러를 추가해야 합니다.    
```sh
<a href="submit-form" role="button" class="btn">Submit</a>
```

**이미지를 포함한 버튼 예시**
버튼 내에 이미지를 포함하여 시각적인 단서를 제공하는 방법입니다. 이미지에는 alt 텍스트를 제공하여, 보조 기술 사용자에게 버튼의 기능을 설명할 수 있도록 합니다.    
```sh
<button>
  <img src="submit-icon.png" alt="Submit">
</button>
```

**비활성화된 버튼 예시**
disabled 속성을 사용하여 버튼을 비활성화할 수 있습니다. 이 경우, 버튼은 클릭할 수 없으며, 보조 기술은 버튼이 비활성화된 상태임을 인식합니다.    
```sh
<button disabled>Submit</button>
```

**토글 버튼 예시**
aria-pressed 속성을 사용하여 버튼의 토글 상태를 나타냅니다. 이 버튼은 사용자가 클릭할 때마다 상태가 바뀌며, 보조 기술은 이 변화를 인식할 수 있습니다.    
```sh
<button aria-pressed="false" onclick="toggleButton(this)">Toggle</button>

<script>
  function toggleButton(button) {
    const isPressed = button.getAttribute('aria-pressed') === 'true';
    button.setAttribute('aria-pressed', !isPressed);
  }
</script>
```

**확장/축소 버튼 예시**
aria-expanded와 aria-controls 속성을 사용하여 버튼이 제어하는 콘텐츠의 확장/축소 상태를 명확하게 나타냅니다.   
```sh
<button aria-expanded="false" aria-controls="details" onclick="toggleDetails(this)">
  Show Details
</button>
<div id="details" style="display:none;">
  More details here...
</div>

<script>
  function toggleDetails(button) {
    const expanded = button.getAttribute('aria-expanded') === 'true';
    button.setAttribute('aria-expanded', !expanded);
    document.getElementById(button.getAttribute('aria-controls')).style.display = expanded ? 'none' : 'block';
  }
</script>
```

**커스텀 스타일 버튼 예시**
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

**상태가 있는 아코디언 버튼 예시**
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
checkbox 역할은 사용자가 선택하거나 선택 해제할 수 있는 옵션을 나타냅니다. 일반적으로 단일 선택이 가능하며, 하나의 체크박스는 독립적인 상태를 가질 수 있습니다. 웹 접근성을 위해 aria-checked 속성을 사용하여 체크박스의 상태를 나타내며, mixed 상태도 지원됩니다.      
[W3C ARIA checkbox](https://www.w3.org/TR/wai-aria-1.2/#checkbox){: target="_blank"}   
[MDN ARIA checkbox](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/checkbox_role){: target="_blank"}   

**기본 설명**  
- checkbox 역할은 사용자가 선택하거나 선택 해제할 수 있는 항목을 정의합니다.    
- 체크박스의 상태는 aria-checked 속성을 통해 표현되며, 상태는 true(선택됨), false(선택되지 않음), mixed(혼합 상태) 중 하나입니다.    
- checkbox는 단일 체크박스 또는 여러 체크박스로 구성된 그룹으로 사용될 수 있습니다.    

**사용 시 주의사항**   
- checkbox 역할을 사용할 때는 항상 aria-checked 속성을 사용하여 체크박스의 상태를 명확히 나타내야 합니다. 가능한 값은 true (선택됨), false (선택되지 않음), mixed (혼합 상태)입니다.   
- 비활성화된 체크박스는 aria-disabled="true" 속성을 사용하여 표시할 수 있으며, 키보드 탐색에서 제외하려면 tabindex="-1"을 설정할 수 있습니다.
- 비활성화된 항목은 aria-disabled="true" 속성을 사용하여 표시할 수 있으며, 키보드 탐색에서 제외하려면 tabindex="-1"을 설정할 수 있습니다.
- 사용자가 키보드를 사용하여 체크박스를 탐색하고 선택할 수 있도록, tabindex 속성을 적절히 설정해야 합니다.
- role="group"을 사용하여 여러 체크박스를 논리적으로 그룹화할 수 있습니다.

**상속된 상태 및 속성**   
- aria-checked: 체크박스의 선택 상태를 나타냅니다. 가능한 값은 true, false, mixed입니다.    
- aria-disabled: 체크박스가 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 체크박스의 레이블과 설명을 참조하는 속성입니다.    


**기본 checkbox 역할 예시**
checkbox 요소는 aria-checked 속성을 사용하여 선택 상태를 나타내며, tabindex="0"을 설정하여 키보드 탐색이 가능하게 해야 합니다.  

```sh
// 잘못된 예시 - 체크 상태를 나타내는 aria-checked 속성이 필요. 키보드 접근성을 위해 tabindex가 필요
<div role="checkbox">I agree to the terms and conditions</div>

// 올바른 예시
<div role="checkbox" aria-checked="false" tabindex="0" onclick="toggleCheckbox(this)">
  I agree to the terms and conditions
</div>

<script>
  function toggleCheckbox(checkbox) {
    const isChecked = checkbox.getAttribute('aria-checked') === 'true';
    checkbox.setAttribute('aria-checked', !isChecked);
  }
</script>

// (권장)시멘틱 요소 사용
<input type="checkbox" id="terms">
<label for="terms">I agree to the terms and conditions</label>
```

**혼합 상태 checkbox 예시**
체크박스가 mixed 상태를 가질 수 있도록 설정되었습니다. 혼합 상태는 일부 항목이 선택된 경우를 나타내며, 클릭 시 상태가 변경됩니다.   
```sh
<div role="checkbox" aria-checked="mixed" tabindex="0" onclick="toggleCheckbox(this)">
  Select All (Some items selected)
</div>

<script>
  function toggleCheckbox(checkbox) {
    const currentState = checkbox.getAttribute('aria-checked');
    const newState = currentState === 'mixed' ? 'true' : (currentState === 'true' ? 'false' : 'mixed');
    checkbox.setAttribute('aria-checked', newState);
  }
</script>
```

**비활성화된 checkbox 예시**
aria-disabled="true" 속성을 사용하여 체크박스가 비활성화되었음을 나타내고 있으며, 키보드 탐색에서 제외하기 위해 tabindex="-1"로 설정되었습니다.  
```sh
<div role="checkbox" aria-checked="false" aria-disabled="true" tabindex="-1">
  I agree to the terms and conditions
</div>
```

**그룹화된 체크박스 예시**
role="group" 속성을 사용하여 여러 체크박스를 하나의 그룹으로 묶었습니다. 각각의 체크박스는 독립적으로 선택될 수 있습니다.  
```sh
<div role="group" aria-labelledby="group-label">
  <span id="group-label">Choose your preferences:</span>
  <div role="checkbox" aria-checked="false" tabindex="0" onclick="toggleCheckbox(this)">Option 1</div>
  <div role="checkbox" aria-checked="true" tabindex="0" onclick="toggleCheckbox(this)">Option 2</div>
  <div role="checkbox" aria-checked="false" tabindex="0" onclick="toggleCheckbox(this)">Option 3</div>
</div>
```

### **3. radio (라디오 버튼 역할)**    
radio 역할은 사용자가 상호 배타적인 옵션 중 하나를 선택할 수 있는 라디오 버튼을 나타냅니다. 여러 개의 radio 요소가 radiogroup 안에 포함되며, 사용자는 한 번에 하나의 radio만 선택할 수 있습니다.        
[W3C ARIA radio](https://www.w3.org/TR/wai-aria-1.2/#radio){: target="_blank"}   
[MDN ARIA radio](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/radio_role){: target="_blank"}   

**기본 설명**  
- radio 역할은 사용자가 여러 옵션 중 하나를 선택할 수 있는 라디오 버튼을 정의합니다.    
- radio 요소는 반드시 radiogroup 역할을 가진 컨테이너 안에 포함되어야 합니다.    
- 선택된 상태는 aria-checked 속성을 통해 나타내며, 키보드 탐색과 선택이 가능하도록 tabindex 속성을 적절히 설정해야 합니다.    

**사용 시 주의사항**   
- radio 역할은 반드시 radiogroup 역할을 가진 요소 안에 있어야 합니다.   
- 각 radio 요소는 선택 상태를 나타내기 위해 aria-checked 속성을 사용해야 합니다. 값은 true (선택됨) 또는 false (선택되지 않음) 중 하나입니다.
- 비활성화된 항목은 aria-disabled="true" 속성을 사용하여 표시할 수 있으며, 키보드 탐색에서 제외하려면 tabindex="-1"을 설정할 수 있습니다.
- radiogroup 내에서는 하나의 radio만 aria-checked="true" 상태여야 합니다.
- 사용자가 키보드를 사용하여 라디오 버튼 그룹을 탐색하고 선택할 수 있어야 하므로, tabindex 속성을 적절히 설정해야 합니다.

**상속된 상태 및 속성**   
- aria-checked: 라디오 버튼의 선택 상태를 나타냅니다. 가능한 값은 true 또는 false입니다.    
- aria-disabled: 라디오 버튼이 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 라디오 버튼의 레이블과 설명을 참조하는 속성입니다.    


**기본 radio 역할 예시**
각 radio 요소는 radiogroup 역할을 가진 컨테이너(부모요소) 안에 포함되어 있어야 하며, aria-checked 속성을 사용해 현재 선택 상태를 나타내고, 각 항목은 tabindex="0"으로 설정되어 키보드 탐색이 가능하게 해야 합니다.   

```sh
// 잘못된 예시 - 단독으로 사용할 수 없음. 선택 상태를 나타내는 aria-checked 속성 누락.
<div role="radio">Option 1</div>

// 올바른 예시
<div role="radiogroup" aria-labelledby="group-label">
  <span id="group-label">Choose an option:</span>
  <div role="radio" aria-checked="true" tabindex="0">Option 1</div>
  <div role="radio" aria-checked="false" tabindex="0">Option 2</div>
  <div role="radio" aria-checked="false" tabindex="0">Option 3</div>
</div>

// (권장)시멘틱 요소 사용 - 시멘틱하게 구성된 라디오 버튼 그룹으로, <input type="radio">와 <label>을 사용해 라디오 버튼을 제공.
<fieldset>
  <legend>Choose an option:</legend>
  <input type="radio" id="option1" name="options" checked>
  <label for="option1">Option 1</label><br>
  <input type="radio" id="option2" name="options">
  <label for="option2">Option 2</label><br>
  <input type="radio" id="option3" name="options">
  <label for="option3">Option 3</label>
</fieldset>
```

**동적 상태 변경을 고려한 radio 예시**
사용자가 클릭할 때마다 aria-checked 속성이 업데이트되어 라디오 버튼의 선택 상태가 변경됩니다. 선택된 항목만이 aria-checked="true" 상태가 되며, 다른 항목의 선택이 해제됩니다.   
```sh
<div role="radiogroup" aria-labelledby="group-label">
  <span id="group-label">Choose an option:</span>
  <div role="radio" aria-checked="true" tabindex="0" onclick="selectRadio(this)">Option 1</div>
  <div role="radio" aria-checked="false" tabindex="0" onclick="selectRadio(this)">Option 2</div>
  <div role="radio" aria-checked="false" tabindex="0" onclick="selectRadio(this)">Option 3</div>
</div>

<script>
  function selectRadio(selectedRadio) {
    const radios = document.querySelectorAll('[role="radiogroup"] [role="radio"]');
    radios.forEach(radio => {
      radio.setAttribute('aria-checked', 'false');
      radio.setAttribute('tabindex', '-1');
    });
    selectedRadio.setAttribute('aria-checked', 'true');
    selectedRadio.setAttribute('tabindex', '0');
    selectedRadio.focus();
  }
</script>
```

**비활성화된 radio 예시**
aria-disabled="true" 속성을 사용하여 두 번째 라디오 버튼이 비활성화되었음을 나타내고 있으며, 이 항목은 키보드 탐색에서 제외되도록 tabindex="-1"로 설정되었습니다.  
```sh
<div role="radiogroup" aria-labelledby="group-label">
  <span id="group-label">Choose an option:</span>
  <div role="radio" aria-checked="true" tabindex="0">Option 1</div>
  <div role="radio" aria-checked="false" aria-disabled="true" tabindex="-1">Option 2 (Disabled)</div>
  <div role="radio" aria-checked="false" tabindex="0">Option 3</div>
</div>
```


### **4. gridcell (그리드 셀 역할)**    
gridcell 역할은 그리드 또는 테이블에서 개별 셀을 나타내는 데 사용됩니다.    
이 역할은 표 형식의 데이터를 구조화하는 데 유용하며, 사용자가 각 셀의 데이터를 쉽게 탐색하고 접근할 수 있도록 돕습니다.         
특정 관련 ARIA 역할 및 속성에 대한 지원은 보조 기술에 대한 지원이 부족합니다. 가능하면 HTML 테이블 마크업을 대신 사용하는것이 좋습니다.    
[W3C ARIA gridcell](https://www.w3.org/TR/wai-aria-1.2/#gridcell){: target="_blank"}   
[MDN ARIA gridcell](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/gridcell_role){: target="_blank"}   

**기본 설명**  
- gridcell은 그리드의 한 칸 또는 테이블 셀에 해당하는 역할입니다.    
- gridcell은 보통 grid, row, rowgroup과 함께 사용됩니다.    
- 사용자는 키보드를 통해 gridcell 사이를 탐색할 수 있으며, 이때 보조 기술이 셀의 상태(예: 선택됨, 비활성화됨 등)를 올바르게 읽을 수 있습니다.    

**사용 시 주의사항**   
- gridcell은 항상 row 역할을 가진 요소 내에 있어야 하며, row는 grid 역할을 가진 요소 내에 있어야 합니다.   
- aria-selected 속성을 사용하여 셀의 선택 여부를 나타낼 수 있습니다. 사용자가 셀을 클릭하거나 선택했을 때 보조 기술이 이 상태를 정확히 인식할 수 있도록 합니다.
- 키보드 탐색을 고려하여 tabindex 속성을 적절하게 설정해야 합니다. tabindex="0"을 사용하여 포커스를 받을 수 있도록 하거나, tabindex="-1"을 사용하여 포커스를 제거할 수 있습니다.
- aria-rowindex, aria-colindex 속성을 사용하여 그리드 내의 셀의 위치를 명시할 수 있습니다. 이는 큰 그리드에서 사용자가 현재 어느 셀에 있는지를 이해하는 데 도움이 됩니다.

**상속된 상태 및 속성**   
- aria-selected: 셀이 현재 선택되었는지 여부를 나타냅니다.    
- aria-readonly: 셀이 읽기 전용인지 여부를 나타냅니다.    
- aria-required: 셀이 필수 입력 항목인지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 셀의 레이블 및 설명을 참조하는 속성입니다.    


```sh
// 잘못된 예시 - gridcell 요소는 반드시 row 역할을 가진 컨테이너 내부에 있어야 하며, 단독으로 사용할 수 없습니다.
<div role="gridcell">Cell Content</div>

// 올바른 예시
<div role="row">
  <div role="gridcell" aria-selected="false" tabindex="0">Cell Content</div>
</div>
// gridcell은 row 역할을 가진 요소 안에 배치되어 있으며, aria-selected 속성을 사용하여 선택 여부를 나타내고 있습니다. 
// 또한, tabindex="0"을 설정하여 키보드로 포커스를 받을 수 있게 했습니다.

// (권장)시멘틱 요소 사용 - HTML 표 요소 <td>를 사용하여 시멘틱하게 그리드 셀을 표현할 수 있습니다. 이 경우, <table>, <tr>와 같은 시멘틱 요소들이 함께 사용됩니다. 
<tr>
  <td>Cell Content</td>
</tr>

// ARIA 속성을 사용한 복합 그리드 예시
<div role="grid" aria-rowcount="2" aria-colcount="3">
  <div role="row" aria-rowindex="1">
    <div role="gridcell" aria-colindex="1" aria-selected="true" tabindex="0">Row 1, Cell 1</div>
    <div role="gridcell" aria-colindex="2" aria-selected="false" tabindex="-1">Row 1, Cell 2</div>
    <div role="gridcell" aria-colindex="3" aria-selected="false" tabindex="-1">Row 1, Cell 3</div>
  </div>
  <div role="row" aria-rowindex="2">
    <div role="gridcell" aria-colindex="1" aria-selected="false" tabindex="-1">Row 2, Cell 1</div>
    <div role="gridcell" aria-colindex="2" aria-selected="false" tabindex="-1">Row 2, Cell 2</div>
    <div role="gridcell" aria-colindex="3" aria-selected="true" tabindex="0">Row 2, Cell 3</div>
  </div>
</div>
// 이 예시에서는 aria-rowcount, aria-colcount, aria-rowindex, aria-colindex와 같은 속성을 사용하여 그리드의 행과 열을 정의하고, 각 셀이 어떤 위치에 있는지 명시합니다. aria-selected 속성으로 각 셀의 선택 상태를 나타내고 있습니다.
```

### **5. link (링크 역할)**    
link 역할은 다른 페이지나 리소스로 연결되는 클릭 가능한 요소를 나타냅니다. 일반적으로 &lt;a&gt; 태그로 구현되지만, 다른 HTML 요소에 role="link" 속성을 추가하여 링크로 동작하게 할 수도 있습니다. 이 역할은 웹 내비게이션의 핵심 요소로, 사용자에게 페이지 간의 이동 경로를 제공합니다.        
[W3C ARIA link](https://www.w3.org/TR/wai-aria-1.2/#link){: target="_blank"}   
[MDN ARIA link](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/link_role){: target="_blank"}   

**기본 설명** 
- 기본적인 역할: link 역할은 클릭하거나 Enter 키를 눌렀을 때 사용자를 다른 리소스로 이동시킵니다.    
- 보조 기술과의 통합: 보조 기술은 link 역할을 인식하여 사용자에게 클릭 가능한 링크가 있다는 것을 알리고, 그 링크가 어디로 이동하는지 알려줍니다.    

**사용 시 주의사항**   
- &lt;a&gt; 태그를 사용할 때는 href 속성을 반드시 지정해야 합니다. href 속성이 없는 &lt;a&gt; 태그는 보조 기술에서 링크로 인식되지 않을 수 있습니다.   
- role="link"를 사용하는 경우, tabindex="0"을 추가하여 키보드 탐색이 가능하도록 해야 합니다.
- aria-disabled 속성을 사용하여 링크를 비활성화할 수 있습니다. 그러나 링크를 완전히 비활성화하려면 href="#"와 함께 스크립트로 클릭 이벤트를 차단하는 것이 좋습니다.
- 이미지 링크의 경우, alt 속성을 사용하여 이미지의 의미를 명확하게 설명해야 합니다.

**상속된 상태 및 속성**   
- aria-disabled: 링크가 비활성화되었는지 여부를 나타냅니다.    
- aria-label: 링크의 대체 텍스트를 제공합니다. 링크의 목적을 명확히 하기 위해 사용됩니다.    
- aria-labelledby: 링크의 레이블을 지정하는 다른 요소의 ID를 참조합니다.    


```sh
// 잘못된 예시 - <div> 태그는 본래 링크 역할이 아니며, 적절한 키보드 탐색 기능이 부족할 수 있습니다. 보조 기술이 이를 링크로 인식하지 않을 수 있습니다.
<div role="link">Go to Example</div>

// 올바른 예시
<a href="https://example.com" role="link">Go to Example</a>
// <a> 태그는 본래 링크 역할을 가지므로, role="link"를 명시적으로 지정할 필요는 없습니다. 이 예시에서는 올바르게 링크를 구현했습니다.

// (권장)시멘틱 요소 사용 - 시멘틱하게 적절히 구현된 <a> 요소입니다. href 속성으로 링크를 지정하면, 보조 기술은 이를 자동으로 인식합니다.
<a href="https://example.com">Go to Example</a>


// 이미지를 포함한 링크
<a href="https://example.com">
  <img src="example.jpg" alt="Example Image">
</a>
// 이 예시는 이미지 전체가 클릭 가능한 링크로 설정된 경우입니다. alt 속성을 통해 이미지의 의미를 명확히 설명해야 합니다.

// 키보드 탐색이 가능한 링크
<div role="link" tabindex="0" onclick="window.location.href='https://example.com'">Go to Example</div>
// <div> 요소에 role="link"와 tabindex="0"을 추가하여 키보드 탐색이 가능하게 했습니다. onclick 이벤트를 사용하여 링크 동작을 구현했습니다. 이렇게 하면 <div> 요소가 링크처럼 작동합니다. 

// 비활성화된 링크
<a href="#" role="link" aria-disabled="true">Disabled Link</a>
// aria-disabled="true" 속성을 사용하여 링크가 비활성화되었음을 나타냅니다. 이 경우 시각적으로도 비활성화된 상태를 표현하는 것이 중요합니다.
```


### **6. menuitem (메뉴 항목 역할)**    
menuitem 역할은 메뉴에서 선택할 수 있는 개별 항목을 나타냅니다. 이 역할은 menu 역할을 가진 컨테이너(부모요소) 안에서 사용되며, 사용자가 선택하거나 클릭할 수 있는 항목을 정의합니다. menuitem은 일반적인 단일 선택 메뉴 항목을 나타내며, menuitemcheckbox와 menuitemradio와 구별됩니다.        
[W3C ARIA menuitem](https://www.w3.org/TR/wai-aria-1.2/#menuitem){: target="_blank"}   
[MDN ARIA menuitem](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitem_role){: target="_blank"}   

**기본 설명** 
- menuitem 역할은 일반적으로 menu 역할을 가진 요소 안에 포함됩니다.    
- 이 역할은 사용자가 특정 동작을 트리거할 수 있는 선택 가능한 항목을 나타냅니다.    
- 이 역할은 사용자가 특정 동작을 트리거할 수 있는 선택 가능한 항목을 나타냅니다.    
- menuitem은 보통 파일 메뉴, 드롭다운 메뉴, 컨텍스트 메뉴와 같은 메뉴 구조에서 사용됩니다.    

**사용 시 주의사항**   
- menuitem은 항상 menu 또는 menubar 역할을 가진 요소 안에 있어야 합니다.   
- 각 menuitem 요소는 키보드로 탐색할 수 있도록 tabindex="0"을 설정해야 합니다. 비활성화된 항목의 경우 tabindex="-1"을 설정할 수 있습니다.
- 서브메뉴를 가진 menuitem의 경우 aria-haspopup="true"와 aria-expanded 속성을 사용해 서브메뉴의 상태를 관리해야 합니다.
- 사용자가 메뉴 항목을 선택할 수 없는 경우, aria-disabled="true" 속성을 사용하여 비활성화 상태를 명확히 해야 합니다.

**상속된 상태 및 속성**   
- aria-disabled: 메뉴 항목이 비활성화되었는지 여부를 나타냅니다.    
- aria-haspopup: 메뉴 항목이 서브메뉴 또는 다른 팝업을 가지고 있는지 여부를 나타냅니다.    
- aria-expanded: 서브메뉴가 확장되었는지 여부를 나타냅니다.    
- aria-label: 메뉴 항목의 대체 텍스트를 제공합니다.    


**기본 menuitem 역할 예시**
menuitem 역할은 menu 역할을 가진 &lt;element&gt; 안에 포함되어 있어야 하며, 각 항목은 키보드로 포커스를 받을 수 있도록 tabindex="0"이 설정되어 있어야 합니다.    
시멘틱하게 구성된 메뉴를 사용하는것을 권장합니다.

```sh
// 잘못된 예시 - menuitem 역할은 단독으로 사용될 수 없으며, 반드시 menu 역할을 가진 컨테이너 안에 있어야 하며. 또한 키보드 접근성에 대한 고려가 부족
<div role="menuitem">Save</div>

// 올바른 예시
<ul role="menu">
  <li role="menuitem" tabindex="0">Save</li>
  <li role="menuitem" tabindex="0">Open</li>
  <li role="menuitem" tabindex="0">Exit</li>
</ul>

// (권장)시멘틱 요소 사용 - 시멘틱하게 구성된 메뉴로, <a> 태그를 사용해 각 메뉴 항목을 정의했습니다. 일반적인 내비게이션 메뉴에 사용
<nav>
  <ul>
    <li><a href="#">Save</a></li>
    <li><a href="#">Open</a></li>
    <li><a href="#">Exit</a></li>
  </ul>
</nav>
```

**키보드 내비게이션을 고려한 menuitem 예시**
각 menuitem 요소에 onclick 이벤트가 추가되어 있어 사용자가 항목을 클릭하거나 Enter 키를 눌렀을 때 동작이 실행됩니다. tabindex="0"을 설정해 키보드 내비게이션이 가능합니다.   
```sh
<ul role="menu">
  <li role="menuitem" tabindex="0" onclick="alert('New File')">New File</li>
  <li role="menuitem" tabindex="0" onclick="alert('Open File')">Open File</li>
  <li role="menuitem" tabindex="0" onclick="alert('Save File')">Save File</li>
</ul>
```

**비활성화된 menuitem 예시**
aria-disabled="true" 속성을 사용하여 Save 메뉴 항목이 비활성화되었음을 나타냅니다. 이 항목은 포커스를 받을 수 없도록 tabindex="-1"로 설정했습니다.   
```sh
<ul role="menu">
  <li role="menuitem" tabindex="-1" aria-disabled="true">Save</li>
  <li role="menuitem" tabindex="0">Open</li>
  <li role="menuitem" tabindex="0">Exit</li>
</ul>
```

**서브메뉴를 가진 menuitem 예시**
File 메뉴 항목은 서브메뉴를 가지고 있으며, aria-haspopup="true"와 aria-expanded 속성을 사용해 서브메뉴의 표시 여부를 관리합니다. 클릭 시 서브메뉴가 표시되거나 숨겨집니다.   
```sh
<ul role="menu">
  <li role="menuitem" aria-haspopup="true" aria-expanded="false" onclick="toggleSubMenu(this)">
    File
    <ul role="menu" class="submenu" style="display: none;">
      <li role="menuitem" tabindex="0">New</li>
      <li role="menuitem" tabindex="0">Open</li>
    </ul>
  </li>
  <li role="menuitem" tabindex="0">Edit</li>
  <li role="menuitem" tabindex="0">View</li>
</ul>

<script>
  function toggleSubMenu(menuitem) {
    const submenu = menuitem.querySelector('.submenu');
    const expanded = menuitem.getAttribute('aria-expanded') === 'true';
    menuitem.setAttribute('aria-expanded', !expanded);
    submenu.style.display = expanded ? 'none' : 'block';
  }
</script>
```


### **7. menuitemcheckbox (메뉴 항목 체크박스 역할)**    
menuitemcheckbox 역할은 메뉴에서 선택 가능하거나 선택 해제할 수 있는 체크박스 항목을 나타냅니다. 이 역할은 일반적인 체크박스와 유사하지만, 메뉴 구조 내에서 사용됩니다. 사용자는 하나 이상의 menuitemcheckbox를 선택하거나 해제할 수 있습니다.        
[W3C ARIA menuitemcheckbox](https://www.w3.org/TR/wai-aria-1.2/#menuitemcheckbox){: target="_blank"}   
[MDN ARIA menuitemcheckbox](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitemcheckbox_role){: target="_blank"}   

**기본 설명** 
- menuitemcheckbox 역할은 주로 menu 역할을 가진 컨테이너(부모요소) 안에 포함되어 사용됩니다.    
- 사용자는 이 요소를 클릭하거나 선택하여 항목을 켜거나 끌 수 있으며, 이를 통해 여러 옵션을 선택할 수 있습니다.    
- menuitemcheckbox는 선택 상태를 나타내기 위해 aria-checked 속성을 사용합니다.    

**사용 시 주의사항**   
- menuitemcheckbox는 반드시 menu 또는 menubar 역할을 가진 요소 안에 있어야 합니다.   
- 각 menuitemcheckbox 요소는 선택 상태를 나타내기 위해 aria-checked 속성을 사용해야 합니다. 값은 true (선택됨), false (선택되지 않음), mixed (혼합 상태) 중 하나입니다.
- 비활성화된 항목은 aria-disabled="true" 속성을 사용하여 표시할 수 있으며, 키보드 탐색에서 제외하려면 tabindex="-1"을 설정할 수 있습니다.
- 사용자는 키보드를 사용하여 메뉴 항목을 탐색하고 선택할 수 있어야 하므로, tabindex 속성을 적절히 설정해야 합니다.

**상속된 상태 및 속성**   
- aria-checked: 메뉴 항목의 체크 상태를 나타냅니다. 가능한 값은 true, false, mixed입니다.    
- aria-disabled: 메뉴 항목이 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 메뉴 항목의 레이블과 설명을 참조하는 속성입니다.    


**기본 menuitemcheckbox 역할 예시**
menuitemcheckbox는 menu 역할을 가진 &lt;element&gt; 요소 안에 포함되어 있어야 하며, aria-checked 속성을 사용해 현재 선택 상태를 명확히 나타내고 있어야 합니다. 또한 각 항목은 tabindex="0"을 설정해 키보드 탐색이 가능하게 해야 합니다.   

```sh
// 잘못된 예시 - menuitemcheckbox 역할은 반드시 menu 역할을 가진 컨테이너 안에 있어야 합니다. 또한, 체크 상태를 나타내는 aria-checked 속성이 누락되었습니다.
<div role="menuitemcheckbox">Enable Notifications</div>

// 올바른 예시
<ul role="menu">
  <li role="menuitemcheckbox" aria-checked="false" tabindex="0">Enable Notifications</li>
  <li role="menuitemcheckbox" aria-checked="true" tabindex="0">Receive Newsletters</li>
</ul>

// (권장)시멘틱 요소 사용 - 시멘틱하게 구현된 체크박스 메뉴 항목으로, <input type="checkbox">와 <label>을 사용해 체크박스 기능을 제공
<ul>
  <li>
    <input type="checkbox" id="notifications" checked>
    <label for="notifications">Enable Notifications</label>
  </li>
  <li>
    <input type="checkbox" id="newsletters">
    <label for="newsletters">Receive Newsletters</label>
  </li>
</ul>
```

**동적 상태 변경을 고려한 menuitemcheckbox 예시**
사용자가 클릭할 때마다 aria-checked 속성이 변경되어 체크박스의 상태를 업데이트합니다. 이를 통해 사용자는 메뉴 항목을 선택하거나 해제할 수 있습니다.   
```sh
<ul role="menu">
  <li role="menuitemcheckbox" aria-checked="false" tabindex="0" onclick="toggleCheckbox(this)">
    Enable Notifications
  </li>
  <li role="menuitemcheckbox" aria-checked="true" tabindex="0" onclick="toggleCheckbox(this)">
    Receive Newsletters
  </li>
</ul>

<script>
  function toggleCheckbox(menuItem) {
    const isChecked = menuItem.getAttribute('aria-checked') === 'true';
    menuItem.setAttribute('aria-checked', !isChecked);
  }
</script>
```

**비활성화된 menuitemcheckbox 예시**
aria-disabled="true" 속성을 사용해 첫 번째 항목이 비활성화되었음을 나타내주고, 키보드 탐색에서 제외하기 위해 tabindex="-1"을 설정합니다.   
```sh
<ul role="menu">
  <li role="menuitemcheckbox" aria-checked="false" aria-disabled="true" tabindex="-1">
    Enable Notifications
  </li>
  <li role="menuitemcheckbox" aria-checked="true" tabindex="0">Receive Newsletters</li>
</ul>
```

### **8. menuitemradio (메뉴 항목 라디오 버튼 역할)**    
menuitemradio 역할은 메뉴 내에서 사용자가 선택할 수 있는 라디오 버튼 항목을 나타냅니다. menuitemradio는 상호 배타적인 선택 항목을 제공하며, 동일한 그룹 내에서 하나의 항목만 선택할 수 있습니다. 일반적인 라디오 버튼과 유사하지만, 메뉴 구조 내에서 사용됩니다.        
[W3C ARIA menuitemradio](https://www.w3.org/TR/wai-aria-1.2/#menuitemradio){: target="_blank"}   
[MDN ARIA menuitemradio](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/menuitemradio_role){: target="_blank"}   

**기본 설명** 
- menuitemradio 역할은 일반적으로 menu 역할을 가진 컨테이너(부모요소) 안에서 사용됩니다.    
- 이 역할은 사용자가 하나의 항목만 선택할 수 있는 상호 배타적인 옵션을 제공하며, 선택된 상태를 aria-checked 속성을 통해 나타냅니다.    
- 라디오 버튼 그룹은 role="group" 또는 role="menu"로 그룹화할 수 있습니다.    

**사용 시 주의사항**   
- menuitemradio는 반드시 menu 또는 group 역할을 가진 요소 안에 있어야 합니다.   
- aria-disabled: 메뉴 항목이 비활성화되었는지 여부를 나타냅니다.
- aria-labelledby, aria-describedby: 메뉴 항목의 레이블과 설명을 참조하는 속성입니다.

**상속된 상태 및 속성**   
- aria-checked: 라디오 버튼의 선택 상태를 나타냅니다. 가능한 값은 true 또는 false입니다.    
- aria-disabled: 메뉴 항목이 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 메뉴 항목의 레이블과 설명을 참조하는 속성입니다.    


**기본 menuitemradio 역할 예시**
각 menuitemradio 요소는 menu 역할을 가진 &lt;element&gt; 요소 안에 포함되어 있어야 하며, aria-checked 속성을 사용해 현재 선택 상태를 명확히 나타내야 합니다. 또한 각 항목은 tabindex="0"으로 설정되어 있어 키보드 탐색이 가능하게 해야 합니다.   

```sh
// 잘못된 예시 - menuitemradio 역할은 반드시 menu 또는 group 역할을 가진 컨테이너 안에 있어야 하며, aria-checked 속성이 없어 선택 상태가 명확하지 않습니다.
<div role="menuitemradio">Option 1</div>

// 올바른 예시
<ul role="menu">
  <li role="menuitemradio" aria-checked="true" tabindex="0">Option 1</li>
  <li role="menuitemradio" aria-checked="false" tabindex="0">Option 2</li>
  <li role="menuitemradio" aria-checked="false" tabindex="0">Option 3</li>
</ul>

// (권장)시멘틱 요소 사용 - 시멘틱하게 구성된 라디오 버튼 그룹으로, <input type="radio">와 <label> 요소를 사용해 라디오 버튼을 제공합니다.
<fieldset>
  <legend>Choose an option:</legend>
  <input type="radio" id="option1" name="options" checked>
  <label for="option1">Option 1</label><br>
  <input type="radio" id="option2" name="options">
  <label for="option2">Option 2</label><br>
  <input type="radio" id="option3" name="options">
  <label for="option3">Option 3</label>
</fieldset>
```

**동적 상태 변경을 고려한 menuitemradio 예시**
사용자가 클릭할 때마다 aria-checked 속성이 업데이트되어 라디오 버튼의 상태를 변경합니다. 이 예시는 다른 menuitemradio 요소들의 선택을 해제하고, 클릭된 항목을 선택 상태로 만듭니다.   
```sh
<ul role="menu">
  <li role="menuitemradio" aria-checked="true" tabindex="0" onclick="selectRadio(this)">
    Option 1
  </li>
  <li role="menuitemradio" aria-checked="false" tabindex="0" onclick="selectRadio(this)">
    Option 2
  </li>
  <li role="menuitemradio" aria-checked="false" tabindex="0" onclick="selectRadio(this)">
    Option 3
  </li>
</ul>

<script>
  function selectRadio(selectedItem) {
    const menu = selectedItem.parentElement;
    const items = menu.querySelectorAll('[role="menuitemradio"]');
    items.forEach(item => {
      item.setAttribute('aria-checked', 'false');
      item.setAttribute('tabindex', '-1');
    });
    selectedItem.setAttribute('aria-checked', 'true');
    selectedItem.setAttribute('tabindex', '0');
    selectedItem.focus();
  }
</script>
```

**비활성화된 menuitemradio 예시**
aria-disabled="true" 속성을 사용하여 두 번째 항목이 비활성화되었음을 나타냅니다. 이 항목은 키보드 탐색에서 제외되도록 tabindex="-1"로 설정되었습니다.   
```sh
<ul role="menu">
  <li role="menuitemradio" aria-checked="true" tabindex="0">Option 1</li>
  <li role="menuitemradio" aria-checked="false" aria-disabled="true" tabindex="-1">Option 2</li>
  <li role="menuitemradio" aria-checked="false" tabindex="0">Option 3</li>
</ul>
```


### **9. option (옵션 역할)**    
option 역할은 사용자가 선택할 수 있는 개별 항목을 나타내며, 일반적으로 listbox, select, combobox 등의 컨테이너(부모요소) 안에서 사용됩니다. 이 역할은 사용자가 여러 옵션 중 하나를 선택할 수 있는 상황에서 사용됩니다.        
[W3C ARIA option](https://www.w3.org/TR/wai-aria-1.2/#option){: target="_blank"}   
[MDN ARIA option](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/option_role){: target="_blank"}   

**기본 설명** 
- option 역할은 사용자가 선택할 수 있는 항목을 정의하며, 주로 listbox, select, combobox 역할과 함께 사용됩니다.    
- 선택된 상태는 aria-selected 속성을 통해 나타내며, 키보드 탐색을 지원하기 위해 적절한 tabindex 설정이 필요합니다.    

**사용 시 주의사항**   
- option 역할은 반드시 listbox, select, 또는 combobox 역할을 가진 컨테이너 안에 있어야 합니다.   
- 각 option 요소는 선택 상태를 나타내기 위해 aria-selected 속성을 사용해야 합니다. 값은 true (선택됨) 또는 false (선택되지 않음) 중 하나입니다.
- 비활성화된 항목은 aria-disabled="true" 속성을 사용하여 표시할 수 있으며, 키보드 탐색에서 제외하려면 tabindex="-1"을 설정할 수 있습니다.
- aria-multiselectable 속성을 listbox에 추가하면 여러 옵션을 동시에 선택할 수 있습니다.
- 사용자가 키보드를 사용하여 옵션을 탐색하고 선택할 수 있어야 하므로, tabindex 속성을 적절히 설정해야 합니다.

**상속된 상태 및 속성**   
- aria-selected: 옵션의 선택 상태를 나타냅니다. 가능한 값은 true 또는 false입니다.    
- aria-disabled: 옵션이 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 옵션의 레이블과 설명을 참조하는 속성입니다.    



**기본 option 역할 예시**
각 option 요소는 listbox 역할을 가진 &lt;element&gt; 요소 안에 포함되어 있어야 하며, aria-selected 속성을 사용해 현재 선택 상태를 명확히 나타내고 있어야 합니다. 각 항목은 tabindex="0"으로 설정되어 있어 키보드 탐색이 가능하게 해야 합니다.   

```sh
// 잘못된 예시 - option 역할은 반드시 listbox 또는 select, combobox 역할을 가진 컨테이너 안에 있어야 하며, 단독으로 사용될 수 없습니다. 선택 상태를 나타내는 aria-selected 속성도 누락되었습니다.
<div role="option">Item 1</div>

// 올바른 예시
<ul role="listbox">
  <li role="option" aria-selected="true" tabindex="0">Item 1</li>
  <li role="option" aria-selected="false" tabindex="0">Item 2</li>
  <li role="option" aria-selected="false" tabindex="0">Item 3</li>
</ul>

// (권장)시멘틱 요소 사용 - 시멘틱하게 구성된 선택 목록으로, <select>와 <option> 요소를 사용해 옵션을 제공합니다. 브라우저와 보조 기술에서 기본적으로 지원하는 시멘틱 마크업입니다.
<select>
  <option selected>Item 1</option>
  <option>Item 2</option>
  <option>Item 3</option>
</select>
```

**동적 상태 변경을 고려한 option 예시**
사용자가 클릭할 때마다 aria-selected 속성이 업데이트되어 옵션의 선택 상태가 변경됩니다. 선택된 항목만이 aria-selected="true" 상태가 되며, 다른 항목의 선택이 해제됩니다.   
```sh
<ul role="listbox" id="myListbox">
  <li role="option" aria-selected="true" tabindex="0" onclick="selectOption(this)">Item 1</li>
  <li role="option" aria-selected="false" tabindex="0" onclick="selectOption(this)">Item 2</li>
  <li role="option" aria-selected="false" tabindex="0" onclick="selectOption(this)">Item 3</li>
</ul>

<script>
  function selectOption(selectedOption) {
    const options = document.querySelectorAll('#myListbox [role="option"]');
    options.forEach(option => {
      option.setAttribute('aria-selected', 'false');
      option.setAttribute('tabindex', '-1');
    });
    selectedOption.setAttribute('aria-selected', 'true');
    selectedOption.setAttribute('tabindex', '0');
    selectedOption.focus();
  }
</script>
```

**비활성화된 option 예시**
aria-disabled="true" 속성을 사용하여 두 번째 옵션이 비활성화되었음을 나타내고 있으며, 이 항목은 키보드 탐색에서 제외되도록 tabindex="-1"로 설정되었습니다.  
```sh
<ul role="listbox">
  <li role="option" aria-selected="true" tabindex="0">Item 1</li>
  <li role="option" aria-selected="false" aria-disabled="true" tabindex="-1">Item 2 (Disabled)</li>
  <li role="option" aria-selected="false" tabindex="0">Item 3</li>
</ul>
```

**다중 선택이 가능한 option 예시**
aria-multiselectable="true" 속성을 사용해 여러 항목을 선택할 수 있도록 설정한 예시입니다. 사용자가 클릭할 때마다 선택 상태가 토글됩니다.  
```sh
<ul role="listbox" aria-multiselectable="true">
  <li role="option" aria-selected="true" tabindex="0" onclick="toggleOption(this)">Item 1</li>
  <li role="option" aria-selected="true" tabindex="0" onclick="toggleOption(this)">Item 2</li>
  <li role="option" aria-selected="false" tabindex="0" onclick="toggleOption(this)">Item 3</li>
</ul>

<script>
  function toggleOption(option) {
    const isSelected = option.getAttribute('aria-selected') === 'true';
    option.setAttribute('aria-selected', !isSelected);
  }
</script>
```


### **10. progressbar (진행 상태 막대 역할)**    
progressbar 역할은 작업의 진행 상태를 시각적으로 나타내는 막대를 정의합니다. 이 역할은 사용자가 특정 작업이 얼마나 완료되었는지 확인할 수 있도록 도와줍니다. progressbar는 진행률을 나타내기 위해 aria-valuenow, aria-valuemin, aria-valuemax와 같은 ARIA 속성을 사용하여 현재 진행 상태를 전달합니다.        
[W3C ARIA progressbar](https://www.w3.org/TR/wai-aria-1.2/#progressbar){: target="_blank"}   
[MDN ARIA progressbar](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/progressbar_role){: target="_blank"}   

**기본 설명** 
- progressbar 역할은 파일 다운로드, 업로드, 데이터 처리 등의 작업 진행 상황을 나타내기 위해 사용됩니다.    
- 보조 기술은 progressbar의 현재 값(aria-valuenow), 최소 값(aria-valuemin), 최대 값(aria-valuemax)을 사용해 진행 상태를 인식하고 사용자에게 전달합니다.    
- 진행률을 나타내는 숫자(퍼센트)와 시각적인 막대가 함께 사용될 수 있습니다.    

**사용 시 주의사항**   
- progressbar 역할을 사용할 때는 반드시 aria-valuenow, aria-valuemin, aria-valuemax 속성을 설정해야 하며, 이를 통해 보조 기술이 진행 상태를 정확히 전달할 수 있도록 합니다.   
- aria-valuenow는 현재 진행 상태를 나타내는 값이며, aria-valuemin은 진행 상태의 최소값(일반적으로 0), aria-valuemax는 최대값(일반적으로 100)을 나타냅니다.
- 동적 콘텐츠에서 progressbar의 상태를 자주 업데이트할 경우, 진행 상태가 사용자가 이해할 수 있는 속도로 적절히 업데이트되도록 해야 합니다.
- 비활성화된 상태를 나타내기 위해 aria-disabled 속성을 사용할 수 있습니다.
- 시각적인 진행 상태와 텍스트로 표시된 퍼센트 값을 함께 제공하면, 시각적 장애가 있는 사용자뿐만 아니라 모든 사용자에게 더 명확한 정보를 제공할 수 있습니다.

**상속된 상태 및 속성**   
- aria-valuenow: 현재 진행 상태를 나타냅니다. 값은 숫자로 설정됩니다.    
- aria-valuemin: 진행 상태의 최소값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 0입니다.    
- aria-valuemax: 진행 상태의 최대값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 100입니다.    
- aria-disabled: 진행 상태 막대가 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 진행 상태 막대의 레이블과 설명을 참조하는 속성입니다.    



**기본 progressbar 역할 예시**
aria-valuenow를 사용해 현재 진행률을 나타내고, aria-valuemin과 aria-valuemax를 사용해 진행 상태의 범위를 지정합니다. 시각적인 막대는 width 스타일을 통해 진행 상태를 시각적으로 표현할 수 있습니다.   

```sh
// 잘못된 예시 - 진행 상태를 나타내기 위한 aria-valuenow, aria-valuemin, aria-valuemax 속성이 누락
<div role="progressbar">70%</div>

// 올바른 예시
<div role="progressbar" aria-valuenow="70" aria-valuemin="0" aria-valuemax="100" style="width: 70%;">
  70%
</div>

// (권장)시멘틱 요소 사용 -  HTML5의 <progress> 요소를 사용하여 시멘틱하게 진행 상태를 나타냅니다. <progress> 요소는 기본적으로 progressbar 역할을 가집니다.
<progress value="70" max="100">70%</progress>
```

**동적 업데이트가 가능한 progressbar 예시**
이 예시는 자바스크립트를 사용해 진행 상태를 동적으로 업데이트합니다. updateProgress 함수는 aria-valuenow 속성을 업데이트하고, 시각적 막대의 너비와 텍스트를 변경하여 진행 상태를 반영합니다.   
```sh
<div role="progressbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100" id="progressbar" style="width: 0%;">
  0%
</div>

<script>
  function updateProgress(value) {
    const progressBar = document.getElementById('progressbar');
    progressBar.setAttribute('aria-valuenow', value);
    progressBar.style.width = value + '%';
    progressBar.textContent = value + '%';
  }

  // Example: simulate progress update
  let value = 0;
  const interval = setInterval(() => {
    if (value >= 100) clearInterval(interval);
    updateProgress(value);
    value += 10;
  }, 1000);
</script>
```

**비활성화된 progressbar 예시**
aria-disabled="true" 속성을 사용하여 진행 상태 막대가 비활성화되었음을 나타냅니다. 이 상태에서는 진행 상태의 업데이트가 중지되었음을 시각적으로나 보조 기술을 통해 사용자에게 전달할 수 있습니다.  
```sh
<div role="progressbar" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-disabled="true" style="width: 50%;">
  50% (Disabled)
</div>
```


### **11. scrollbar (스크롤바 역할)**    
scrollbar 역할은 스크롤 가능한 콘텐츠 영역의 스크롤바를 나타냅니다. 이 역할은 사용자가 콘텐츠의 특정 부분을 탐색할 수 있도록 도와줍니다. 스크롤바는 수직 또는 수평으로 나타날 수 있으며, 사용자는 스크롤바를 이동시켜 콘텐츠를 탐색합니다. scrollbar 역할은 보조 기술에서 이 요소를 스크롤바로 인식하게 하여 사용자가 콘텐츠의 어느 부분을 보고 있는지, 그리고 스크롤 가능한 범위 내에서 현재 위치가 어디인지를 전달합니다.        
[W3C ARIA scrollbar](https://www.w3.org/TR/wai-aria-1.2/#scrollbar){: target="_blank"}   
[MDN ARIA scrollbar](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/scrollbar_role){: target="_blank"}   

**기본 설명** 
- scrollbar 역할은 스크롤 가능한 콘텐츠 영역의 스크롤바를 정의하며, 사용자가 스크롤 가능한 콘텐츠를 탐색할 수 있도록 돕습니다.    
- 스크롤바의 위치 및 상태를 나타내기 위해 aria-valuenow, aria-valuemin, aria-valuemax, aria-orientation 등의 속성이 사용됩니다.    
- 수직 스크롤바는 aria-orientation="vertical"을, 수평 스크롤바는 aria-orientation="horizontal"을 사용하여 정의됩니다.    

**사용 시 주의사항**   
- scrollbar 역할을 사용할 때는 반드시 aria-valuenow, aria-valuemin, aria-valuemax, aria-orientation 속성을 설정해야 하며, 이를 통해 보조 기술이 스크롤바의 상태를 정확히 전달할 수 있도록 합니다.   
- aria-valuenow는 현재 스크롤바 위치를 나타내며, aria-valuemin은 스크롤 가능한 범위의 최소값, aria-valuemax는 최대값을 나타냅니다.
- aria-orientation 속성은 스크롤 방향을 지정하며, 가능한 값은 vertical(수직) 또는 horizontal(수평)입니다.
- 비활성화된 스크롤바를 나타내기 위해 aria-disabled 속성을 사용할 수 있습니다. 이 경우, 사용자에게 스크롤이 불가능함을 명확히 전달해야 합니다.
- 시각적인 스크롤 핸들을 제공하여 사용자가 스크롤 가능한 범위와 현재 위치를 명확히 이해할 수 있도록 합니다.

**상속된 상태 및 속성**   
- aria-valuenow: 스크롤바의 현재 위치를 나타냅니다. 값은 숫자로 설정됩니다.    
- aria-valuemin: 스크롤 가능한 범위의 최소값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 0입니다.    
- aria-valuemax: 스크롤 가능한 범위의 최대값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 100입니다.    
- aria-orientation: 스크롤바의 방향을 나타냅니다. 가능한 값은 vertical(수직) 또는 horizontal(수평)입니다.    
- aria-disabled: 스크롤바가 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 스크롤바의 레이블과 설명을 참조하는 속성입니다.    



**기본 scrollbar 역할 예시**
scrollbar 역할을 제대로 구현하기 위해서는 aria-valuenow, aria-valuemin, aria-valuemax 속성을 사용하여 스크롤바의 현재 위치와 범위를 정의하고 aria-orientation="vertical" 속성을 사용하여 스크롤바가 수직임을 나타냅니다. 또한, tabindex="0"을 추가하여 키보드 탐색이 가능하도록 해야 합니다.
```sh
// 잘못된 예시 - 스크롤 가능한 범위 및 현재 위치를 나타내는 aria-valuenow, aria-valuemin, aria-valuemax 속성이 누락, 스크롤 방향을 나타내기 위해 aria-orientation 속성 누락
<div role="scrollbar"></div>

// 올바른 예시
<div role="scrollbar" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-orientation="vertical" tabindex="0" style="height: 100px;">
  <!-- 스크롤 핸들 -->
  <div style="height: 50%; background-color: #ccc;"></div>
</div>

// 기본 HTML에서는 별도의 시멘틱 스크롤바 요소가 없으므로, ARIA 속성을 사용하여 의미를 명확히 합니다.
```

**동적 스크롤바 업데이트 예시**
스크롤바의 위치를 동적으로 업데이트하는 예제입니다. updateScrollbar 함수는 스크롤바의 위치를 변경하면서 aria-valuenow 속성을 업데이트하고, 시각적으로도 스크롤 핸들의 위치를 변경합니다.  
```sh
<div role="scrollbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100" aria-orientation="horizontal" tabindex="0" id="scrollbar" style="width: 100%;">
  <!-- 스크롤 핸들 -->
  <div id="scroll-handle" style="width: 10%; background-color: #ccc;"></div>
</div>

<script>
  function updateScrollbar(position) {
    const scrollbar = document.getElementById('scrollbar');
    const handle = document.getElementById('scroll-handle');
    scrollbar.setAttribute('aria-valuenow', position);
    handle.style.left = position + '%';
  }

  // 예시: 스크롤바 업데이트 시뮬레이션
  let position = 0;
  const interval = setInterval(() => {
    if (position >= 100) clearInterval(interval);
    updateScrollbar(position);
    position += 10;
  }, 1000);
</script>
```

**비활성화된 scrollbar 예시**
aria-disabled="true" 속성을 사용하여 스크롤바가 비활성화되었음을 나타내고 있으며, 키보드 탐색에서 제외하기 위해 tabindex="-1"을 설정했습니다.  
```sh
<div role="scrollbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100" aria-orientation="vertical" aria-disabled="true" tabindex="-1" style="height: 100px;">
  <!-- 스크롤 핸들 -->
  <div style="height: 50%; background-color: #ccc;"></div>
</div>
```


### **12. searchbox (검색 상자 역할)**    
searchbox 역할은 사용자가 검색어를 입력할 수 있는 텍스트 필드를 나타냅니다. 이 역할은 검색 기능을 제공하는 입력 필드를 정의하며, 일반적으로 검색 버튼과 함께 사용됩니다. searchbox 역할을 사용하면 보조 기술이 이 필드가 검색을 위한 것임을 명확히 인식할 수 있습니다.        
HTML5의 &lt;input type="search"&gt; 요소는 기본적으로 검색 상자 역할을 가지며, 보조 기술이 이 필드가 검색을 위한 것임을 자동으로 인식하기 때문에 role="searchbox"는 사용을 안하는것을 권장합니다.    
[W3C ARIA searchbox](https://www.w3.org/TR/wai-aria-1.2/#searchbox){: target="_blank"}   
[MDN ARIA searchbox](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/searchbox_role){: target="_blank"}   
[input type요소 참조 - UXKM search](https://uxkm.io/publishing/html/09-forms/03-input_element_part1#gsc.tab=0){: target="_blank"}    

**기본 설명** 
- searchbox 역할은 사용자가 검색어를 입력할 수 있는 필드를 정의합니다.    
- 이 역할은 aria-required, aria-invalid, aria-autocomplete 등의 속성을 사용하여 필드의 상태와 동작을 정의할 수 있습니다.    
- 검색 상자는 기본적으로 텍스트 입력 필드로 구현되며, 보조 기술은 이 필드가 검색 목적임을 알 수 있습니다.    

**사용 시 주의사항**   
- 시멘틱 요소 사용을 권장합니다.   
- searchbox 역할을 사용할 때는 aria-label 속성을 통해 검색 상자의 목적을 명확히 해야 합니다.   
- 필수 입력 필드일 경우 aria-required="true"를 사용하여 사용자에게 이를 알립니다.
- 자동 완성 기능이 포함된 경우, aria-autocomplete 속성을 사용하여 보조 기술이 자동 완성 기능을 인식하도록 합니다.
- 유효성 검사가 필요한 경우, aria-invalid 속성을 사용하여 검색어의 유효성을 나타낼 수 있습니다. 유효하지 않은 경우 관련 메시지를 제공해야 합니다.
- 검색 상자는 일반적으로 버튼과 함께 사용되므로, 검색 버튼과의 관계를 명확히 해야 합니다.

**상속된 상태 및 속성**   
- aria-required: 검색 상자가 필수 입력 필드인지 여부를 나타냅니다.    
- aria-invalid: 검색 상자의 입력 내용이 유효한지 여부를 나타냅니다.    
- aria-autocomplete: 검색 상자에서 자동 완성 기능이 작동하는 방식을 나타냅니다. 가능한 값은 none, list, inline, both입니다.    
- aria-labelledby, aria-describedby: 검색 상자의 레이블과 설명을 참조하는 속성입니다.    



**기본 searchbox 역할 예시**
role="searchbox"를 사용해 검색 상자 역할을 명확히 정의하고 aria-label 속성을 통해 보조 기술이 검색 상자의 목적을 명확히 알 수 있도록 해야 합니다.    
```sh
// 잘못된 예시 - 기본 텍스트 입력 필드로 검색 기능을 제공할 수 있지만, 보조 기술이 이 필드가 검색을 위한 것임을 명확히 인식하지 못할 수 있습니다.
<input type="text" placeholder="Search...">

// (권장) 올바른 예시 시멘틱 요소 사용 - HTML5의 <input type="search"> 요소는 기본적으로 검색 상자 역할을 가지며, 보조 기술이 이 필드가 검색을 위한 것임을 자동으로 인식합니다.
<input type="search" aria-label="Search the site" placeholder="Search...">
```

**자동 완성 기능이 포함된 searchbox 예시**
aria-autocomplete="list" 속성을 사용하여 자동 완성 기능이 포함된 검색 상자를 구현했습니다. datalist 요소는 사용자가 입력할 때 검색어 제안을 제공합니다.  
```sh
<input type="search" aria-label="Search the site" aria-autocomplete="list" placeholder="Search..." list="search-suggestions">
<datalist id="search-suggestions">
  <option value="HTML"></option>
  <option value="CSS"></option>
  <option value="JavaScript"></option>
</datalist>
```

**필수 입력 searchbox 예시**
aria-required="true" 속성을 사용하여 검색 상자가 필수 입력 필드임을 나타냅니다. 사용자가 이 필드를 비워두고 제출하려고 할 때, 보조 기술은 이를 경고할 수 있습니다.  
```sh
<input type="search" aria-label="Search the site" aria-required="true" placeholder="Search...">
```

**유효성 검사가 포함된 searchbox 예시**
aria-invalid 속성을 사용하여 검색 쿼리의 유효성을 검사하는 예제입니다. 사용자가 입력한 내용이 유효하지 않은 경우, 보조 기술은 이를 알리고 관련 오류 메시지를 제공할 수 있습니다.  
```sh
<input type="search" aria-label="Search the site" aria-invalid="false" placeholder="Search...">
<p id="error-message" style="display: none;">Invalid search query</p>

<script>
  const searchBox = document.querySelector('input[role="searchbox"]');
  searchBox.addEventListener('input', function() {
    if (searchBox.value.length < 3) {
      searchBox.setAttribute('aria-invalid', 'true');
      document.getElementById('error-message').style.display = 'block';
    } else {
      searchBox.setAttribute('aria-invalid', 'false');
      document.getElementById('error-message').style.display = 'none';
    }
  });
</script>
```


### **13. separator (구분선 역할, 포커스 가능할 때)**    
separator 역할은 콘텐츠를 구분하기 위한 시각적인 선을 나타내며, 이 요소가 포커스(초점)를 받을 수 있을 때 ARIA 역할로 설정됩니다. 포커스(초점) 가능한 구분선은 종종 슬라이더, 드래그 앤 드롭 또는 키보드 내비게이션을 위한 핸들 역할을 수행합니다. 이러한 구분선은 사용자가 구분선을 이동시켜 레이아웃을 조정하거나 특정 동작을 트리거할 수 있도록 설계됩니다.    
[W3C ARIA separator](https://www.w3.org/TR/wai-aria-1.2/#separator){: target="_blank"}   
[MDN ARIA separator](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/separator_role){: target="_blank"}   

**기본 설명** 
- separator 역할은 일반적으로 콘텐츠를 시각적으로 구분하는 수평 또는 수직 선을 나타냅니다.    
- 포커스(초점) 가능한 경우, 이 역할은 슬라이더나 패널 조절기 등으로 사용될 수 있으며, aria-orientation, aria-valuenow, aria-valuemin, aria-valuemax 등의 속성으로 현재 상태를 나타낼 수 있습니다.    
- 보조 기술을 통해 구분선의 위치와 역할이 사용자에게 전달됩니다.    

**사용 시 주의사항**   
- separator 역할을 사용할 때는 반드시 aria-orientation 속성을 통해 구분선의 방향을 지정해야 합니다. 가능한 값은 horizontal(수평) 또는 vertical(수직)입니다.   
- 포커스 가능한 구분선의 경우, aria-valuenow, aria-valuemin, aria-valuemax 속성을 설정하여 구분선의 현재 위치와 조정 가능한 범위를 나타내야 합니다.
- 사용자가 키보드를 사용해 구분선을 조정할 수 있도록, tabindex="0"을 설정하고 적절한 키보드 이벤트 핸들러를 구현해야 합니다.
- 비활성화된 구분선은 aria-disabled="true" 속성을 사용해 표시할 수 있으며, 이 경우 포커스가 불가능하도록 설정해야 합니다.

**상속된 상태 및 속성**   
- aria-orientation: 구분선의 방향을 나타냅니다. 가능한 값은 horizontal 또는 vertical입니다.    
- aria-valuenow: 구분선의 현재 위치를 나타냅니다. 값은 숫자로 설정됩니다.    
- aria-valuemin: 구분선의 조정 가능한 범위의 최소값을 나타냅니다. 값은 숫자로 설정됩니다.    
- aria-valuemax: 구분선의 조정 가능한 범위의 최대값을 나타냅니다. 값은 숫자로 설정됩니다.    
- aria-disabled: 구분선이 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 구분선의 레이블과 설명을 참조하는 속성입니다.    



**기본 separator 역할 (포커스 불가능한 상태) 예시**
이 예시는 포커스가 불가능한 기본 구분선을 나타냅니다. &lt;hr&gt; 요소는 시각적으로 콘텐츠를 구분하는 역할을 하며, 보조 기술에서 이 요소를 구분선으로 인식하게 합니다. 이 경우, separator는 단순한 시각적 구분용으로만 사용됩니다.   
```sh
<hr role="separator">
```

**포커스 가능한 separator 역할 예시**
이 예시는 포커스 가능한 구분선으로, 사용자가 키보드나 마우스를 통해 이 구분선을 이동하여 레이아웃을 조정할 수 있습니다. aria-valuenow, aria-valuemin, aria-valuemax 속성을 통해 구분선의 현재 위치와 조정 가능한 범위를 나타내며, aria-orientation 속성으로 구분선의 방향(수평)을 지정합니다. 
```sh
<div role="separator" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-orientation="horizontal" tabindex="0" style="height: 5px; background-color: #ccc;">
  <!-- 구분선을 조정할 수 있는 핸들 -->
</div>
```

**동적 조절 가능한 separator 예시**
이 구분선은 키보드(화살표 키)를 통해 조정할 수 있으며, aria-valuenow 속성이 업데이트됩니다. 사용자는 이 구분선을 사용해 패널의 크기를 조정할 수 있습니다. 스크립트는 키보드 입력에 따라 구분선의 위치를 변경하고, 보조 기술이 구분선의 새 위치를 인식하도록 합니다.  
```sh
<div role="separator" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-orientation="vertical" tabindex="0" id="separator" style="width: 5px; background-color: #ccc;">
  <!-- 구분선을 조정할 수 있는 핸들 -->
</div>

<script>
  document.getElementById('separator').addEventListener('keydown', function(event) {
    let currentValue = parseInt(this.getAttribute('aria-valuenow'));
    if (event.key === 'ArrowUp' || event.key === 'ArrowRight') {
      currentValue = Math.min(currentValue + 10, 100);
    } else if (event.key === 'ArrowDown' || event.key === 'ArrowLeft') {
      currentValue = Math.max(currentValue - 10, 0);
    }
    this.setAttribute('aria-valuenow', currentValue);
    // 시각적으로 구분선 위치를 조정
    this.style.height = currentValue + '%';
  });
</script>
```

**비활성화된 separator 예시**
aria-disabled="true" 속성을 사용하여 구분선이 비활성화되었음을 나타내고 있으며, 이 상태에서는 구분선을 조정할 수 없습니다. 또한, 포커스가 불가능하도록 tabindex="-1"로 설정되었습니다.  
```sh
<div role="separator" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-orientation="horizontal" aria-disabled="true" tabindex="-1" style="height: 5px; background-color: #ccc;">
  <!-- 비활성화된 구분선 -->
</div>
```


### **14. slider (슬라이더 역할)**    
slider 역할은 사용자가 특정 범위 내에서 값을 선택할 수 있도록 해주는 UI 요소를 나타냅니다. 슬라이더는 일반적으로 사용자가 드래그하거나 키보드를 사용하여 값을 조정할 수 있는 수평 또는 수직의 막대 형태로 제공됩니다. 슬라이더는 aria-valuenow, aria-valuemin, aria-valuemax, aria-orientation 등의 ARIA 속성을 통해 현재 값과 범위를 설정하고, 사용자가 슬라이더의 상태를 쉽게 파악할 수 있도록 돕습니다.    
[W3C ARIA slider](https://www.w3.org/TR/wai-aria-1.2/#slider){: target="_blank"}   
[MDN ARIA slider](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/slider_role){: target="_blank"}   
[input type요소 참조 - UXKM range](https://uxkm.io/publishing/html/09-forms/03-input_element_part1#gsc.tab=0){: target="_blank"}    

**기본 설명** 
- slider 역할은 사용자가 특정 값이나 범위를 선택할 수 있는 인터랙티브 요소를 정의합니다.    
- 슬라이더는 수평(horizontal) 또는 수직(vertical) 방향으로 설정될 수 있으며, 현재 선택된 값을 시각적으로 나타냅니다.    
- 보조 기술은 aria-valuenow, aria-valuemin, aria-valuemax 속성을 사용하여 슬라이더의 현재 값, 최소값, 최대값을 사용자에게 전달합니다.    

**사용 시 주의사항**   
- slider 역할을 사용할 때는 반드시 aria-valuenow, aria-valuemin, aria-valuemax, aria-orientation 속성을 설정하여 슬라이더의 현재 값, 최소값, 최대값, 방향을 명확히 정의해야 합니다.   
- 사용자가 키보드를 사용해 슬라이더를 탐색하고 값을 조정할 수 있도록, tabindex="0"을 설정하고 키보드 이벤트 핸들러를 구현해야 합니다.
- 슬라이더가 비활성화된 경우, aria-disabled="true" 속성을 사용하여 보조 기술이 이를 인식할 수 있도록 해야 합니다.
- 수직 또는 수평 방향의 슬라이더를 구현할 때, aria-orientation 속성을 적절히 설정해야 합니다.
- 슬라이더의 현재 값을 시각적으로도 반영하여 사용자가 시각적으로 현재 위치를 쉽게 파악할 수 있도록 해야 합니다.

**상속된 상태 및 속성**   
- aria-valuenow: 슬라이더의 현재 값을 나타냅니다. 값은 숫자로 설정됩니다.    
- aria-valuemin: 슬라이더의 최소값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 0입니다.    
- aria-valuemax: 슬라이더의 최대값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 100입니다.    
- aria-orientation: 슬라이더의 방향을 나타냅니다. 가능한 값은 horizontal(수평) 또는 vertical(수직)입니다.    
- aria-disabled: 슬라이더가 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 슬라이더의 레이블과 설명을 참조하는 속성입니다.    



**기본 slider 역할 예시**
시멘틱 요소 사용을 권장하며, HTML5의 &lt;input type="range"&gt; 요소를 사용하여 시멘틱하게 슬라이더를 구현합니다. 이 요소는 기본적으로 slider 역할을 가지며, 보조 기술은 이를 슬라이더로 인식합니다.   
슬라이더는 aria-valuenow(현재 값), aria-valuemin(최소값), aria-valuemax(최대값) 속성을 사용하여 현재 상태를 정의하고, 키보드 탐색이 가능하도록 tabindex="0"이 설정되어 있어야 합니다.    
```sh
// 잘못된 예시 - aria-valuenow, aria-valuemin, aria-valuemax 등의 속성 미제공. 또한, 슬라이더의 방향을 지정하는 aria-orientation 속성도 미제공
<div role="slider">50</div>

// 올바른 예시
<div role="slider" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-orientation="horizontal" tabindex="0" style="width: 200px; height: 10px; background-color: #ddd;">
  <!-- 슬라이더 핸들 -->
  <div style="width: 20px; height: 20px; background-color: #000; position: relative; left: 50%; top: -5px;"></div>
</div>

// (권장) 시멘틱 요소 사용
<input type="range" min="0" max="100" value="50">
```

**동적으로 업데이트 가능한 slider 예시**
이 예시는 키보드를 사용해 슬라이더의 값을 동적으로 변경할 수 있는 슬라이더를 구현한 것입니다. ArrowRight, ArrowLeft, ArrowUp, ArrowDown 키로 슬라이더 값을 조정할 수 있으며, 이에 따라 슬라이더 핸들의 위치가 변경됩니다.  
```sh
<div role="slider" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-orientation="horizontal" tabindex="0" id="mySlider" style="width: 200px; height: 10px; background-color: #ddd;">
  <!-- 슬라이더 핸들 -->
  <div id="handle" style="width: 20px; height: 20px; background-color: #000; position: relative; left: 50%; top: -5px;"></div>
</div>

<script>
  const slider = document.getElementById('mySlider');
  const handle = document.getElementById('handle');

  slider.addEventListener('keydown', function(event) {
    let value = parseInt(slider.getAttribute('aria-valuenow'));
    if (event.key === 'ArrowRight' || event.key === 'ArrowUp') {
      value = Math.min(value + 1, 100);
    } else if (event.key === 'ArrowLeft' || event.key === 'ArrowDown') {
      value = Math.max(value - 1, 0);
    }
    slider.setAttribute('aria-valuenow', value);
    handle.style.left = value + '%';
  });
</script>
```

**수직 slider 예시**
이 예시는 수직 슬라이더를 구현한 것입니다. aria-orientation="vertical" 속성을 사용해 슬라이더의 방향을 수직으로 설정했으며, 슬라이더 핸들은 현재 값에 따라 위치가 조정됩니다.  
```sh
<div role="slider" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" aria-orientation="vertical" tabindex="0" style="width: 10px; height: 200px; background-color: #ddd;">
  <!-- 슬라이더 핸들 -->
  <div style="width: 20px; height: 20px; background-color: #000; position: relative; top: 30%;"></div>
</div>
```

**비활성화된 slider 예시**
이 슬라이더는 aria-disabled="true" 속성을 사용해 비활성화되었습니다. 슬라이더는 비활성화 상태이므로, 키보드 탐색에서도 제외되도록 tabindex="-1"로 설정되었습니다.  
```sh
<div role="slider" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" aria-orientation="horizontal" aria-disabled="true" tabindex="-1" style="width: 200px; height: 10px; background-color: #ddd;">
  <!-- 비활성화된 슬라이더 핸들 -->
  <div style="width: 20px; height: 20px; background-color: #888; position: relative; left: 50%; top: -5px;"></div>
</div>
```


### **15. spinbutton (스핀 버튼 역할)**    
spinbutton 역할은 사용자가 특정 범위 내에서 값을 증가 또는 감소시켜 선택할 수 있는 입력 필드를 나타냅니다. 스핀 버튼은 일반적으로 숫자 입력 필드로 구현되며, 사용자는 키보드나 마우스를 사용하여 값을 조정할 수 있습니다. spinbutton 역할은 aria-valuenow, aria-valuemin, aria-valuemax 등의 ARIA 속성을 통해 현재 값과 범위를 설정하여 보조 기술이 이를 정확하게 인식하도록 도와줍니다.    
[W3C ARIA spinbutton](https://www.w3.org/TR/wai-aria-1.2/#spinbutton){: target="_blank"}   
[MDN ARIA spinbutton](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/spinbutton_role){: target="_blank"}   
[input type요소 참조 - UXKM number](https://uxkm.io/publishing/html/09-forms/03-input_element_part1#gsc.tab=0){: target="_blank"}    

**기본 설명** 
- spinbutton 역할은 사용자가 값을 직접 입력하거나 버튼을 사용해 값을 증가 또는 감소시킬 수 있는 UI 요소를 정의합니다.    
- 보조 기술은 aria-valuenow, aria-valuemin, aria-valuemax 속성을 사용하여 스핀 버튼의 현재 값, 최소값, 최대값을 사용자에게 전달합니다.    
- 스핀 버튼은 일반적으로 숫자 입력 필드로 사용되며, 사용자가 특정 범위 내에서 값을 선택할 수 있도록 합니다.    

**사용 시 주의사항**   
- spinbutton 역할을 사용할 때는 반드시 aria-valuenow, aria-valuemin, aria-valuemax 속성을 설정하여 스핀 버튼의 현재 값과 조정 가능한 범위를 정의해야 합니다.   
- 사용자가 키보드를 사용해 스핀 버튼의 값을 조정할 수 있도록, tabindex="0"을 설정하고 키보드 이벤트 핸들러를 구현해야 합니다.
- 스핀 버튼이 비활성화된 경우, aria-disabled="true" 속성을 사용하여 보조 기술이 이를 인식할 수 있도록 해야 합니다.
- 스핀 버튼의 현재 값을 시각적으로도 반영하여 사용자가 현재 선택된 값을 쉽게 파악할 수 있도록 해야 합니다.

**상속된 상태 및 속성**   
- aria-valuenow: 스핀 버튼의 현재 값을 나타냅니다. 값은 숫자로 설정됩니다.    
- aria-valuemin: 스핀 버튼의 최소값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 0입니다.    
- aria-valuemax: 스핀 버튼의 최대값을 나타냅니다. 값은 숫자로 설정되며, 기본값은 100입니다.    
- aria-disabled: 스핀 버튼이 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 스핀 버튼의 레이블과 설명을 참조하는 속성입니다.    



**기본 spinbutton 역할 예시**
시멘틱 요소 사용을 권장하며, HTML5의 &lt;input type="number"&gt; 요소는 기본적으로 spinbutton 역할을 가지며, 보조 기술은 이를 스핀 버튼으로 인식합니다.   
aria-valuenow, aria-valuemin, aria-valuemax 속성을 사용하여 스핀 버튼의 현재 값과 범위를 정의해야 하며, tabindex="0"을 설정하여 키보드 탐색이 가능하도록 해야 합니다.   
```sh
// 잘못된 예시 - aria-valuenow, aria-valuemin, aria-valuemax 속성 미제공. 이러한 속성 없이 보조 기술은 현재 값을 전달할 수 없습니다.
<div role="spinbutton">10</div>

// 올바른 예시
<div role="spinbutton" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100" tabindex="0" style="display: inline-block; border: 1px solid #ccc; padding: 5px; width: 50px; text-align: center;">
  10
</div>

// (권장) 시멘틱 요소 사용
<input type="number" min="0" max="100" value="10">
```

**동적으로 업데이트 가능한 spinbutton 예시**
이 예시는 키보드를 사용해 값을 증가(위쪽 화살표) 또는 감소(아래쪽 화살표)할 수 있는 스핀 버튼을 구현한 것입니다. 현재 값은 aria-valuenow 속성에 반영되며, 시각적으로도 업데이트됩니다.  
```sh
<div role="spinbutton" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100" tabindex="0" id="mySpinbutton" style="display: inline-block; border: 1px solid #ccc; padding: 5px; width: 50px; text-align: center;">
  10
</div>

<script>
  const spinbutton = document.getElementById('mySpinbutton');

  spinbutton.addEventListener('keydown', function(event) {
    let value = parseInt(spinbutton.getAttribute('aria-valuenow'));
    if (event.key === 'ArrowUp') {
      value = Math.min(value + 1, 100);
    } else if (event.key === 'ArrowDown') {
      value = Math.max(value - 1, 0);
    }
    spinbutton.setAttribute('aria-valuenow', value);
    spinbutton.textContent = value;
  });
</script>
```

**비활성화된 spinbutton 예시**
aria-disabled="true" 속성을 사용하여 스핀 버튼이 비활성화되었음을 나타내고 있습니다. 이 상태에서는 스핀 버튼이 사용 불가능하며, 포커스도 받을 수 없습니다(tabindex="-1").  
```sh
<div role="spinbutton" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100" aria-disabled="true" tabindex="-1" style="display: inline-block; border: 1px solid #ccc; padding: 5px; width: 50px; text-align: center; color: #999;">
  10
</div>
```

**증가 및 감소 버튼이 포함된 spinbutton 예시**
이 예시는 증가(+) 및 감소(-) 버튼이 포함된 스핀 버튼입니다. 사용자는 버튼을 클릭하여 값을 조정할 수 있으며, 보조 기술은 현재 값을 정확히 전달받을 수 있습니다.  
```sh
<div role="spinbutton" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100" tabindex="0" id="spinbuttonWithControls" style="display: flex; align-items: center; border: 1px solid #ccc; width: 100px;">
  <button onclick="adjustValue(-1)" style="width: 30px;">-</button>
  <div id="spinbuttonValue" style="flex: 1; text-align: center;">10</div>
  <button onclick="adjustValue(1)" style="width: 30px;">+</button>
</div>

<script>
  function adjustValue(change) {
    const spinbutton = document.getElementById('spinbuttonWithControls');
    let value = parseInt(spinbutton.getAttribute('aria-valuenow'));
    value = Math.max(0, Math.min(100, value + change));
    spinbutton.setAttribute('aria-valuenow', value);
    document.getElementById('spinbuttonValue').textContent = value;
  }
</script>
```

### **16. switch (스위치 역할)**    
switch 역할은 사용자가 켜기와 끄기 상태 사이를 전환할 수 있는 토글 버튼을 나타냅니다. 스위치는 일반적으로 두 가지 상태(예: "켜짐"/"꺼짐", "사용"/"미사용") 중 하나를 나타내며, 사용자가 이 상태를 변경할 수 있습니다. 이 역할은 aria-checked 속성을 사용하여 스위치의 현재 상태를 보조 기술이 인식할 수 있도록 합니다.    
[W3C ARIA switch](https://www.w3.org/TR/wai-aria-1.2/#switch){: target="_blank"}   
[MDN ARIA switch](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/switch_role){: target="_blank"}   
[input type요소 참조 - UXKM checkbox](https://uxkm.io/publishing/html/09-forms/03-input_element_part1#gsc.tab=0){: target="_blank"}    

**기본 설명** 
- switch 역할은 사용자가 클릭하여 두 가지 상태(예: 켜짐/꺼짐)를 전환할 수 있는 UI 요소를 정의합니다.    
- switch 역할은 기본적으로 토글 버튼과 유사하지만, 스위치를 표현할 때 더 적합한 역할입니다.    
- 보조 기술은 aria-checked 속성을 통해 스위치가 현재 켜져 있는지(true) 또는 꺼져 있는지(false)를 인식합니다.    

**사용 시 주의사항**   
- switch 역할을 사용할 때는 반드시 aria-checked 속성을 사용하여 스위치의 상태를 명확히 나타내야 합니다. 가능한 값은 true(켜짐)와 false(꺼짐)입니다.   
- 키보드 접근성을 보장하기 위해 tabindex="0"을 설정하고, 키보드 이벤트 핸들러를 통해 스위치를 제어할 수 있도록 해야 합니다.
- 스위치가 비활성화된 경우, aria-disabled="true" 속성을 사용하여 보조 기술이 이를 인식할 수 있도록 해야 하며, 시각적으로도 비활성화 상태를 명확히 나타내야 합니다.
- 스위치의 상태를 시각적으로 명확하게 표현하여 사용자가 상태 변화를 쉽게 인식할 수 있도록 합니다.

**상속된 상태 및 속성**   
- aria-checked: 스위치의 현재 상태를 나타냅니다. 값은 true(켜짐) 또는 false(꺼짐)입니다.    
- aria-disabled: 스위치가 비활성화되었는지 여부를 나타냅니다.    
- aria-labelledby, aria-describedby: 스위치의 레이블과 설명을 참조하는 속성입니다.    



**기본 switch 역할 예시**
시멘틱 요소 사용을 권장하며, HTML5의 &lt;input type="checkbox"&gt; 요소를 사용하면 기본적으로 switch 역할을 가지며, 보조 기술은 이를 스위치로 인식합니다.   
aria-checked="false" 속성으로 초기 상태를 꺼짐(Off)으로 설정하고, 클릭 시 상태 토글. 시각적으로도 상태를 업데이트하여 사용자가 쉽게 스위치의 상태를 확인할 수 있게 합니다.   
```sh
// 잘못된 예시 - aria-checked 속성 미제공 또한, 키보드 탐색을 위한 tabindex 미제공.
<div role="switch">Toggle</div>

// 올바른 예시
<div role="switch" aria-checked="false" tabindex="0" style="display: inline-block; padding: 10px; background-color: #ddd; cursor: pointer;">
  Off
</div>

<script>
  const switchElement = document.querySelector('[role="switch"]');
  switchElement.addEventListener('click', function() {
    const isChecked = this.getAttribute('aria-checked') === 'true';
    this.setAttribute('aria-checked', !isChecked);
    this.textContent = !isChecked ? 'On' : 'Off';
    this.style.backgroundColor = !isChecked ? '#4CAF50' : '#ddd';
  });
</script>

// (권장) 시멘틱 요소 사용
<label class="switch">
  <input type="checkbox">
  <span class="slider"></span>
</label>
```

**동적으로 업데이트 가능한 switch 예시**
이 예시는 키보드와 마우스를 사용해 상태를 토글할 수 있는 동적 스위치를 구현한 것입니다. Enter 키 또는 Space 키를 눌러 스위치 상태를 변경할 수 있으며, 보조 기술은 이 상태 변화를 인식합니다.  
```sh
<div role="switch" aria-checked="true" tabindex="0" id="dynamicSwitch" style="display: inline-block; padding: 10px; background-color: #4CAF50; cursor: pointer;">
  On
</div>

<script>
  const dynamicSwitch = document.getElementById('dynamicSwitch');

  dynamicSwitch.addEventListener('keydown', function(event) {
    if (event.key === 'Enter' || event.key === ' ') {
      const isChecked = this.getAttribute('aria-checked') === 'true';
      this.setAttribute('aria-checked', !isChecked);
      this.textContent = !isChecked ? 'On' : 'Off';
      this.style.backgroundColor = !isChecked ? '#4CAF50' : '#ddd';
    }
  });

  dynamicSwitch.addEventListener('click', function() {
    const isChecked = this.getAttribute('aria-checked') === 'true';
    this.setAttribute('aria-checked', !isChecked);
    this.textContent = !isChecked ? 'On' : 'Off';
    this.style.backgroundColor = !isChecked ? '#4CAF50' : '#ddd';
  });
</script>
```

**비활성화된 switch 예시**
aria-disabled="true" 속성을 사용하여 스위치가 비활성화된 상태임을 나타내고 있습니다. 이 상태에서는 스위치가 클릭되거나 포커스를 받을 수 없습니다(tabindex="-1").  
```sh
<div role="switch" aria-checked="true" aria-disabled="true" tabindex="-1" style="display: inline-block; padding: 10px; background-color: #bbb; cursor: not-allowed;">
  On
</div>
```

**다양한 스타일의 switch 예시**
이 예시는 스위치를 다양한 스타일로 꾸며서, 시각적으로 더 눈에 띄는 인터페이스를 제공합니다. 스위치가 클릭될 때마다 핸들이 이동하며 배경색도 변경됩니다.  
```sh
<div role="switch" aria-checked="false" tabindex="0" style="display: inline-block; padding: 10px; background-color: #ddd; cursor: pointer; border-radius: 20px; width: 40px; height: 20px; position: relative;">
  <div style="background-color: #fff; border-radius: 50%; width: 20px; height: 20px; position: absolute; top: 0; left: 0; transition: all 0.3s;"></div>
</div>

<script>
  const styledSwitch = document.querySelector('[role="switch"]');
  styledSwitch.addEventListener('click', function() {
    const isChecked = this.getAttribute('aria-checked') === 'true';
    this.setAttribute('aria-checked', !isChecked);
    const handle = this.querySelector('div');
    handle.style.left = !isChecked ? '20px' : '0';
    this.style.backgroundColor = !isChecked ? '#4CAF50' : '#ddd';
  });
</script>
```

### **17. tab (탭 역할)**    
tab 역할은 탭 인터페이스에서 사용되는 개별 탭을 나타냅니다. 사용자는 탭을 클릭하거나 키보드를 사용해 선택하여 관련 콘텐츠를 활성화할 수 있습니다. tab 역할은 일반적으로 tablist 역할과 함께 사용되며, tablist는 여러 tab을 포함하는 컨테이너 역할을 합니다. 각 tab 요소는 고유한 tabpanel과 연관되어 있어, 사용자가 선택한 탭에 따라 해당 tabpanel이 활성화됩니다.    
[W3C ARIA tab](https://www.w3.org/TR/wai-aria-1.2/#tab){: target="_blank"}   
[MDN ARIA tab](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tab_role){: target="_blank"}   

**기본 설명** 
- tab 역할은 탭 인터페이스에서 개별 탭을 정의합니다.    
- 사용자는 클릭하거나 키보드를 사용해 탭을 탐색하고 선택할 수 있습니다.   
- aria-selected 속성을 사용하여 현재 선택된 탭을 나타내며, aria-controls 속성으로 해당 탭이 제어하는 tabpanel을 지정합니다.    
- 탭은 일반적으로 tablist 컨테이너 안에 포함되며, 선택된 탭에 따라 관련 콘텐츠(tabpanel)가 표시됩니다.    

**사용 시 주의사항**   
- tab 역할을 사용할 때는 반드시 aria-selected 속성을 설정하여 현재 선택된 탭을 명확히 표시해야 합니다. 값은 true(선택됨) 또는 false(선택되지 않음)입니다.   
- 각 tab 요소는 aria-controls 속성을 사용하여 제어하는 tabpanel을 지정해야 합니다. 이 속성은 tabpanel의 ID와 연결되어야 합니다.
- tabpanel은 tab과 연결되어야 하며, 탭이 선택될 때 해당 tabpanel만 표시되고 나머지는 숨겨져야 합니다.
- 비활성화된 탭은 aria-disabled="true" 속성을 사용하여 표시하며, 시각적으로도 이를 나타내야 합니다.
- 키보드 내비게이션을 지원하도록 구현하여 사용자가 탭을 쉽게 탐색할 수 있도록 해야 합니다.

**상속된 상태 및 속성**   
- aria-selected: 현재 탭의 선택 상태를 나타냅니다. 값은 true(선택됨) 또는 false(선택되지 않음)입니다.    
- aria-controls: 탭이 제어하는 tabpanel의 ID를 참조합니다.    
- aria-disabled: 탭이 비활성화되었는지 여부를 나타냅니다.    



**기본 tab 역할 예시**
시멘틱 요소 사용을 권장하며, &lt;button&gt; 요소를 사용하여 탭을 구현. 탭 버튼과 관련 콘텐츠가 올바르게 연결되어 보조 기술이 이 구조를 정확히 이해할 수 있도록 합니다.   
tab과 tabpanel을 올바르게 연결한 것입니다. aria-controls 속성을 사용해 각 tab이 제어하는 tabpanel을 명시했고, aria-selected 속성으로 현재 선택된 탭을 나타냈습니다. 선택되지 않은 탭은 tabindex="-1"을 사용해 포커스가 불가능하도록 설정되었습니다.    

```sh
// 잘못된 예시 - tab과 tabpanel이 연결되지 않았고, aria-selected 및 aria-controls 속성 누락.
<div role="tab">Tab 1</div>
<div role="tabpanel">Content for Tab 1</div>

// 올바른 예시
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" tabindex="-1">Tab 2</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>

// (권장) 시멘틱 요소 사용
<div role="tablist">
  <button role="tab" id="tab1" aria-selected="true" aria-controls="panel1">Tab 1</button>
  <button role="tab" id="tab2" aria-selected="false" aria-controls="panel2">Tab 2</button>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>
```

**동적으로 업데이트 가능한 tab 예시**
이 예시는 탭을 동적으로 업데이트할 수 있는 기능을 구현한 것입니다. 사용자가 탭을 클릭하면, 이전에 선택된 탭은 비활성화되고 새 탭이 활성화됩니다. 보조 기술은 현재 선택된 탭과 그에 따른 콘텐츠를 정확히 전달받습니다. 
```sh
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" tabindex="-1">Tab 2</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>

<script>
  const tabs = document.querySelectorAll('[role="tab"]');
  const panels = document.querySelectorAll('[role="tabpanel"]');

  tabs.forEach(tab => {
    tab.addEventListener('click', () => {
      tabs.forEach(t => {
        t.setAttribute('aria-selected', 'false');
        t.setAttribute('tabindex', '-1');
      });
      panels.forEach(p => p.hidden = true);

      tab.setAttribute('aria-selected', 'true');
      tab.setAttribute('tabindex', '0');
      document.getElementById(tab.getAttribute('aria-controls')).hidden = false;
    });
  });
</script>
```

**비활성화된 tab 예시**
aria-disabled="true" 속성을 사용하여 비활성화된 탭을 나타냈습니다. 이 탭은 포커스를 받을 수 없으며(tabindex="-1"), 시각적으로도 비활성화된 상태임을 표시했습니다.  
```sh
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" aria-disabled="true" tabindex="-1" style="color: grey;">Tab 2</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>
```

**키보드 내비게이션을 지원하는 tab 예시**
이 예시는 키보드 내비게이션을 지원하는 탭 인터페이스를 구현한 것입니다. 사용자는 ArrowRight 및 ArrowLeft 키를 사용하여 탭 간에 이동할 수 있으며, 탭의 선택이 자동으로 업데이트됩니다.  
```sh
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" tabindex="-1">Tab 2</div>
  <div role="tab" id="tab3" aria-selected="false" aria-controls="panel3" tabindex="-1">Tab 3</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>
<div role="tabpanel" id="panel3" aria-labelledby="tab3" hidden>Content for Tab 3</div>

<script>
  const tabElements = document.querySelectorAll('[role="tab"]');

  tabElements.forEach((tab, index) => {
    tab.addEventListener('keydown', (event) => {
      let newIndex;
      if (event.key === 'ArrowRight') {
        newIndex = (index + 1) % tabElements.length;
      } else if (event.key === 'ArrowLeft') {
        newIndex = (index - 1 + tabElements.length) % tabElements.length;
      } else {
        return;
      }
      tabElements[newIndex].focus();
      tabElements[newIndex].click();
    });
  });
</script>
```

### **18. tabpanel (탭 패널 역할)**    
tabpanel 역할은 탭 인터페이스에서 개별 탭(tab)과 연결된 콘텐츠 영역을 나타냅니다. 사용자가 특정 탭을 선택하면 해당 tabpanel이 활성화되며, 사용자는 탭과 관련된 콘텐츠를 볼 수 있습니다. tabpanel은 tablist 내의 tab과 함께 사용되며, 각 tab 요소는 aria-controls 속성을 통해 자신이 제어하는 tabpanel을 가리킵니다.    
[W3C ARIA tabpanel](https://www.w3.org/TR/wai-aria-1.2/#tabpanel){: target="_blank"}   
[MDN ARIA tabpanel](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tabpanel_role){: target="_blank"}   

**기본 설명** 
- tab 역할은 탭 인터페이스에서 개별 탭을 정의합니다.    
- 사용자는 클릭하거나 키보드를 사용해 탭을 탐색하고 선택할 수 있습니다.   
- aria-selected 속성을 사용하여 현재 선택된 탭을 나타내며, aria-controls 속성으로 해당 탭이 제어하는 tabpanel을 지정합니다.    
- 탭은 일반적으로 tablist 컨테이너 안에 포함되며, 선택된 탭에 따라 관련 콘텐츠(tabpanel)가 표시됩니다.    

**사용 시 주의사항**   
- tab 역할을 사용할 때는 반드시 aria-selected 속성을 설정하여 현재 선택된 탭을 명확히 표시해야 합니다. 값은 true(선택됨) 또는 false(선택되지 않음)입니다.   
- 각 tab 요소는 aria-controls 속성을 사용하여 제어하는 tabpanel을 지정해야 합니다. 이 속성은 tabpanel의 ID와 연결되어야 합니다.
- tabpanel은 tab과 연결되어야 하며, 탭이 선택될 때 해당 tabpanel만 표시되고 나머지는 숨겨져야 합니다.
- 비활성화된 탭은 aria-disabled="true" 속성을 사용하여 표시하며, 시각적으로도 이를 나타내야 합니다.
- 키보드 내비게이션을 지원하도록 구현하여 사용자가 탭을 쉽게 탐색할 수 있도록 해야 합니다.

**상속된 상태 및 속성**   
- aria-selected: 현재 탭의 선택 상태를 나타냅니다. 값은 true(선택됨) 또는 false(선택되지 않음)입니다.    
- aria-controls: 탭이 제어하는 tabpanel의 ID를 참조합니다.    
- aria-disabled: 탭이 비활성화되었는지 여부를 나타냅니다.    



**기본 tab 역할 예시**
시멘틱 요소 사용을 권장하며, &lt;button&gt; 요소를 사용하여 탭을 구현. 탭 버튼과 관련 콘텐츠가 올바르게 연결되어 보조 기술이 이 구조를 정확히 이해할 수 있도록 합니다.   
tab과 tabpanel을 올바르게 연결한 것입니다. aria-controls 속성을 사용해 각 tab이 제어하는 tabpanel을 명시했고, aria-selected 속성으로 현재 선택된 탭을 나타냈습니다. 선택되지 않은 탭은 tabindex="-1"을 사용해 포커스가 불가능하도록 설정되었습니다.    

```sh
// 잘못된 예시 - tab과 tabpanel이 연결되지 않았고, aria-selected 및 aria-controls 속성 누락.
<div role="tab">Tab 1</div>
<div role="tabpanel">Content for Tab 1</div>

// 올바른 예시
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" tabindex="-1">Tab 2</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>

// (권장) 시멘틱 요소 사용
<div role="tablist">
  <button role="tab" id="tab1" aria-selected="true" aria-controls="panel1">Tab 1</button>
  <button role="tab" id="tab2" aria-selected="false" aria-controls="panel2">Tab 2</button>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>
```

**동적으로 업데이트 가능한 tab 예시**
이 예시는 탭을 동적으로 업데이트할 수 있는 기능을 구현한 것입니다. 사용자가 탭을 클릭하면, 이전에 선택된 탭은 비활성화되고 새 탭이 활성화됩니다. 보조 기술은 현재 선택된 탭과 그에 따른 콘텐츠를 정확히 전달받습니다. 
```sh
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" tabindex="-1">Tab 2</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>

<script>
  const tabs = document.querySelectorAll('[role="tab"]');
  const panels = document.querySelectorAll('[role="tabpanel"]');

  tabs.forEach(tab => {
    tab.addEventListener('click', () => {
      tabs.forEach(t => {
        t.setAttribute('aria-selected', 'false');
        t.setAttribute('tabindex', '-1');
      });
      panels.forEach(p => p.hidden = true);

      tab.setAttribute('aria-selected', 'true');
      tab.setAttribute('tabindex', '0');
      document.getElementById(tab.getAttribute('aria-controls')).hidden = false;
    });
  });
</script>
```

**비활성화된 tab 예시**
aria-disabled="true" 속성을 사용하여 비활성화된 탭을 나타냈습니다. 이 탭은 포커스를 받을 수 없으며(tabindex="-1"), 시각적으로도 비활성화된 상태임을 표시했습니다.  
```sh
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" aria-disabled="true" tabindex="-1" style="color: grey;">Tab 2</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>
```

**키보드 내비게이션을 지원하는 tab 예시**
이 예시는 키보드 내비게이션을 지원하는 탭 인터페이스를 구현한 것입니다. 사용자는 ArrowRight 및 ArrowLeft 키를 사용하여 탭 간에 이동할 수 있으며, 탭의 선택이 자동으로 업데이트됩니다.  
```sh
<div role="tablist">
  <div role="tab" id="tab1" aria-selected="true" aria-controls="panel1" tabindex="0">Tab 1</div>
  <div role="tab" id="tab2" aria-selected="false" aria-controls="panel2" tabindex="-1">Tab 2</div>
  <div role="tab" id="tab3" aria-selected="false" aria-controls="panel3" tabindex="-1">Tab 3</div>
</div>
<div role="tabpanel" id="panel1" aria-labelledby="tab1">Content for Tab 1</div>
<div role="tabpanel" id="panel2" aria-labelledby="tab2" hidden>Content for Tab 2</div>
<div role="tabpanel" id="panel3" aria-labelledby="tab3" hidden>Content for Tab 3</div>

<script>
  const tabElements = document.querySelectorAll('[role="tab"]');

  tabElements.forEach((tab, index) => {
    tab.addEventListener('keydown', (event) => {
      let newIndex;
      if (event.key === 'ArrowRight') {
        newIndex = (index + 1) % tabElements.length;
      } else if (event.key === 'ArrowLeft') {
        newIndex = (index - 1 + tabElements.length) % tabElements.length;
      } else {
        return;
      }
      tabElements[newIndex].focus();
      tabElements[newIndex].click();
    });
  });
</script>
```




---

**복합형(Composite) Widget Roles**






다음 역할은 독립형 사용자 인터페이스 위젯 또는 더 큰 복합 위젯의 일부로 작동합니다.
button, checkbox, radio, gridcell, link, menuitem, menuitemcheckbox, menuitemradio, option, progressbar, scrollbar, searchbox, separator (when focusable), slider, spinbutton, switch, tab, tabpanel, textbox, treeitem

다음 역할은 복합 사용자 인터페이스 위젯 역할을 합니다. 이러한 역할은 일반적으로 포함된 다른 위젯을 관리하는 컨테이너 역할을 합니다.
combobox, grid, listbox, menu, menubar, radiogroup, tablist, tree, treegrid

## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  