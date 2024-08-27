# WAI-ARIA 상태 및 속성
> WAI-ARIA 상태 및 속성은 웹 애플리케이션의 접근성을 향상시키기 위해 HTML 요소에 추가적인 의미와 기능을 부여하는 메커니즘입니다. 이 섹션에서는 다양한 WAI-ARIA 속성과 상태를 설명하고, 이를 위젯, 라이브 리전, 드래그 앤 드롭, 관계 관련 기능에 적용하는 방법을 다룹니다.    
이 속성과 상태들은 WAI-ARIA가 웹 애플리케이션의 접근성을 강화하기 위해 제공하는 중요한 도구입니다. 이들을 적절하게 사용하면 시각적 장애를 가진 사용자도 웹 콘텐츠와 상호작용할 수 있으며, 동적인 콘텐츠 변경 사항을 쉽게 인지할 수 있습니다. 이를 통해 웹 접근성을 크게 개선할 수 있습니다.   

## Drag-and-Drop Attributes (드래그 앤 드롭 속성)
> WAI-ARIA (Web Accessibility Initiative - Accessible Rich Internet Applications)에서 정의한 Drag-and-Drop 속성은 사용자가 마우스나 터치를 사용하지 않고도 드래그 앤 드롭 기능을 활용할 수 있도록 돕습니다. 특히, 보조 기술을 사용하는 사용자에게 현재 인터페이스에서 발생하는 드래그 앤 드롭과 관련된 상태와 피드백을 제공하여 접근성을 크게 향상시킵니다.   
[W3C ARIA Drag-and-Drop Attributes](https://www.w3.org/TR/wai-aria-1.2/#attrs_dragdrop){: target="_blank"}   
[MDN: ARIA Drag & drop attributes](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#drag_drop_attributes){: target="_blank"}   

### **1. aria-dropeffect (property) - (deprecated)**    
aria-dropeffect 속성은 WAI-ARIA(WAI-Accessible Rich Internet Applications)에서 정의된 속성 중 하나로, 드래그 앤 드롭 인터페이스에서 사용자가 드래그 가능한 객체가 특정 드롭 영역에 놓였을 때 어떤 효과가 발생할지를 나타냅니다. 그러나, **WAI-ARIA 1.2에서는 aria-dropeffect 속성이 더 이상 사용되지 않는 것으로 권장**됩니다. 대신, HTML5의 네이티브 드래그 앤 드롭 이벤트와 속성을 사용하여 접근성을 관리하는 것이 좋습니다.   
[WAI-ARIA 1.2 Specification (aria-dropeffect)](https://www.w3.org/TR/wai-aria-1.2/#aria-dropeffect){: target="_blank"}   
[MDN Web Docs (aria-dropeffect)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-dropeffect){: target="_blank"}   

**aria-dropeffect 속성 값**  
WAI-ARIA 1.2에서는 aria-dropeffect 속성의 사용이 권장되지 않지만, 이 속성은 여전히 다음과 같은 값들을 가질 수 있습니다.   
- **copy**: 드래그된 객체가 드롭되면 원본 객체가 복사됩니다.   
- **move**: 드래그된 객체가 드롭되면 원본 객체가 이동됩니다.   
- **link**: 드래그된 객체가 드롭되면 원본 객체에 대한 링크가 생성됩니다.   
- **execute**: 드래그된 객체가 드롭되면 실행 액션이 발생합니다.   
- **popup**: 드래그된 객체가 드롭되면 새 창이나 팝업이 생성됩니다.   
- **none**: 드롭 효과가 발생하지 않음을 명시합니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, p, li, ul, section, article 등 대부분의 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: 드롭 가능한 요소에 대해 사용될 수 있으며, group, region, listbox, grid, tree, tabpanel 등의 역할과 함께 사용할 수 있습니다.    

**사용 시 주의사항**   
- **더 이상 권장되지 않음**: aria-dropeffect는 WAI-ARIA 1.2에서 사용을 피하는 것이 좋습니다. HTML5의 드래그 앤 드롭 API와 같은 네이티브 기능을 사용하는 것이 권장됩니다.   
- **최신 접근성 표준 준수**: 최신 접근성 표준에 맞춰 드래그 앤 드롭 인터페이스를 설계하고, 가능한 경우 키보드 지원을 포함하는 것이 중요합니다.    


**잘못된 예시**      
WAI-ARIA 1.2에서는 aria-dropeffect의 사용이 권장되지 않으므로, 이 속성을 사용하지 않는 것이 좋습니다.    
```sh
<div id="dropzone" aria-dropeffect="move">
  드롭 가능한 영역입니다.
</div>
<script>
  // 이 예시는 aria-dropeffect 사용을 보여주지만, 현대 접근성 표준에 맞지 않습니다.
  document.getElementById('dropzone').addEventListener('dragover', (event) => {
    event.preventDefault();
  });
  document.getElementById('dropzone').addEventListener('drop', (event) => {
    event.preventDefault();
    console.log('Object moved');
  });
</script>
```

**올바른 예시**      
이 예시에서는 aria-dropeffect 대신 HTML5의 네이티브 이벤트와 ARIA 역할 및 속성(role="region", aria-label)을 사용하여 접근성을 유지합니다.    
```sh
<div id="dropzone" role="region" aria-label="드롭 가능한 영역" ondragover="event.preventDefault()">
  드래그 앤 드롭을 사용해 파일을 여기에 업로드하세요.
</div>
<script>
  document.getElementById('dropzone').addEventListener('drop', (event) => {
    event.preventDefault();
    console.log('File dropped');
  });
</script>
```

**파일을 복사하는 드롭 효과 구현 예시**    
```sh
<div id="copyzone" role="region" aria-label="복사할 수 있는 드롭 영역" ondragover="event.preventDefault()">
  파일을 여기에 드롭하여 복사하세요.
</div>
<script>
  document.getElementById('copyzone').addEventListener('drop', (event) => {
    event.preventDefault();
    console.log('File copied');
  });
</script>
```

**링크를 생성하는 드롭 효과 구현 예시**    
```sh
<div id="linkzone" role="region" aria-label="링크 생성 가능한 드롭 영역" ondragover="event.preventDefault()">
  링크를 생성하려면 여기에 드롭하세요.
</div>
<script>
  document.getElementById('linkzone').addEventListener('drop', (event) => {
    event.preventDefault();
    console.log('Link created');
  });
</script>
```

**시멘틱 구조의 예시**    
이 구조는 접근성을 높이기 위해 HTML5 드래그 앤 드롭 API와 ARIA 속성을 사용하여 파일 드롭 영역을 구현한 예시입니다. aria-dropeffect 대신 최신 접근성 표준을 따릅니다.   
```sh
<section role="region" aria-labelledby="drop-title">
  <h2 id="drop-title">파일 드롭 영역</h2>
  <div id="dropzone" ondragover="event.preventDefault()" aria-label="여기에 파일을 드롭하세요">
    드래그 앤 드롭으로 파일을 업로드하세요.
  </div>
</section>
<script>
  document.getElementById('dropzone').addEventListener('drop', (event) => {
    event.preventDefault();
    console.log('File dropped');
  });
</script>
```

### **2. aria-grabbed (state) - (deprecated)**    
aria-grabbed 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 정의된 속성 중 하나로, 드래그 앤 드롭 인터페이스에서 사용자가 특정 요소를 "잡았는지"(즉, 드래그 중인지) 여부를 나타냅니다. 이 속성은 주로 스크린 리더 사용자에게 현재 요소가 드래그되고 있는 상태임을 알리는 데 사용됩니다. 그러나, **WAI-ARIA 1.2에서는 aria-grabbed 속성이 더 이상 권장되지 않습니다.** 대신, HTML5 네이티브 드래그 앤 드롭 이벤트를 사용하는 것이 권장됩니다.   
[WAI-ARIA 1.2 Specification (aria-grabbed)](https://www.w3.org/TR/wai-aria-1.2/#aria-grabbed){: target="_blank"}   
[MDN Web Docs (aria-grabbed)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-grabbed){: target="_blank"}   

**aria-grabbed 속성 값**  
- **true**: 요소가 현재 사용자가 "잡은"(드래그 중인) 상태임을 나타냅니다.   
- **false**: 요소가 현재 "잡히지 않은"(드래그되지 않은) 상태임을 나타냅니다.   
- **undefined**: aria-grabbed 속성이 없으면, 기본적으로 요소가 드래그되지 않은 상태로 간주됩니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, li, img, p, section, article 등 대부분의 HTML 요소에서 사용 가능.   
- **연관된 역할**: 드래그 가능한 요소와 관련하여 사용할 수 있으며, listitem, treeitem, gridcell, row, option 등의 역할과 함께 사용할 수 있습니다.    

**사용 시 주의사항**   
- **더 이상 권장되지 않음**: aria-grabbed는 WAI-ARIA 1.2에서 사용을 피하는 것이 좋습니다. HTML5의 드래그 앤 드롭 API와 같은 네이티브 기능을 사용하는 것이 권장됩니다.   
- **대체 방법**: HTML5의 draggable 속성과 드래그 이벤트(dragstart, dragend 등)를 사용하여 드래그 상태를 처리하는 것이 더 나은 접근성 표준을 준수하는 방법입니다.    


**잘못된 예시**      
WAI-ARIA 1.2에서 더 이상 aria-grabbed의 사용이 권장되지 않습니다. 대신 최신 HTML5 드래그 앤 드롭 API를 사용해야 합니다.    
```sh
<div id="draggable-item" aria-grabbed="true">
  이 항목을 드래그 중입니다.
</div>
<script>
  document.getElementById('draggable-item').addEventListener('dragend', () => {
    document.getElementById('draggable-item').setAttribute('aria-grabbed', 'false');
  });
</script>
```

**올바른 예시**      
이 예시에서는 aria-grabbed를 사용하지 않고 HTML5의 네이티브 드래그 앤 드롭 이벤트를 사용하여 드래그 상태를 관리합니다.    
```sh
<div id="draggable-item" draggable="true" aria-label="드래그 가능한 항목">
  이 항목을 드래그하세요.
</div>
<div id="dropzone" aria-label="드롭 가능한 영역" ondragover="event.preventDefault()">
  여기에 드롭하세요.
</div>
<script>
  const draggableItem = document.getElementById('draggable-item');
  draggableItem.addEventListener('dragstart', () => {
    draggableItem.setAttribute('aria-grabbed', 'true');
  });
  draggableItem.addEventListener('dragend', () => {
    draggableItem.setAttribute('aria-grabbed', 'false');
  });
  document.getElementById('dropzone').addEventListener('drop', (event) => {
    event.preventDefault();
    console.log('Item dropped');
  });
</script>
```

**드래그 상태를 나타내는 예시 (deprecated)**    
WAI-ARIA 1.2에서는 이 방법이 더 이상 권장되지 않습니다.   
```sh
<div id="item" aria-grabbed="true">
  이 항목은 드래그 중입니다.
</div>
<script>
  document.getElementById('item').addEventListener('dragend', () => {
    document.getElementById('item').setAttribute('aria-grabbed', 'false');
  });
</script>
```

**HTML5 드래그 앤 드롭을 사용한 드래그 상태 관리 예시**    
이 예시는 최신 접근성을 고려한 구현 방법을 보여줍니다.   
```sh
<div id="draggable" draggable="true" aria-label="드래그 가능한 항목">
  이 항목을 드래그하세요.
</div>
<script>
  const draggable = document.getElementById('draggable');
  draggable.addEventListener('dragstart', () => {
    draggable.setAttribute('aria-grabbed', 'true');
  });
  draggable.addEventListener('dragend', () => {
    draggable.setAttribute('aria-grabbed', 'false');
  });
</script>
```

**시멘틱 구조의 예시**    
이 예시는 접근성을 고려한 드래그 앤 드롭 인터페이스를 구현하는 예시로, aria-grabbed 대신 HTML5 네이티브 드래그 앤 드롭 API를 사용합니다.   
```sh
<section role="region" aria-labelledby="drag-drop-section">
  <h2 id="drag-drop-section">드래그 앤 드롭 영역</h2>
  <div id="draggable" draggable="true" aria-label="드래그 가능한 항목">
    드래그하여 이동할 항목
  </div>
  <div id="dropzone" aria-label="드롭 가능한 영역" ondragover="event.preventDefault()">
    여기에 드롭하세요.
  </div>
</section>
<script>
  const draggable = document.getElementById('draggable');
  draggable.addEventListener('dragstart', () => {
    draggable.setAttribute('aria-grabbed', 'true');
  });
  draggable.addEventListener('dragend', () => {
    draggable.setAttribute('aria-grabbed', 'false');
  });
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
  