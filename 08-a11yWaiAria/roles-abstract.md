# WAI-ARIA 역할

## Abstract Roles (추상적 역할)
> **Abstract Roles**은 다른 역할을 정의하는 데 사용되는 개념적 역할입니다. 이러한 역할들은 웹 페이지에 직접 사용되지 않으며, 구체적인 역할을 정의하고 이들 간의 관계를 설명하고,        
웹 접근성을 높이는 데 중요한 역할을 합니다. 올바르게 이해하고 사용하여 웹 콘텐츠의 접근성을 개선할 수 있습니다.

### **1. command (명령 역할)**    
사용자 명령을 나타내는 역할의 상위 개념입니다. 이 역할을 통해 사용자가 상호작용할 수 있는 다양한 UI 요소를 정의합니다. command 역할 자체는 직접 사용되지 않으며, button, link, menuitem 등의 구체적인 역할이 이 역할에서 파생됩니다.   
[W3C ARIA command](https://www.w3.org/TR/wai-aria-1.2/#command){: target="_blank"}   
[MDN ARIA command](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/command_role){: target="_blank"}   

```sh
// 잘못된 예시 - 'command'는 직접 사용되지 않음
<div role="command">Click me</div>

// 올바른 예시 - button은 command에서 파생된 역할
<div role="button">Click me</div> 

// (권장)시맨틱 마크업과의 비교 - HTML5의 시맨틱 요소를 사용하여 button 역할을 암시적으로 정의
<button type="button">Click me</button>
```
**사용 시 주의사항**   
- command는 직접 사용되지 않으며, 이를 상속하는 구체적인 역할(button, link 등)을 사용해야 합니다.   
- 명령 요소는 사용자에게 명확히 전달되도록 aria-label 또는 aria-labelledby 속성을 사용할 수 있습니다.   

**상속된 상태 및 속성**   
- aria-disabled: 요소가 비활성화되었는지 여부를 나타냅니다.   
- aria-expanded: 요소가 확장되었는지 여부를 나타냅니다.    

### **2. composite (복합 역할)**    
composite 역할은 여러 개의 상호작용 가능한 위젯을 포함하는 복합 위젯을 정의하는 상위 개념입니다. combobox, grid, tablist, tree 등이 이 역할을 상속받습니다.   
[W3C ARIA composite](https://www.w3.org/TR/wai-aria-1.2/#composite){: target="_blank"}   
[MDN ARIA composite](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/composite_role){: target="_blank"}   

```sh
// 잘못된 예시 - composite는 직접 사용되지 않음
<div role="composite">Items</div>

// 올바른 예시
<div role="tablist">
  <div role="tab" aria-selected="true">Tab 1</div>
  <div role="tab" aria-selected="false">Tab 2</div>
</div>

// (권장)시맨틱 마크업과의 비교 - 시맨틱 마크업만으로는 복합 위젯을 정의하기 어려움
<div>
  <button type="button">Tab 1</button>
  <button type="button">Tab 2</button>
</div>
```
**사용 시 주의사항**   
- composite는 직접 사용되지 않고, 구체적인 복합 위젯 역할을 사용해야 합니다.   
- 복합 위젯 내의 자식 요소는 명확하게 정의되고 접근 가능해야 합니다.   

**상속된 상태 및 속성**   
- aria-activedescendant: 복합 위젯 내에서 현재 활성화된 자식 요소의 ID를 지정합니다.   
- aria-disabled: 요소가 비활성화되었는지 여부를 나타냅니다.   
- aria-expanded: 요소가 확장되었는지 여부를 나타냅니다.   


### **3. input (입력 역할)**    
input 역할은 사용자가 입력할 수 있는 요소를 정의하는 상위 개념입니다. checkbox, radio, slider, spinbutton, textbox 등이 이 역할을 상속받습니다.   
[W3C ARIA input](https://www.w3.org/TR/wai-aria-1.2/#input){: target="_blank"}   
[MDN ARIA input](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/input_role){: target="_blank"}   

```sh
// 잘못된 예시 - input는 직접 사용되지 않음
<div role="input">Enter text</div>

// 올바른 예시
<input role="textbox" type="text" aria-label="Enter text">

// (권장)시맨틱 마크업과의 비교 - HTML5 시맨틱 요소 사용
<input type="text" aria-label="Enter text">
```
**사용 시 주의사항**   
- input 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 입력 역할을 사용해야 합니다.   
- 사용자는 입력 필드의 상태(예: 필수, 읽기 전용, 비활성화)를 명확히 알 수 있어야 합니다.   

**상속된 상태 및 속성**   
- aria-required: 필드가 필수인지 여부를 나타냅니다.   
- aria-readonly: 필드가 읽기 전용인지 여부를 나타냅니다.   
- aria-disabled: 요소가 비활성화되었는지 여부를 나타냅니다.   


### **4. landmark (랜드마크 역할)**    
landmark 역할은 웹 페이지의 주요 섹션을 정의하는 상위 개념입니다. banner, navigation, main, contentinfo 등에서 파생됩니다.   
[W3C ARIA landmark](https://www.w3.org/TR/wai-aria-1.2/#landmark){: target="_blank"}   
[MDN ARIA landmark](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/landmark_role){: target="_blank"}   

```sh
// 잘못된 예시 - landmark는 직접 사용되지 않음
<div role="landmark">Main Content</div>

// 올바른 예시
<div role="main">
  <h1>Main Content</h1>
  <p>This is the main area of the page.</p>
</div>

// (권장)시맨틱 마크업과의 비교 - 시맨틱 요소를 통해 main 역할이 암시됨
<main>
  <h1>Main Content</h1>
  <p>This is the main area of the page.</p>
</main>
```
**사용 시 주의사항**   
- landmark 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 랜드마크 역할을 사용해야 합니다.   
- 각 랜드마크 역할은 페이지 내에서 고유한 역할을 가지며, 중복되지 않도록 주의해야 합니다.   

**상속된 상태 및 속성**   
- aria-label: 요소의 레이블을 제공하여 사용자에게 명확한 정보를 전달합니다.   
- aria-labelledby: 요소를 레이블링하는 다른 요소의 ID를 지정합니다.   


### **5. range (범위 역할)**    
range 역할은 특정 범위 내에서 값을 설정하거나 선택할 수 있는 위젯을 정의하는 상위 개념입니다. progressbar, slider, spinbutton 등에서 파생됩니다.   
[W3C ARIA range](https://www.w3.org/TR/wai-aria-1.2/#range){: target="_blank"}   
[MDN ARIA range](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/range_role){: target="_blank"}   

```sh
// 잘못된 예시 - range는 직접 사용되지 않음
<div role="range">50</div>

// 올바른 예시
<div role="slider" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" tabindex="0"></div>

// (권장)시맨틱 마크업과의 비교 - HTML5의 range 요소
<input type="range" min="0" max="100" value="50">
```
**사용 시 주의사항**   
- range 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 역할을 사용해야 합니다.   
- 사용자는 현재 값과 범위를 명확히 이해할 수 있어야 하며, 필요한 경우 aria-valuetext를 사용하여 설명을 제공합니다.   

**상속된 상태 및 속성**   
- aria-valuemin: 값의 최소 범위를 지정합니다.       
- aria-valuemax: 값의 최대 범위를 지정합니다.    
- aria-valuenow: 현재 값을 지정합니다.    
- aria-valuetext: 현재 값을 텍스트로 표현할 수 있도록 합니다.    


### **6. roletype (역할 유형)**    
roletype은 모든 WAI-ARIA 역할의 최상위 추상적 역할로, 다른 모든 역할이 이 역할에서 파생됩니다.   
[W3C ARIA roletype](https://www.w3.org/TR/wai-aria-1.2/#roletype){: target="_blank"}   
[MDN ARIA roletype](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/roletype_role){: target="_blank"}   

```sh
'roletype'은 다른 역할을 정의하는 데 사용되므로 직접 사용되지 않음

// 잘못된 예시 - roletype은 직접 사용되지 않음
<div role="roletype">Item</div>

// 권장사항 - 사용하지 마십시오.
```
**사용 시 주의사항**   
- roletype은 직접 사용되지 않고, 구체적인 역할에서만 상속되어 사용됩니다.   
- 적절한 aria 속성을 사용하여 역할이 명확히 전달되도록 해야 합니다.   

**상속된 상태 및 속성**   
- aria-atomic: 변경 시 전체 영역을 다시 읽어야 하는지 여부를 지정합니다.       
- aria-busy: 요소가 현재 작업 중인지 여부를 나타냅니다.    
- aria-controls: 이 요소가 제어하는 다른 요소의 ID를 지정합니다.    
- aria-describedby: 이 요소를 설명하는 다른 요소의 ID를 지정합니다.    


### **7. section (섹션 역할)**    
section 역할은 문서의 주제별 섹션을 정의하는 상위 개념입니다. region, alert, log, status 등이 이 역할을 상속받습니다.   
[W3C ARIA section](https://www.w3.org/TR/wai-aria-1.2/#section){: target="_blank"}   
[MDN ARIA section](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/section_role){: target="_blank"}   

```sh
// 잘못된 예시 - section은 직접 사용되지 않음
<div role="section">Section Content</div>

// 올바른 예시
<div role="region" aria-labelledby="section-title">
  <h2 id="section-title">Section Title</h2>
  <p>This is a section of the document.</p>
</div>

// (권장)시맨틱 마크업과의 비교 - HTML5의 section 요소
<section aria-labelledby="section-title">
  <h2 id="section-title">Section Title</h2>
  <p>This is a section of the document.</p>
</section>
```
**사용 시 주의사항**   
- section 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 섹션 역할을 사용해야 합니다.   
- 각 섹션은 명확히 구분되고, 적절한 레이블과 설명이 제공되어야 합니다.   

**상속된 상태 및 속성**   
- aria-labelledby: 이 섹션을 레이블링하는 다른 요소의 ID를 지정합니다.    
- aria-describedby: 이 섹션을 설명하는 다른 요소의 ID를 지정합니다.    


### **8. sectionhead (섹션 헤더 역할)**    
sectionhead 역할은 문서 내 섹션의 제목을 나타내는 역할입니다. heading, tab, columnheader, rowheader 등이 이 역할을 상속받습니다.   
[W3C ARIA sectionhead](https://www.w3.org/TR/wai-aria-1.2/#sectionhead){: target="_blank"}   
[MDN ARIA sectionhead](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/sectionhead_role){: target="_blank"}   

```sh
// 잘못된 예시 - sectionhead는 직접 사용되지 않음
<div role="sectionhead">Section Title</div>

// 올바른 예시
<div role="heading" aria-level="2">Section Title</div>

// (권장)시맨틱 마크업과의 비교 - HTML5의 heading 요소
<h2>Section Title</h2>
```
**사용 시 주의사항**   
- sectionhead 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 역할을 사용해야 합니다.   
- 문서 구조와 일치하는 헤더 계층이 중요하며, aria-level 속성을 사용하여 정의합니다.   

**상속된 상태 및 속성**   
- aria-level: 섹션 헤더의 계층적 수준을 지정합니다.    


### **9. select (선택 역할)**    
select 역할은 사용자가 옵션을 선택할 수 있는 위젯을 정의하는 상위 개념입니다. combobox, listbox, menu, radiogroup 등이 이 역할을 상속받습니다.   
[W3C ARIA select](https://www.w3.org/TR/wai-aria-1.2/#select){: target="_blank"}   
[MDN ARIA select](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/select_role){: target="_blank"}   

```sh
// 잘못된 예시 - select는 직접 사용되지 않음
<div role="select">Option 1</div>

// 올바른 예시
<ul role="listbox" aria-multiselectable="true">
  <li role="option">Option 1</li>
  <li role="option">Option 2</li>
</ul>

// (권장)시맨틱 마크업과의 비교 - HTML5의 select 요소
<select>
  <option>Option 1</option>
  <option>Option 2</option>
</select>
```
**사용 시 주의사항**   
- select 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 선택 위젯 역할을 사용해야 합니다.   
- 사용자는 선택 가능한 옵션의 수와 상태를 명확히 이해할 수 있어야 합니다.   

**상속된 상태 및 속성**   
- aria-multiselectable: 사용자가 여러 항목을 선택할 수 있는지 여부를 지정합니다.    
- aria-required: 선택이 필수인지 여부를 지정합니다.    


### **10. structure (구조 역할)**    
structure 역할은 문서의 구조를 정의하는 상위 개념입니다. document, article, section, group, heading 등이 이 역할을 상속받습니다.  
[W3C ARIA structure](https://www.w3.org/TR/wai-aria-1.2/#structure){: target="_blank"}   
[MDN ARIA structure](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/structure_role){: target="_blank"}   

```sh
// 잘못된 예시 - structure는 직접 사용되지 않음
<div role="structure">Document Structure</div>

// 올바른 예시
<div role="article">
  <h2>Article Title</h2>
  <p>This is an article content.</p>
</div>

// (권장)시맨틱 마크업과의 비교 - HTML5의 article 요소
<article>
  <h2>Article Title</h2>
  <p>This is an article content.</p>
</article>
```
**사용 시 주의사항**   
- structure 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 구조 역할을 사용해야 합니다.   
- 문서 구조의 일관성을 유지하고, 사용자에게 명확한 내비게이션을 제공해야 합니다.   

**상속된 상태 및 속성**   
- aria-labelledby: 이 구조를 레이블링하는 다른 요소의 ID를 지정합니다.    
- aria-describedby: 이 구조를 설명하는 다른 요소의 ID를 지정합니다.    


### **11. widget (위젯 역할)**    
widget 역할은 사용자가 상호작용할 수 있는 UI 요소를 정의하는 상위 개념입니다. button, checkbox, slider, link, textbox 등이 이 역할을 상속받습니다.   
[W3C ARIA widget](https://www.w3.org/TR/wai-aria-1.2/#widget){: target="_blank"}   
[MDN ARIA widget](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/widget_role){: target="_blank"}   

```sh
// 잘못된 예시 - widget은 직접 사용되지 않음
<div role="widget">Interactive Element</div>

// 올바른 예시
<div role="button" aria-disabled="true">Click me</div>

// (권장)시맨틱 마크업과의 비교 - HTML5의 button 요소
<button type="button">Click me</button>
```
**사용 시 주의사항**   
- widget 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 역할을 사용해야 합니다.   
- 상호작용 가능한 위젯은 사용자에게 명확히 전달되고, 키보드 및 보조 기술을 통한 접근성이 보장되어야 합니다.   

**상속된 상태 및 속성**   
- aria-disabled: 요소가 비활성화되었는지 여부를 나타냅니다.    
- aria-expanded: 요소가 확장되었는지 여부를 나타냅니다.    


### **12. window (윈도우 역할)**    
window 역할은 사용자 인터페이스의 창 요소를 정의하는 역할입니다. alertdialog, dialog, tooltip 등이 이 역할을 상속받습니다.   
[W3C ARIA window](https://www.w3.org/TR/wai-aria-1.2/#window){: target="_blank"}   
[MDN ARIA window](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/window_role){: target="_blank"}   

```sh
// 잘못된 예시 - window는 직접 사용되지 않음
<div role="window">Dialog Window</div>

// 올바른 예시- 시맨틱 마크업으로 직접 대응할 수 없는 역할로, ARIA를 사용하여 정의
<div role="dialog" aria-labelledby="dialog-title">
  <h2 id="dialog-title">Settings</h2>
  <p>Adjust your preferences below:</p>
</div>
```
**사용 시 주의사항**   
- window 역할은 직접 사용되지 않으며, 이를 상속하는 구체적인 역할을 사용해야 합니다.  
- 창 요소는 포커스(초점) 관리가 중요하며, 창이 닫힐 때 이전 상태로 포커스(초점)를 반환해야 합니다.   

**상속된 상태 및 속성**   
- aria-modal: 창이 모달 대화 상자인지 여부를 나타냅니다.    
- aria-labelledby: 창을 레이블링하는 다른 요소의 ID를 지정합니다.    
- aria-describedby: 창을 설명하는 다른 요소의 ID를 지정합니다.    



## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  