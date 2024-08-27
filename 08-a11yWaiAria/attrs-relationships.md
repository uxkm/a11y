# WAI-ARIA 상태 및 속성
> WAI-ARIA 상태 및 속성은 웹 애플리케이션의 접근성을 향상시키기 위해 HTML 요소에 추가적인 의미와 기능을 부여하는 메커니즘입니다. 이 섹션에서는 다양한 WAI-ARIA 속성과 상태를 설명하고, 이를 위젯, 라이브 리전, 드래그 앤 드롭, 관계 관련 기능에 적용하는 방법을 다룹니다.    
이 속성과 상태들은 WAI-ARIA가 웹 애플리케이션의 접근성을 강화하기 위해 제공하는 중요한 도구입니다. 이들을 적절하게 사용하면 시각적 장애를 가진 사용자도 웹 콘텐츠와 상호작용할 수 있으며, 동적인 콘텐츠 변경 사항을 쉽게 인지할 수 있습니다. 이를 통해 웹 접근성을 크게 개선할 수 있습니다.   

## Relationship Attributes (관계 속성)
> WAI-ARIA(Accessible Rich Internet Applications)의 관계 속성(Relationship Attributes)은 웹 페이지 내의 요소 간 관계를 명시적으로 정의하여 접근성을 높이는 데 중요한 역할을 합니다. 이 속성들은 스크린 리더와 같은 보조 기술이 웹 콘텐츠를 보다 이해하기 쉽게 만들기 위해 사용됩니다. 관계 속성은 특히 복잡한 웹 애플리케이션에서 요소들 간의 논리적 관계를 명확하게 하는 데 필수적입니다.   
[W3C ARIA Relationship Attributes](https://www.w3.org/TR/wai-aria-1.2/#attrs_relationships){: target="_blank"}   
[MDN: ARIA Relationship attributes](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#relationship_attributes){: target="_blank"}   

**자주 사용하는 Relationship Attributes (관계 속성)**
1. **aria-labelledby**   
    - 이 속성은 하나 이상의 요소를 참조하여 현재 요소의 레이블을 지정합니다. 예를 들어, 어떤 요소가 하나 이상의 제목이나 설명 텍스트를 통해 설명될 때 사용됩니다.   
    - 예시) div aria-labelledby="label1 label2" 여기서 label1, label2는 해당 요소의 ID를 가리키며, 이 요소들은 현재 요소의 레이블 역할을 합니다.   
2. **aria-describedby**   
    - 설명: 이 속성은 사용자가 현재 요소에 대해 추가적인 설명을 제공하는 하나 이상의 요소를 참조하는 데 사용됩니다. 주로 툴팁이나 설명 텍스트 같은 부가 정보를 연결할 때 유용합니다.   
    - 예시) input aria-describedby="desc1" 여기서 desc1은 입력 필드에 대한 추가 설명을 제공하는 요소의 ID입니다.   
3. **aria-controls**   
    - 이 속성은 현재 요소가 조작하는 하나 이상의 요소를 참조합니다. 예를 들어, 버튼이 특정 콘텐츠를 보여주거나 숨길 수 있는 경우 이 속성을 사용해 그 관계를 명확히 할 수 있습니다.   
    - 예시) button aria-controls="section1" 여기서 section1은 버튼이 조작할 수 있는 콘텐츠 영역의 ID입니다.   
   
**사용 시 주의사항**   
1. **적절한 관계 정의**: 관계 속성은 요소 간의 논리적 관계를 명확히 하기 위해 사용됩니다. 잘못된 관계 정의는 사용자를 혼란스럽게 할 수 있으므로, 올바른 참조를 설정하는 것이 중요합니다.   
2. **ID 참조의 유효성**: 모든 참조된 ID는 문서 내에서 고유해야 하며, 참조된 요소가 실제로 존재해야 합니다.   


### **1. aria-labelledby (property)**    
aria-labelledby 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 특정 요소의 레이블(제목)을 다른 요소를 통해 정의할 때 사용됩니다. 이 속성은 보조 기술(예: 스크린 리더)이 요소와 연관된 레이블을 사용자에게 명확하게 전달할 수 있도록 도와줍니다. aria-labelledby 속성은 aria-label 속성과 유사하지만, aria-label이 직접적으로 레이블 텍스트를 제공하는 반면, aria-labelledby는 다른 요소의 콘텐츠를 레이블로 참조합니다.     
[WAI-ARIA 1.2 Specification (aria-labelledby)](https://www.w3.org/TR/wai-aria-1.2/#aria-labelledby){: target="_blank"}   
[MDN Web Docs (aria-labelledby)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby){: target="_blank"}   


**aria-labelledby 속성 값**  
- aria-labelledby의 값은 레이블로 사용할 요소의 id입니다. 하나 이상의 요소를 공백으로 구분하여 나열할 수 있습니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: input, textarea, button, div, section 등 거의 모든 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: textbox, button, img, link 등 다양한 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 참조**: aria-labelledby 속성의 값으로 참조되는 ID는 문서 내에서 고유해야 하며, 실제로 존재하는 요소를 가리켜야 합니다.   
- **문맥에 맞는 레이블**: 참조된 요소의 텍스트는 해당 요소가 설명하려는 대상과 관련성이 있어야 합니다.   
- **보완적 사용**: aria-describedby와 함께 사용하면, 요소의 제목과 추가 설명을 모두 보조 기술에 전달할 수 있습니다.   

   
**폼 필드에서의 사용 예시**      
이 예시에서는 input 요소가 aria-labelledby 속성을 통해 label 요소(username-label ID가 있는 요소)를 참조합니다. 보조 기술은 input 필드의 레이블로 "사용자 이름"을 사용자에게 전달합니다.      
```sh
<label id="username-label" for="username">사용자 이름:</label>
<input type="text" id="username" aria-labelledby="username-label">
```

**그룹화된 요소에서의 사용 예시**      
이 예시에서는 input 필드들이 aria-labelledby 속성을 통해 h2 요소(personal-info-title ID가 있는 요소)를 참조하여, 두 필드 모두 "개인 정보"라는 제목을 레이블로 사용합니다.    
```sh
<div id="personal-info">
  <h2 id="personal-info-title">개인 정보</h2>
  <p>아래에 개인 정보를 입력하세요.</p>
</div>

<input type="text" id="first-name" aria-labelledby="personal-info-title" placeholder="이름">
<input type="text" id="last-name" aria-labelledby="personal-info-title" placeholder="성">
```

**버튼에 대한 설명에서의 사용 예시**      
이 예시에서는 button 요소가 aria-labelledby 속성을 통해 div 요소(save-desc ID가 있는 요소)를 참조합니다. 보조 기술은 버튼의 텍스트와 함께 추가 설명을 사용자에게 전달합니다.    
```sh
<div id="save-desc">현재 페이지에서 작성한 내용을 저장합니다.</div>
<button id="save-button" aria-labelledby="save-desc">저장</button>
```

**이미지에 대한 설명에서의 사용 예시**      
이 예시에서는 div 요소가 role="group"과 함께 사용되며, aria-labelledby 속성을 통해 그룹의 제목을 정의합니다. 보조 기술은 그룹 내의 모든 요소들이 "복합 위젯 제목"이라는 레이블을 공유하고 있음을 전달합니다.    
```sh
<img src="example.jpg" alt="자연 경관" id="landscape-img" aria-labelledby="image-desc">
<div id="image-desc">이 이미지는 저녁 노을이 비치는 산과 호수를 담고 있습니다.</div>
```

**복합 위젯에서의 사용 예시**      
이 예시에서는 div 요소가 role="group"과 함께 사용되며, aria-labelledby 속성을 통해 그룹의 제목을 정의합니다. 보조 기술은 그룹 내의 모든 요소들이 "복합 위젯 제목"이라는 레이블을 공유하고 있음을 전달합니다.    
```sh
<div id="widget-title">복합 위젯 제목</div>
<div role="group" aria-labelledby="widget-title">
  <button>버튼 1</button>
  <button>버튼 2</button>
</div>
```

### **2. aria-labelledby (property)**    
aria-labelledby 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 특정 요소의 레이블(제목)을 다른 요소를 통해 정의할 때 사용됩니다. 이 속성은 보조 기술(예: 스크린 리더)이 요소와 연관된 레이블을 사용자에게 명확하게 전달할 수 있도록 도와줍니다. aria-labelledby 속성은 aria-label 속성과 유사하지만, aria-label이 직접적으로 레이블 텍스트를 제공하는 반면, aria-labelledby는 다른 요소의 콘텐츠를 레이블로 참조합니다.     
[WAI-ARIA 1.2 Specification (aria-labelledby)](https://www.w3.org/TR/wai-aria-1.2/#aria-labelledby){: target="_blank"}   
[MDN Web Docs (aria-labelledby)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby){: target="_blank"}   


**aria-labelledby 속성 값**  
- aria-labelledby의 값은 레이블로 사용할 요소의 id입니다. 하나 이상의 요소를 공백으로 구분하여 나열할 수 있습니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: input, textarea, button, div, section 등 거의 모든 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: textbox, button, img, link 등 다양한 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 참조**: aria-labelledby 속성의 값으로 참조되는 ID는 문서 내에서 고유해야 하며, 실제로 존재하는 요소를 가리켜야 합니다.   
- **문맥에 맞는 레이블**: 참조된 요소의 텍스트는 해당 요소가 설명하려는 대상과 관련성이 있어야 합니다.   
- **보완적 사용**: aria-describedby와 함께 사용하면, 요소의 제목과 추가 설명을 모두 보조 기술에 전달할 수 있습니다.   

   
**폼 필드에서의 사용 예시**      
이 예시에서는 input 요소가 aria-labelledby 속성을 통해 label 요소(username-label ID가 있는 요소)를 참조합니다. 보조 기술은 input 필드의 레이블로 "사용자 이름"을 사용자에게 전달합니다.      
```sh
<label id="username-label" for="username">사용자 이름:</label>
<input type="text" id="username" aria-labelledby="username-label">
```

**그룹화된 요소에서의 사용 예시**      
이 예시에서는 input 필드들이 aria-labelledby 속성을 통해 h2 요소(personal-info-title ID가 있는 요소)를 참조하여, 두 필드 모두 "개인 정보"라는 제목을 레이블로 사용합니다.    
```sh
<div id="personal-info">
  <h2 id="personal-info-title">개인 정보</h2>
  <p>아래에 개인 정보를 입력하세요.</p>
</div>

<input type="text" id="first-name" aria-labelledby="personal-info-title" placeholder="이름">
<input type="text" id="last-name" aria-labelledby="personal-info-title" placeholder="성">
```

**버튼에 대한 설명에서의 사용 예시**      
이 예시에서는 button 요소가 aria-labelledby 속성을 통해 div 요소(save-desc ID가 있는 요소)를 참조합니다. 보조 기술은 버튼의 텍스트와 함께 추가 설명을 사용자에게 전달합니다.    
```sh
<div id="save-desc">현재 페이지에서 작성한 내용을 저장합니다.</div>
<button id="save-button" aria-labelledby="save-desc">저장</button>
```

**이미지에 대한 설명에서의 사용 예시**      
이 예시에서는 div 요소가 role="group"과 함께 사용되며, aria-labelledby 속성을 통해 그룹의 제목을 정의합니다. 보조 기술은 그룹 내의 모든 요소들이 "복합 위젯 제목"이라는 레이블을 공유하고 있음을 전달합니다.    
```sh
<img src="example.jpg" alt="자연 경관" id="landscape-img" aria-labelledby="image-desc">
<div id="image-desc">이 이미지는 저녁 노을이 비치는 산과 호수를 담고 있습니다.</div>
```

**복합 위젯에서의 사용 예시**      
이 예시에서는 div 요소가 role="group"과 함께 사용되며, aria-labelledby 속성을 통해 그룹의 제목을 정의합니다. 보조 기술은 그룹 내의 모든 요소들이 "복합 위젯 제목"이라는 레이블을 공유하고 있음을 전달합니다.    
```sh
<div id="widget-title">복합 위젯 제목</div>
<div role="group" aria-labelledby="widget-title">
  <button>버튼 1</button>
  <button>버튼 2</button>
</div>
```

### **3. aria-controls (property)**    
aria-controls 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 특정 요소가 제어하는 다른 요소의 ID를 참조하는 데 사용됩니다. 이 속성은 주로 동적 콘텐츠(예: 탭 패널, 드롭다운 메뉴, 대화 상자 등)에서 사용되며, 보조 기술(예: 스크린 리더) 사용자에게 현재 요소가 어떤 요소를 제어하고 있는지를 알리는 역할을 합니다. 즉, 요소 간의 제어 관계를 명확히 전달할 수 있으며, 이를 통해 보다 접근성 높은 인터랙티브 웹 콘텐츠를 제공할 수 있습니다.     
[WAI-ARIA 1.2 Specification (aria-controls)](https://www.w3.org/TR/wai-aria-1.2/#aria-controls){: target="_blank"}   
[MDN Web Docs (aria-controls)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-controls){: target="_blank"}   


**aria-controls 속성 값**  
- aria-controls의 값은 제어할 요소의 id 값을 사용합니다. 하나의 요소만 제어할 수도 있고, 여러 요소를 공백으로 구분하여 제어할 수도 있습니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: button, a, div, input, details, summary 등 제어 기능을 수행하는 대부분의 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: tab, button, checkbox, radio, switch, combobox, menuitem 등의 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 참조**: aria-controls 속성의 값은 반드시 유효한 ID여야 하며, 문서 내에서 고유해야 합니다. 잘못된 참조는 보조 기술 사용자에게 혼란을 줄 수 있습니다.   
- **시맨틱 의미**: aria-controls 속성은 보조 기술 사용자에게만 영향을 주므로, 제어되는 요소 간의 시각적 또는 논리적 관계를 명확히 하도록 HTML 구조를 설계해야 합니다.   
- **동작 시나리오**: 이 속성은 주로 JavaScript와 함께 사용되어 인터랙티브한 동작을 구현할 때 유용합니다.    

**사용 시나리오**   
- **모달 대화 상자**: button이 모달 대화 상자를 열 때, aria-controls로 대화 상자의 ID를 참조하여 제어 관계를 명시합니다.   
- **탭 인터페이스**: 탭이 선택되었을 때 해당 탭이 제어하는 패널을 aria-controls로 지정하여 보조 기술이 어떤 콘텐츠가 활성화되는지 알 수 있도록 합니다.   
- **슬라이더**: 슬라이더 컨트롤이 특정 콘텐츠 영역을 업데이트할 때, 해당 영역을 aria-controls로 참조합니다.   

**드롭다운 메뉴에서의 사용 예시**      
이 예시에서는 button 요소가 aria-controls 속성을 통해 ul 요소(드롭다운 메뉴)를 제어하고 있음을 나타냅니다. 드롭다운 메뉴가 열리면 첫 번째 항목에 포커스가 이동하며, 메뉴가 닫히면 버튼으로 포커스가 반환됩니다.      
```sh
<button aria-controls="dropdown-menu" aria-expanded="false" id="menu-button">
  메뉴 열기
</button>
<ul id="dropdown-menu" hidden>
  <li><a href="#" tabindex="0">항목 1</a></li>
  <li><a href="#" tabindex="0">항목 2</a></li>
  <li><a href="#" tabindex="0">항목 3</a></li>
</ul>

<script>
  const button = document.getElementById('menu-button');
  const menu = document.getElementById('dropdown-menu');
  const menuItems = menu.querySelectorAll('a');

  button.addEventListener('click', () => {
    const expanded = button.getAttribute('aria-expanded') === 'true';
    button.setAttribute('aria-expanded', !expanded);
    menu.hidden = expanded;

    if (!expanded) {
      menuItems[0].focus(); // 첫 번째 항목에 포커스 설정
    } else {
      button.focus(); // 버튼으로 포커스 반환
    }
  });

  // ESC 키로 메뉴 닫기
  menu.addEventListener('keydown', (event) => {
    if (event.key === 'Escape') {
      menu.hidden = true;
      button.setAttribute('aria-expanded', 'false');
      button.focus();
    }
  });
</script>
```

**탭 패널에서의 사용 예시**      
이 예시에서는 각 탭(button 요소)이 aria-controls 속성을 사용하여 해당하는 패널(div 요소)을 제어하고 있음을 나타냅니다. 사용자가 탭을 선택하면 해당 패널로 포커스가 이동하며, 선택된 탭이 활성화됩니다.    
```sh
<div role="tablist">
  <button role="tab" aria-controls="panel1" aria-selected="true" id="tab1" tabindex="0">탭 1</button>
  <button role="tab" aria-controls="panel2" aria-selected="false" id="tab2" tabindex="-1">탭 2</button>
</div>

<div id="panel1" role="tabpanel" tabindex="0">탭 1의 내용</div>
<div id="panel2" role="tabpanel" hidden tabindex="0">탭 2의 내용</div>

<script>
  const tabs = document.querySelectorAll('[role="tab"]');
  const panels = document.querySelectorAll('[role="tabpanel"]');

  tabs.forEach(tab => {
    tab.addEventListener('click', () => {
      tabs.forEach(t => {
        t.setAttribute('aria-selected', 'false');
        t.setAttribute('tabindex', '-1');
      });
      panels.forEach(panel => panel.hidden = true);

      tab.setAttribute('aria-selected', 'true');
      tab.setAttribute('tabindex', '0');
      document.getElementById(tab.getAttribute('aria-controls')).hidden = false;
      document.getElementById(tab.getAttribute('aria-controls')).focus(); // 패널에 포커스 설정
    });
  });
</script>
```

**모달 대화 상자에서의 사용 예시**      
이 예시에서는 button 요소가 aria-controls 속성을 통해 모달 대화 상자(div 요소)를 제어하고 있음을 나타냅니다. 모달이 열리면 닫기 버튼으로 포커스가 이동하고, 모달이 닫히면 버튼으로 포커스가 반환됩니다.    
```sh
<button id="open-modal" aria-controls="modal" aria-expanded="false">
  모달 열기
</button>

<div id="modal" role="dialog" aria-modal="true" hidden>
  <div role="document">
    <h2>모달 제목</h2>
    <p>이것은 모달의 내용입니다.</p>
    <button id="close-modal">모달 닫기</button>
  </div>
</div>

<script>
  const openButton = document.getElementById('open-modal');
  const modal = document.getElementById('modal');
  const closeButton = document.getElementById('close-modal');

  openButton.addEventListener('click', () => {
    modal.hidden = false;
    openButton.setAttribute('aria-expanded', 'true');
    closeButton.focus(); // 모달이 열리면 닫기 버튼에 포커스
  });

  closeButton.addEventListener('click', () => {
    modal.hidden = true;
    openButton.setAttribute('aria-expanded', 'false');
    openButton.focus(); // 모달이 닫히면 버튼으로 포커스 반환
  });

  // ESC 키로 모달 닫기
  modal.addEventListener('keydown', (event) => {
    if (event.key === 'Escape') {
      modal.hidden = true;
      openButton.setAttribute('aria-expanded', 'false');
      openButton.focus();
    }
  });
</script>
```

**스와이프 슬라이더에서의 사용 예시**      
이 예시에서는 이전 및 다음 버튼이 aria-controls 속성을 사용하여 슬라이더(div 요소)를 제어하고 있음을 나타냅니다. 사용자가 버튼을 클릭하면 슬라이드가 변경되며, 변경된 슬라이드에 포커스가 설정됩니다.    
```sh
<div id="slider" class="slider" aria-live="polite">
  <div id="slide1" class="slide">슬라이드 1</div>
  <div id="slide2" class="slide" hidden>슬라이드 2</div>
  <div id="slide3" class="slide" hidden>슬라이드 3</div>
</div>

<button id="prev" aria-controls="slider">이전</button>
<button id="next" aria-controls="slider">다음</button>

<script>
  const slides = document.querySelectorAll('.slide');
  let currentIndex = 0;

  function updateSlide(index) {
    slides[currentIndex].hidden = true;
    currentIndex = index;
    slides[currentIndex].hidden = false;
    slides[currentIndex].focus(); // 활성 슬라이드에 포커스 설정
  }

  document.getElementById('prev').addEventListener('click', () => {
    updateSlide((currentIndex - 1 + slides.length) % slides.length);
  });

  document.getElementById('next').addEventListener('click', () => {
    updateSlide((currentIndex + 1) % slides.length);
  });
</script>
```

### **4. aria-describedby (property)**    
aria-describedby 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 특정 요소에 대한 추가적인 설명을 제공하는 요소의 ID를 참조하는 데 사용됩니다. 이 속성은 주로 입력 필드, 버튼, 이미지 등에서 추가적인 컨텍스트나 설명을 제공할 때 사용되며, 보조 기술(예: 스크린 리더)이 이 정보를 사용자에게 전달할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-describedby)](https://www.w3.org/TR/wai-aria-1.2/#aria-describedby){: target="_blank"}   
[MDN Web Docs (aria-describedby)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-describedby){: target="_blank"}   


**aria-describedby 속성 값**  
- aria-describedby의 값은 하나 이상의 ID를 공백으로 구분하여 나열합니다. 이러한 ID들은 설명을 제공하는 요소를 가리킵니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: input, button, textarea, img, div 등 거의 모든 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: textbox, button, img, link 등 다양한 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 참조**: aria-controls 속성의 값은 반드시 유효한 ID여야 하며, 문서 내에서 고유해야 합니다. 잘못된 참조는 보조 기술 사용자에게 혼란을 줄 수 있습니다.   
- **시맨틱 의미**: aria-controls 속성은 보조 기술 사용자에게만 영향을 주므로, 제어되는 요소 간의 시각적 또는 논리적 관계를 명확히 하도록 HTML 구조를 설계해야 합니다.   
- **동작 시나리오**: 이 속성은 주로 JavaScript와 함께 사용되어 인터랙티브한 동작을 구현할 때 유용합니다.    

**폼 입력 필드에서의 사용 예시**      
이 예시에서는 input 요소가 aria-describedby 속성을 통해 추가 설명(div 요소)을 참조하고 있습니다. 스크린 리더는 사용자가 입력 필드에 포커스할 때 이 추가 설명을 읽어줍니다.      
```sh
<label for="username">사용자 이름:</label>
<input type="text" id="username" aria-describedby="username-desc">
<div id="username-desc">이름은 4~16자의 영문자나 숫자로 입력해야 합니다.</div>
```

**버튼에서의 사용 예시**      
이 예시에서는 button 요소가 aria-describedby 속성을 통해 추가 설명(div 요소)을 참조하고 있습니다. 이 설명은 버튼이 수행할 작업에 대한 추가 정보를 제공합니다.    
```sh
<button id="submit-btn" aria-describedby="submit-desc">
  제출
</button>
<div id="submit-desc">제출 버튼을 클릭하면 입력한 정보가 서버로 전송됩니다.</div>
```

**이미지에서의 사용 예시**      
이 예시에서는 img 요소가 aria-describedby 속성을 통해 이미지에 대한 추가 설명(div 요소)을 참조하고 있습니다. 스크린 리더는 이미지의 alt 텍스트와 함께 추가 설명을 읽어줍니다.    
```sh
<img src="example.jpg" alt="자연 경관 이미지" id="landscape" aria-describedby="image-desc">
<div id="image-desc">이 이미지는 저녁 노을이 비치는 산과 호수의 모습을 담고 있습니다.</div>
```

**복합 위젯에서의 사용 예시**      
이 예시에서는 div 요소가 aria-describedby 속성을 통해 경고 메시지에 대한 추가 설명을 제공하고 있습니다. 보조 기술은 경고 메시지를 설명과 함께 사용자에게 전달합니다.    
```sh
<div role="alert" aria-describedby="alert-desc">
  <strong>중요:</strong> 이 작업을 완료하려면 모든 필드를 채워야 합니다.
</div>
<div id="alert-desc">각 필드에 올바른 정보를 입력하지 않으면 오류 메시지가 표시됩니다.</div>
```

### **5. aria-details (property)**    
aria-details 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 특정 요소와 관련된 추가적인 세부 정보나 설명을 제공하는 다른 요소의 ID를 참조하는 데 사용됩니다. aria-describedby와 유사하지만, aria-details는 더 구체적이고 복잡한 설명이나 세부 사항을 제공하는 경우에 사용됩니다. 이 속성은 주로 보조 기술(예: 스크린 리더) 사용자에게 추가적인 정보를 제공하기 위해 사용됩니다.     
[WAI-ARIA 1.2 Specification (aria-details)](https://www.w3.org/TR/wai-aria-1.2/#aria-details){: target="_blank"}   
[MDN Web Docs (aria-details)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-details){: target="_blank"}   


**aria-details 속성 값**  
- aria-details의 값은 참조되는 요소의 id입니다. 하나 이상의 요소를 공백으로 구분하여 나열할 수 있습니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, details, summary, input, button 등 거의 모든 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: textbox, button, img, link 등 다양한 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **구체적인 세부 정보**: aria-details는 복잡한 설명이나 세부 정보를 제공할 때 사용됩니다. 기본적인 설명은 aria-describedby를 사용하는 것이 더 적합합니다.   
- **정확한 참조**: aria-details 속성의 값으로 참조되는 ID는 문서 내에서 고유해야 하며, 참조하는 요소가 실제로 존재해야 합니다.   
- **사용 시점**: aria-details는 주로 더 많은 세부 사항이 필요할 때 사용되며, 일반적으로 추가적인 컨텍스트가 필요한 상황에서 사용됩니다.    

**aria-details와 aria-describedby 비교**   
ARIA(Accessible Rich Internet Applications) 속성으로, 웹 콘텐츠의 접근성을 개선하기 위해 사용되지만, 그 목적과 기능이 다릅니다.   
- **aria-details**   
  - **목적**: aria-details는 더 복잡하거나 상세한 정보가 필요할 때 사용됩니다. 이 속성은 주로 추가적인 설명이나 상세한 정보를 제공하는 별도의 요소를 참조합니다.   
  - **사용 예**: 어떤 요소에 대한 자세한 설명이 다른 곳에 있을 때 그 정보를 연결하는 데 사용됩니다. 예를 들어, 사진에 대한 긴 설명이 이미지 바로 옆에 있지 않고, 페이지의 다른 부분에 위치해 있다면 aria-details를 사용하여 그 설명 요소를 참조할 수 있습니다.   
  - **특징**: aria-details가 가리키는 대상은 비교적 상세한 설명이 포함된 요소입니다. 사용자 에이전트(브라우저)와 보조 기술(예: 화면 낭독기)이 이 속성을 통해 관련된 상세 정보를 제공할 수 있습니다.   
  - **요약**: aria-details는 더 자세한 정보를 제공하는 요소를 참조합니다.   
- **aria-describedby**   
  - **목적**: aria-describedby는 요소에 대한 짧고 간결한 설명을 제공하는 다른 요소를 참조합니다. 이 설명은 보통 텍스트 형식이며, 간단한 문장이나 단어로 구성될 수 있습니다.      
  - **사용 예**: 폼 필드에 대한 간단한 설명을 제공하거나, 버튼의 기능을 설명하는데 사용됩니다. 예를 들어, 텍스트 입력 필드가 있고 그 아래에 짧은 설명이 있을 때, 이 설명 요소를 aria-describedby를 통해 참조할 수 있습니다.      
  - **특징**: aria-describedby 속성은 설명이 되는 요소를 가리키며, 이 설명은 간단하고 명확해야 합니다. 화면 낭독기는 이 설명을 읽어서 사용자가 어떤 기능이나 내용을 이해할 수 있도록 돕습니다.      
  - **요약**: aria-describedby는 간단한 설명을 제공하는 요소를 참조합니다.   

   
**이미지에 대한 추가 세부 정보 제공 예시**      
이 예시에서는 img 요소가 aria-details 속성을 통해 이미지에 대한 더 구체적인 설명(div 요소)을 참조하고 있습니다. 스크린 리더는 alt 속성의 기본 설명 외에도 추가적인 세부 정보를 사용자에게 제공할 수 있습니다.      
```sh
<img src="example.jpg" alt="자연 경관 이미지" id="landscape" aria-details="image-details">
<div id="image-details">
  이 이미지는 저녁 노을이 비치는 산과 호수의 모습을 담고 있습니다. 이 지역은 여름철에 많은 관광객이 찾는 곳으로, 맑은 날씨에 아름다운 풍경을 감상할 수 있습니다.
</div>
```

**폼 필드에 대한 복잡한 세부 정보 제공 예시**      
이 예시에서는 input 요소가 aria-details 속성을 통해 사용자 이름 필드에 대한 더 구체적인 입력 요구 사항을 제공하는 div 요소를 참조하고 있습니다. 사용자는 해당 필드에 대한 추가 정보를 받을 수 있습니다.    
```sh
<label for="username">사용자 이름:</label>
<input type="text" id="username" aria-details="username-details">
<div id="username-details">
  사용자 이름은 4~16자의 영문자나 숫자로 입력해야 합니다. 
  이름은 중복될 수 없으며, 공백은 사용할 수 없습니다.
</div>
```

**복잡한 위젯에 대한 세부 정보 제공 예시**      
이 예시에서는 button 요소가 aria-details 속성을 통해 버튼의 동작에 대한 더 구체적인 설명을 제공하는 div 요소를 참조하고 있습니다. 보조 기술은 이 버튼이 수행하는 작업에 대한 추가적인 세부 정보를 사용자에게 제공할 수 있습니다.    
```sh
<button id="view-details" aria-details="widget-details">
  세부 정보 보기
</button>
<div id="widget-details">
  이 버튼을 클릭하면 추가 옵션을 선택할 수 있는 메뉴가 열립니다. 메뉴에서 선택한 항목에 따라 다양한 설정을 조정할 수 있습니다.
</div>
```

**데이터 테이블에 대한 추가 설명 제공 예시**      
이 예시에서는 table 요소가 aria-details 속성을 통해 테이블의 내용과 관련된 추가 설명(div 요소)을 참조하고 있습니다. 사용자는 테이블의 목적이나 맥락에 대한 더 많은 정보를 받을 수 있습니다.    
```sh
<table aria-details="table-details">
  <thead>
    <tr>
      <th>제품명</th>
      <th>가격</th>
      <th>재고 상태</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>노트북</td>
      <td>100만원</td>
      <td>재고 있음</td>
    </tr>
    <tr>
      <td>스마트폰</td>
      <td>80만원</td>
      <td>재고 없음</td>
    </tr>
  </tbody>
</table>
<div id="table-details">
  이 표는 현재 판매 중인 전자제품의 목록을 나타내며, 재고 상태는 매일 업데이트됩니다. 가격은 세금 포함 가격입니다.
</div>
```

### **6. aria-errormessage (property)**    
aria-errormessage 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 사용자 입력에서 오류가 발생했을 때 해당 오류 메시지를 제공하는 요소의 ID를 참조합니다. 이 속성은 주로 폼 필드에서 사용되며, 보조 기술(예: 스크린 리더)을 통해 사용자에게 어떤 오류가 발생했는지 명확하게 전달하는 데 사용됩니다. 사용자가 입력한 데이터가 잘못되었을 때 해당 오류를 명확히 전달하는 데 매우 유용하며, 이를 통해 보조 기술 사용자가 웹 양식에서 발생하는 오류를 보다 쉽게 이해하고 수정할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-errormessage)](https://www.w3.org/TR/wai-aria-1.2/#aria-errormessage){: target="_blank"}   
[MDN Web Docs (aria-errormessage)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-errormessage){: target="_blank"}   


**aria-errormessage 속성 값**  
- aria-errormessage의 값은 오류 메시지를 제공하는 요소의 id입니다. 이 ID는 문서 내에서 고유해야 하며, 참조된 요소는 사용자에게 오류에 대한 구체적인 정보를 제공해야 합니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: input, textarea, select, form, div 등 사용자 입력을 받거나 오류 메시지를 표시하는 요소에서 사용 가능합니다.   
- **연관된 역할**: textbox, combobox, listbox, spinbutton, checkbox, radio, slider 등 다양한 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 오류 메시지 제공**: aria-errormessage는 사용자가 발생시킨 오류를 명확하게 설명하는 메시지와 연결되어야 합니다. 이 메시지는 사용자에게 무엇이 잘못되었는지, 그리고 어떻게 수정할 수 있는지에 대한 정보를 제공해야 합니다.   
- **동적 업데이트**: 오류 메시지는 사용자가 입력을 수정할 때 동적으로 업데이트될 수 있습니다. 이 경우 aria-errormessage 속성도 동적으로 변경되어야 합니다.   
- **보완적 사용**: aria-invalid 속성과 함께 사용하여 폼 필드의 유효성 검사 상태를 명확히 전달할 수 있습니다.   

   
**텍스트 입력 필드에서의 사용 예시**      
이 예시에서는 이메일 입력 필드가 유효성 검사를 통과하지 못할 경우, aria-errormessage 속성을 통해 오류 메시지가 사용자에게 전달됩니다. 오류가 발생하면 필드에 포커스가 유지되며, 오류가 수정되면 오류 메시지가 숨겨집니다.      
```sh
<label for="email">이메일 주소:</label>
<input type="email" id="email" aria-describedby="email-desc" aria-errormessage="email-error" aria-invalid="false">
<div id="email-desc">유효한 이메일 주소를 입력하세요.</div>
<div id="email-error" hidden>올바른 이메일 주소 형식을 입력해야 합니다.</div>

<script>
  const emailInput = document.getElementById('email');
  const errorMessage = document.getElementById('email-error');

  emailInput.addEventListener('input', () => {
    if (!emailInput.checkValidity()) {
      emailInput.setAttribute('aria-invalid', 'true');
      errorMessage.hidden = false;
      emailInput.focus(); // 오류 발생 시 입력 필드에 포커스 설정
    } else {
      emailInput.setAttribute('aria-invalid', 'false');
      errorMessage.hidden = true;
    }
  });
</script>
```

**비밀번호 확인 필드에서의 사용 예시**      
이 예시에서는 비밀번호와 비밀번호 확인 필드 간의 불일치에 대해 aria-errormessage 속성을 사용하여 오류 메시지가 사용자에게 전달됩니다. 비밀번호가 일치하지 않으면 확인 필드에 포커스가 유지되며, 오류가 수정되면 포커스가 해제됩니다.    
```sh
<label for="password">비밀번호:</label>
<input type="password" id="password" aria-describedby="password-desc" aria-errormessage="password-error" aria-invalid="false">
<div id="password-desc">비밀번호는 8자 이상이어야 합니다.</div>

<label for="confirm-password">비밀번호 확인:</label>
<input type="password" id="confirm-password" aria-errormessage="confirm-password-error" aria-invalid="false">
<div id="confirm-password-error" hidden>비밀번호가 일치하지 않습니다.</div>

<script>
  const passwordInput = document.getElementById('password');
  const confirmPasswordInput = document.getElementById('confirm-password');
  const confirmPasswordError = document.getElementById('confirm-password-error');

  confirmPasswordInput.addEventListener('input', () => {
    if (confirmPasswordInput.value !== passwordInput.value) {
      confirmPasswordInput.setAttribute('aria-invalid', 'true');
      confirmPasswordError.hidden = false;
      confirmPasswordInput.focus(); // 오류 발생 시 확인 필드에 포커스 유지
    } else {
      confirmPasswordInput.setAttribute('aria-invalid', 'false');
      confirmPasswordError.hidden = true;
      confirmPasswordInput.blur(); // 오류가 수정되면 포커스 해제
    }
  });
</script>
```

**체크박스에서의 사용 예시**      
이 예시에서는 사용자가 체크박스를 선택하지 않고 제출 버튼을 클릭했을 때, aria-errormessage 속성을 통해 오류 메시지가 표시됩니다. 오류 발생 시 체크박스에 포커스가 유지되며, 사용자가 체크박스를 선택하면 제출 버튼으로 포커스가 이동합니다.    
```sh
<label>
  <input type="checkbox" id="terms" aria-errormessage="terms-error" aria-invalid="false">
  약관에 동의합니다.
</label>
<div id="terms-error" hidden>약관에 동의해야 합니다.</div>

<button id="submit-btn" type="submit">제출</button>

<script>
  const termsCheckbox = document.getElementById('terms');
  const termsError = document.getElementById('terms-error');
  const submitButton = document.getElementById('submit-btn');

  submitButton.addEventListener('click', (event) => {
    if (!termsCheckbox.checked) {
      event.preventDefault();
      termsCheckbox.setAttribute('aria-invalid', 'true');
      termsError.hidden = false;
      termsCheckbox.focus(); // 오류 발생 시 체크박스에 포커스 설정
    } else {
      termsCheckbox.setAttribute('aria-invalid', 'false');
      termsError.hidden = true;
      submitButton.focus(); // 오류가 수정되면 제출 버튼에 포커스 이동
    }
  });
</script>
```

**데이터 테이블에 대한 추가 설명 제공 예시**      
이 예시에서는 table 요소가 aria-details 속성을 통해 테이블의 내용과 관련된 추가 설명(div 요소)을 참조하고 있습니다. 사용자는 테이블의 목적이나 맥락에 대한 더 많은 정보를 받을 수 있습니다.    
```sh
<table aria-details="table-details">
  <thead>
    <tr>
      <th>제품명</th>
      <th>가격</th>
      <th>재고 상태</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>노트북</td>
      <td>100만원</td>
      <td>재고 있음</td>
    </tr>
    <tr>
      <td>스마트폰</td>
      <td>80만원</td>
      <td>재고 없음</td>
    </tr>
  </tbody>
</table>
<div id="table-details">
  이 표는 현재 판매 중인 전자제품의 목록을 나타내며, 재고 상태는 매일 업데이트됩니다. 가격은 세금 포함 가격입니다.
</div>
```

### **7. aria-activedescendant (property)**    
aria-activedescendant 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성 중 하나로, 복잡한 위젯 내에서 현재 활성화된(또는 포커스된) 자식 요소를 지정하는 데 사용됩니다. 이 속성은 사용자 입력에 따라 동적으로 선택된 자식 요소를 명시적으로 참조함으로써, 스크린 리더가 현재 활성화된 항목을 올바르게 전달할 수 있도록 돕습니다.   
[WAI-ARIA 1.2 Specification (aria-activedescendant)](https://www.w3.org/TR/wai-aria-1.2/#aria-activedescendant){: target="_blank"}   
[MDN Web Docs (aria-activedescendant)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-activedescendant){: target="_blank"}   


**aria-activedescendant 속성 값**  
- aria-activedescendant는 현재 활성화된 자식 요소의 id 값을 가집니다. 이 속성은 부모 요소에 설정되고, 해당 부모 요소 내에서 활성화된 자식 요소를 나타냅니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: input, div, ul, table, listbox, grid 등   
- **연관된 역할**: listbox, grid, tree, tablist, combobox, menu, radiogroup 등에서 주로 사용됩니다. 주로 여러 자식 요소를 포함하고 있으며, 사용자의 선택에 따라 활성화된 요소가 바뀌는 구조에서 유용합니다.    

**사용 시 주의사항**   
- **동적 업데이트**: aria-activedescendant 속성은 자식 요소 간의 활성화 상태가 변경될 때마다 동적으로 업데이트되어야 합니다. 예를 들어, 키보드 네비게이션을 통해 선택된 항목이 바뀔 때마다 속성 값을 업데이트해야 합니다.   
- **포커스 관리**: aria-activedescendant 속성을 사용하는 요소는 보통 자체적으로 포커스를 받지 않고, 자식 요소가 대신 포커스를 받는 상황에서 사용됩니다. 이 경우 자식 요소로 포커스를 이동하지 않고, 부모 요소의 포커스 상태를 유지한 채 aria-activedescendant 속성으로 활성화된 자식을 지정합니다.   
- **유효한 ID**: 속성 값으로 참조하는 ID는 반드시 문서 내의 유효한 요소 ID여야 합니다. 참조하는 자식 요소가 실제로 존재하지 않으면, 스크린 리더 사용자가 혼란을 겪을 수 있습니다.    


**Listbox에서의 사용 예시**      
이 예시에서는 사용자가 입력한 값에 따라 listbox의 항목 중 활성화된 항목을 aria-activedescendant로 지정합니다. 스크린 리더는 사용자가 입력을 통해 선택된 항목을 인식할 수 있게 됩니다.    
```sh
<label for="dropdown">과일 선택:</label>
<input type="text" id="dropdown" aria-controls="fruit-list" aria-activedescendant="">
<ul id="fruit-list" role="listbox">
  <li id="apple" role="option">사과</li>
  <li id="banana" role="option">바나나</li>
  <li id="cherry" role="option">체리</li>
</ul>

<script>
  const dropdown = document.getElementById('dropdown');
  const options = document.querySelectorAll('#fruit-list li');

  dropdown.addEventListener('input', () => {
    let activeId = '';
    options.forEach(option => {
      if (option.textContent.toLowerCase().includes(dropdown.value.toLowerCase())) {
        activeId = option.id;
      }
    });
    dropdown.setAttribute('aria-activedescendant', activeId);
  });

  options.forEach(option => {
    option.addEventListener('click', () => {
      dropdown.value = option.textContent;
      dropdown.setAttribute('aria-activedescendant', option.id);
    });
  });
</script>
```

**Combobox에서의 사용 예시**      
이 예시에서는 combobox에서 사용자가 입력한 내용에 따라 listbox 항목 중 선택된 항목이 aria-activedescendant로 지정됩니다. 사용자는 입력한 내용에 따라 자동으로 필터링된 결과를 시각적으로 확인하고, 스크린 리더는 해당 상태를 올바르게 알립니다.    
```sh
<label for="combo">언어 선택:</label>
<input type="text" id="combo" role="combobox" aria-controls="language-list" aria-activedescendant="">
<ul id="language-list" role="listbox" hidden>
  <li id="english" role="option">영어</li>
  <li id="spanish" role="option">스페인어</li>
  <li id="french" role="option">프랑스어</li>
</ul>

<script>
  const combo = document.getElementById('combo');
  const listbox = document.getElementById('language-list');
  const options = listbox.querySelectorAll('li');

  combo.addEventListener('focus', () => {
    listbox.hidden = false;
  });

  combo.addEventListener('blur', () => {
    listbox.hidden = true;
  });

  combo.addEventListener('input', () => {
    let activeId = '';
    options.forEach(option => {
      if (option.textContent.toLowerCase().includes(combo.value.toLowerCase())) {
        activeId = option.id;
      }
    });
    combo.setAttribute('aria-activedescendant', activeId);
  });

  options.forEach(option => {
    option.addEventListener('click', () => {
      combo.value = option.textContent;
      combo.setAttribute('aria-activedescendant', option.id);
      listbox.hidden = true;
    });
  });
</script>
```


### **8. aria-flowto (property)**    
aria-flowto 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 웹 페이지 내의 요소들이 일반적인 문서 흐름과 다르게 논리적으로 연결되어 있음을 명시할 때 사용됩니다. 이 속성은 사용자가 페이지 내의 요소 간 이동을 할 때 특정 요소에서 다른 요소로 이동하도록 안내하는 데 유용합니다. 주로 복잡한 레이아웃에서 요소 간의 탐색 순서를 제어하거나 명시하고자 할 때 사용됩니다.     
[WAI-ARIA 1.2 Specification (aria-flowto)](https://www.w3.org/TR/wai-aria-1.2/#aria-flowto){: target="_blank"}   
[MDN Web Docs (aria-flowto)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-flowto){: target="_blank"}   


**aria-flowto 속성 값**  
- aria-flowto의 값은 하나 이상의 요소 ID입니다. 여러 요소를 참조할 경우 ID를 공백으로 구분하여 나열합니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, section, article 등 거의 모든 HTML 요소에서 사용 가능합니다.   
- **연관된 역할**: 다양한 역할과 함께 사용되며, section, article, region, listitem 등 요소의 논리적 흐름을 명시할 필요가 있는 상황에서 유용합니다.    

**사용 시 주의사항**   
- **정확한 흐름 정의**: aria-flowto 속성은 논리적인 탐색 순서를 명확히 정의할 때 사용되며, 이로 인해 사용자가 예상치 못한 방식으로 페이지를 탐색하지 않도록 주의해야 합니다.   
- **참조의 유효성**: 참조된 요소의 ID는 문서 내에서 유일해야 하며, 실제로 존재하는 요소를 가리켜야 합니다.   
- **보조 기술의 호환성**: 모든 보조 기술이 aria-flowto 속성을 완벽하게 지원하지 않을 수 있습니다. 따라서, 이 속성만을 의존하지 않고 페이지 내의 탐색 흐름을 설계해야 합니다.   
- **탐색 혼란 방지**: 사용자가 논리적인 흐름을 쉽게 이해할 수 있도록, aria-flowto 속성을 신중하게 사용해야 합니다. 지나치게 복잡한 탐색 흐름은 오히려 혼란을 초래할 수 있습니다.   

   
**일반적인 문서 흐름에서 벗어난 요소 간 연결 예시**      
이 예시에서는 section1에서 section3로 논리적인 탐색 순서가 연결되어 있으며, section2는 논리적 흐름에서 제외되었습니다. 보조 기술 사용자는 section1에서 section3로 바로 이동할 수 있습니다.      
```sh
<div id="section1" aria-flowto="section3">
  <h2>섹션 1</h2>
  <p>이곳에서 섹션 3로 이동합니다.</p>
</div>

<div id="section2">
  <h2>섹션 2</h2>
  <p>이 섹션은 섹션 1과 섹션 3 사이에 존재하지만, 논리적 흐름에서 제외되었습니다.</p>
</div>

<div id="section3">
  <h2>섹션 3</h2>
  <p>이곳은 섹션 1의 다음 논리적 섹션입니다.</p>
</div>
```

**인터랙티브한 탐색 순서 제어 예시**      
이 예시에서는 단계별 양식 입력 흐름을 제어하고 있으며, step1에서 step3로 논리적으로 연결되어 있습니다. 사용자는 step2를 건너뛰고 바로 step3로 이동할 수 있습니다.    
```sh
<div id="step1" aria-flowto="step3">
  <h2>1단계: 개인 정보 입력</h2>
  <p>이 단계를 완료하면 3단계로 넘어갑니다.</p>
</div>

<div id="step2">
  <h2>2단계: 주소 입력</h2>
  <p>이 단계는 건너뛰고 논리적으로는 3단계로 이동합니다.</p>
</div>

<div id="step3">
  <h2>3단계: 결제 정보 입력</h2>
  <p>여기서 결제 정보를 입력하세요.</p>
</div>
```

**복잡한 레이아웃에서의 흐름 제어 예시**      
이 예시에서는 content1과 content3이 논리적으로 연결되어 있으며, content2는 탐색 흐름에서 제외되었습니다. 보조 기술 사용자는 이 논리적 흐름에 따라 콘텐츠를 탐색할 수 있습니다.    
```sh
<div id="content1" aria-flowto="content3">
  <h2>콘텐츠 1</h2>
  <p>이 콘텐츠에서 콘텐츠 3으로 이동합니다.</p>
</div>

<div id="content2">
  <h2>콘텐츠 2</h2>
  <p>이 콘텐츠는 논리적 흐름에서 제외되었습니다.</p>
</div>

<div id="content3">
  <h2>콘텐츠 3</h2>
  <p>이 콘텐츠는 콘텐츠 1의 다음 논리적 콘텐츠입니다.</p>
</div>
```

### **9. aria-owns (property)**    
aria-owns 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, DOM(Document Object Model) 트리 내에서 시각적으로나 논리적으로 특정 요소의 자식 요소처럼 보이지만, 실제로는 다른 위치에 있는 요소들을 명시적으로 부모-자식 관계로 설정할 때 사용됩니다. 이 속성은 스크린 리더와 같은 보조 기술이 요소 간의 논리적인 관계를 정확히 이해할 수 있도록 도와줍니다.     
[WAI-ARIA 1.2 Specification (aria-owns)](https://www.w3.org/TR/wai-aria-1.2/#aria-owns){: target="_blank"}   
[MDN Web Docs (aria-owns)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-owns){: target="_blank"}   


**aria-owns 속성 값**  
- aria-owns의 값은 소유할 자식 요소의 id입니다. 하나 이상의 요소를 공백으로 구분하여 나열할 수 있습니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, ul, li, table, tr 등 거의 모든 HTML 요소에서 사용 가능합니다.    
- **연관된 역할**: tree, grid, listbox, menu, toolbar, tablist 등 특정 요소들을 논리적으로 그룹화할 때 사용됩니다.    

**사용 시 주의사항**   
- **DOM 트리와의 일관성**: aria-owns 속성은 실제 DOM 트리 구조를 변경하지 않고 논리적인 관계를 정의하기 때문에, 사용자에게 혼란을 주지 않도록 주의해야 합니다. 사용자는 시각적으로나 기능적으로 요소들이 그룹화되어 있는 것을 기대합니다.    
- **중복 관계 피하기**: aria-owns를 사용하여 이미 DOM 트리에서 자식으로 정의된 요소를 다시 소유하는 것으로 지정할 경우 혼란을 줄 수 있습니다. aria-owns는 실제로 DOM에서 자식이 아닌 요소에 대해서만 사용해야 합니다.    
- **순환 참조 주의**: aria-owns를 잘못 사용하면 순환 참조가 발생할 수 있습니다. 이는 보조 기술 사용자를 혼란스럽게 만들 수 있습니다.   

**사용 시나리오**   
- **동적 콘텐츠 관리**: 동적으로 추가되거나 재배치된 콘텐츠를 논리적으로 그룹화해야 할 때 aria-owns를 사용하여 보조 기술 사용자에게 논리적인 관계를 명확히 전달할 수 있습니다.   
- **복합 위젯**: 트리, 그리드, 메뉴, 탭 인터페이스 등에서 논리적인 부모-자식 관계를 명시하여 복잡한 UI 구조를 보다 명확하게 할 수 있습니다.   
- **리스트 관리**: 리스트나 트리에서 DOM 구조와 논리적 구조가 다를 때, aria-owns를 사용하여 올바른 탐색 순서를 유지할 수 있습니다.   
   
**동적 메뉴에서의 사용 예시**      
이 예시에서는 menu 요소가 aria-owns 속성을 통해 실제 DOM 트리 구조와는 달리 특정 메뉴 항목들을 명시적으로 소유하고 있음을 나타냅니다. menu-item 요소들이 실제로는 다른 위치에 있을 수 있지만, 논리적으로 menu의 자식 요소로 처리됩니다.      
```sh
<div id="menu-button" role="button" aria-haspopup="true" aria-expanded="false" aria-controls="menu">
  메뉴 열기
</div>

<div role="menu" id="menu" aria-owns="menu-item-1 menu-item-2 menu-item-3">
  <div role="menuitem" id="menu-item-1">메뉴 항목 1</div>
  <div role="menuitem" id="menu-item-2">메뉴 항목 2</div>
  <div role="menuitem" id="menu-item-3">메뉴 항목 3</div>
</div>
```

**트리 구조에서의 사용 예시**      
이 예시에서는 parent-node와 child-nodes가 실제로는 DOM 트리에서 떨어져 있지만, aria-owns 속성을 사용하여 논리적으로 트리 구조의 부모-자식 관계를 형성합니다.    
```sh
<div role="tree" id="tree">
  <div role="treeitem" id="parent-node">부모 노드</div>
</div>

<div role="group" id="child-nodes" aria-owns="child-node-1 child-node-2 child-node-3">
  <div role="treeitem" id="child-node-1">자식 노드 1</div>
  <div role="treeitem" id="child-node-2">자식 노드 2</div>
  <div role="treeitem" id="child-node-3">자식 노드 3</div>
</div>
```

**복합 위젯에서의 사용 예시**      
이 예시에서는 content 요소가 aria-owns 속성을 통해 실제 DOM 트리에서 떨어져 있는 탭 패널(tabpanel)들을 논리적으로 소유하고 있음을 나타냅니다.    
```sh
<div role="tablist" id="tablist">
  <div role="tab" id="tab1">탭 1</div>
  <div role="tab" id="tab2">탭 2</div>
</div>

<div id="content" aria-owns="tabpanel1 tabpanel2">
  <div role="tabpanel" id="tabpanel1">탭 1의 콘텐츠</div>
  <div role="tabpanel" id="tabpanel2">탭 2의 콘텐츠</div>
</div>
```

### **10. aria-posinset (property)**    
aria-posinset 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 특정 항목이 세트나 그룹 내에서 몇 번째 위치에 있는지를 나타낼 때 사용됩니다. 이 속성은 일반적으로 aria-setsize와 함께 사용되며, 리스트, 트리, 그리드 등에서 항목의 순서를 명확하게 정의하기 위해 사용됩니다. 이 속성은 스크린 리더와 같은 보조 기술이 그룹 내 항목의 위치를 사용자에게 정확하게 전달할 수 있도록 도와줍니다.     
[WAI-ARIA 1.2 Specification (aria-posinset)](https://www.w3.org/TR/wai-aria-1.2/#aria-posinset){: target="_blank"}   
[MDN Web Docs (aria-posinset)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-posinset){: target="_blank"}   


**aria-posinset 속성 값**  
- aria-posinset의 값은 1 이상의 양의 정수로, 세트나 그룹 내에서 요소의 위치를 나타냅니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: li, option, tr, div, span 등 리스트 항목이나 트리 항목 등을 나타내는 요소에서 사용됩니다.   
- **연관된 역할**: listitem, treeitem, option, row 등 그룹화된 항목에서 주로 사용됩니다.    

**사용 시 주의사항**   
- **일관성 유지**: aria-posinset의 값은 해당 그룹 내의 다른 항목들과 일관성을 유지해야 합니다. 이 값은 해당 항목이 그룹 내에서 몇 번째인지 명확하게 나타내야 합니다.   
- **aria-setsize와 함께 사용**: 일반적으로 aria-setsize 속성과 함께 사용하여 세트의 전체 크기와 각 항목의 위치를 명확하게 정의합니다.   
- **적절한 역할과 함께 사용**: 이 속성은 주로 listitem, treeitem, option, row 등의 역할과 함께 사용되어, 보조 기술이 그룹 내의 탐색 위치를 사용자에게 전달할 수 있도록 합니다.   

**사용 시나리오**   
- **리스트 항목 정의**: 리스트 내의 각 항목의 위치를 명확히 하여 사용자가 현재 몇 번째 항목을 탐색 중인지 알 수 있도록 합니다.   
- **트리 구조**: 트리 구조에서 각 노드의 위치를 명확하게 정의하여, 사용자가 트리 내에서 탐색하는 위치를 파악할 수 있도록 합니다.   
- **그리드 또는 테이블**: 그리드 또는 테이블에서 각 행 또는 셀의 위치를 명확하게 정의하여 탐색의 편의성을 높입니다.   
   
**리스트 항목에서의 사용 예시**      
이 예시에서는 ul 요소 내의 각 li 요소가 aria-posinset 속성을 통해 리스트 내에서 몇 번째 항목인지를 명시하고 있습니다. 스크린 리더는 사용자가 현재 탐색 중인 항목이 전체 리스트 중 몇 번째인지 전달할 수 있습니다.      
```sh
<ul>
  <li role="listitem" aria-posinset="1" aria-setsize="3">항목 1</li>
  <li role="listitem" aria-posinset="2" aria-setsize="3">항목 2</li>
  <li role="listitem" aria-posinset="3" aria-setsize="3">항목 3</li>
</ul>
```

**트리 항목에서의 사용 예시**      
이 예시에서는 트리 구조 내의 각 li 요소가 aria-posinset 속성을 통해 트리에서의 위치를 나타냅니다. 트리 구조에서 스크린 리더는 현재 항목이 몇 번째 위치에 있는지를 사용자에게 전달할 수 있습니다.    
```sh
<ul role="tree">
  <li role="treeitem" aria-posinset="1" aria-setsize="3">루트 항목 1</li>
  <li role="treeitem" aria-posinset="2" aria-setsize="3">루트 항목 2</li>
  <li role="treeitem" aria-posinset="3" aria-setsize="3">루트 항목 3</li>
</ul>
```

**옵션 항목에서의 사용 예시**      
이 예시에서는 select 요소 내의 각 option 요소가 aria-posinset 속성을 통해 해당 옵션이 리스트 내에서 몇 번째 위치에 있는지를 나타냅니다. 사용자는 옵션의 순서를 정확하게 파악할 수 있습니다.    
```sh
<select>
  <option role="option" aria-posinset="1" aria-setsize="4">옵션 1</option>
  <option role="option" aria-posinset="2" aria-setsize="4">옵션 2</option>
  <option role="option" aria-posinset="3" aria-setsize="4">옵션 3</option>
  <option role="option" aria-posinset="4" aria-setsize="4">옵션 4</option>
</select>
```

### **11. aria-setsize (property)**    
aria-setsize 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 특정 그룹이나 세트(set) 내에 포함된 항목의 총 개수를 명시하는 데 사용됩니다. 이 속성은 주로 리스트 항목, 트리 항목, 그리드 항목 등에서 사용되며, 보조 기술(예: 스크린 리더)이 사용자에게 현재 항목이 속한 세트의 크기를 전달할 수 있도록 도와줍니다. aria-setsize 속성은 aria-posinset 속성과 함께 사용하여 세트 내 항목의 순서와 전체 크기를 명확하게 나타냅니다.     
[WAI-ARIA 1.2 Specification (aria-setsize)](https://www.w3.org/TR/wai-aria-1.2/#aria-setsize){: target="_blank"}   
[MDN Web Docs (aria-setsize)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-setsize){: target="_blank"}   


**aria-setsize 속성 값**  
- aria-setsize의 값은 1 이상의 양의 정수로, 세트나 그룹 내의 항목 총수를 나타냅니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: li, option, tr, div, span 등 리스트 항목이나 트리 항목 등을 나타내는 요소에서 사용됩니다.   
- **연관된 역할**: listitem, treeitem, option, row 등 그룹화된 항목에서 주로 사용됩니다.    

**사용 시 주의사항**   
- **정확한 세트 크기 제공**: aria-setsize는 세트 내 항목의 총 개수를 정확히 반영해야 합니다. 예를 들어, 리스트에 5개의 항목이 있으면, 각 항목의 aria-setsize 값은 5여야 합니다.   
- **aria-posinset과 함께 사용**: 일반적으로 aria-posinset 속성과 함께 사용하여, 세트의 전체 크기와 각 항목의 위치를 명확하게 정의합니다.   
- **중복 또는 누락 방지**: aria-setsize는 동일한 세트 내의 다른 항목과 일치해야 하며, 중복되거나 누락되지 않도록 주의해야 합니다.   

**사용 시나리오**   
- **리스트 항목**: 리스트나 메뉴에서 항목의 총 개수를 명시하여 사용자가 전체 항목의 크기를 파악할 수 있도록 합니다.   
- **트리 구조**: 트리 내의 항목 개수를 명시하여 사용자가 전체 트리 구조에서 탐색할 위치를 이해할 수 있도록 합니다.   
- **테이블의 행 또는 열**: 테이블에서 행이나 열의 개수를 명확하게 정의하여 탐색의 편의성을 높입니다.   
   
**리스트 항목에서의 사용 예시**      
이 예시에서는 ul 요소 내의 각 li 요소가 aria-setsize 속성을 통해 리스트 내 항목의 총 개수를 명시하고 있습니다. 스크린 리더는 사용자가 현재 탐색 중인 항목이 3개의 항목 중 하나임을 전달할 수 있습니다.      
```sh
<ul>
  <li role="listitem" aria-posinset="1" aria-setsize="3">항목 1</li>
  <li role="listitem" aria-posinset="2" aria-setsize="3">항목 2</li>
  <li role="listitem" aria-posinset="3" aria-setsize="3">항목 3</li>
</ul>
```

**트리 항목에서의 사용 예시**      
이 예시에서는 트리 구조 내의 각 li 요소가 aria-setsize 속성을 통해 트리 내의 루트 항목의 총 개수를 나타냅니다. 사용자는 전체 트리 구조에서 몇 개의 루트 항목이 있는지 파악할 수 있습니다.    
```sh
<ul role="tree">
  <li role="treeitem" aria-posinset="1" aria-setsize="3">루트 항목 1</li>
  <li role="treeitem" aria-posinset="2" aria-setsize="3">루트 항목 2</li>
  <li role="treeitem" aria-posinset="3" aria-setsize="3">루트 항목 3</li>
</ul>
```

**테이블 행에서의 사용 예시**      
이 예시에서는 테이블 내의 각 행(tr 요소)이 aria-setsize 속성을 통해 전체 테이블에서 몇 개의 행이 있는지 명시하고 있습니다. 사용자는 현재 탐색 중인 행이 전체 행의 몇 번째인지 알 수 있습니다.    
```sh
<table>
  <tr aria-posinset="1" aria-setsize="4">
    <td>셀 1-1</td>
    <td>셀 1-2</td>
  </tr>
  <tr aria-posinset="2" aria-setsize="4">
    <td>셀 2-1</td>
    <td>셀 2-2</td>
  </tr>
  <tr aria-posinset="3" aria-setsize="4">
    <td>셀 3-1</td>
    <td>셀 3-2</td>
  </tr>
  <tr aria-posinset="4" aria-setsize="4">
    <td>셀 4-1</td>
    <td>셀 4-2</td>
  </tr>
</table>
```


### **12. aria-colcount (property)**    
aria-colcount 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 정의된 속성 중 하나로, 그리드나 테이블 구조에서 총 열(column)의 수를 명시적으로 설정하는 데 사용됩니다. 이 속성은 특히 그리드나 테이블이 동적으로 생성되거나 페이지에서 일부 열만 보이는 경우(동적인 그리드나 테이블의 열 수를 명확히 정의)에 유용합니다. aria-colcount는 스크린 리더와 같은 보조 기술이 전체 테이블 구조를 올바르게 이해하고 사용자에게 전달할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-colcount)](https://www.w3.org/TR/wai-aria-1.2/#aria-colcount){: target="_blank"}   
[MDN Web Docs (aria-colcount)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-colcount){: target="_blank"}   


**aria-colcount 속성 값**  
- aria-colcount의 값은 양의 정수로, 그리드 또는 테이블의 열 수를 나타냅니다.   
- 예), aria-colcount="5"는 5개의 열이 있음을 의미합니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: table, grid, treegrid 등 테이블 또는 그리드 구조를 나타내는 요소에 사용됩니다.   
- **연관된 역할**: table, grid, treegrid 등의 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 열 수 설정**: aria-colcount는 시각적으로 보이는 열의 수가 아닌, 데이터 구조에서 전체 열의 수를 반영해야 합니다. 페이지에서 일부 열이 숨겨져 있더라도 전체 열 수를 지정해야 합니다.   
- **동적 콘텐츠**: 동적으로 생성되거나 수정되는 테이블이나 그리드에서는 이 속성을 사용하여 보조 기술이 전체 데이터 구조를 이해할 수 있도록 해야 합니다.   
- **보완적 속성 사용**: aria-colindex, aria-rowcount, aria-rowindex 등 다른 ARIA 속성과 함께 사용하여 전체 테이블 구조를 명확히 나타낼 수 있습니다.    


**단순 테이블에서의 사용 예시**      
이 예시에서는 테이블이 4개의 열을 가지고 있으므로 aria-colcount="4"로 지정합니다. 스크린 리더는 이 속성을 사용하여 테이블의 열 구조를 정확히 전달합니다.    
```sh
<table role="grid" aria-colcount="4">
  <tr>
    <th>이름</th>
    <th>나이</th>
    <th>직업</th>
    <th>국가</th>
  </tr>
  <tr>
    <td>김철수</td>
    <td>30</td>
    <td>개발자</td>
    <td>한국</td>
  </tr>
  <tr>
    <td>이영희</td>
    <td>25</td>
    <td>디자이너</td>
    <td>한국</td>
  </tr>
</table>
```

**동적으로 생성되는 그리드에서의 사용 예시**      
이 그리드 구조는 3개의 열을 가지고 있으므로 aria-colcount="3"로 지정합니다. 스크린 리더는 이 정보를 사용하여 그리드의 열 구조를 사용자에게 전달할 수 있습니다.    
```sh
<div role="grid" aria-colcount="3">
  <div role="row">
    <div role="gridcell">제품명</div>
    <div role="gridcell">가격</div>
    <div role="gridcell">재고 상태</div>
  </div>
  <div role="row">
    <div role="gridcell">노트북</div>
    <div role="gridcell">100만원</div>
    <div role="gridcell">재고 있음</div>
  </div>
  <div role="row">
    <div role="gridcell">스마트폰</div>
    <div role="gridcell">80만원</div>
    <div role="gridcell">재고 없음</div>
  </div>
</div>
```

**시멘틱 구조의 예시**      
이 예시에서는 aria-colcount와 함께 aria-rowcount 속성도 사용하여 전체 그리드의 행과 열의 수를 명확히 나타내고 있습니다. 이러한 정보는 스크린 리더가 그리드의 구조를 정확하게 이해하고 사용자에게 전달하는 데 도움을 줍니다.    
```sh
<div role="grid" aria-colcount="4" aria-rowcount="3">
  <div role="row">
    <div role="columnheader">제품명</div>
    <div role="columnheader">카테고리</div>
    <div role="columnheader">가격</div>
    <div role="columnheader">재고</div>
  </div>
  <div role="row">
    <div role="gridcell">노트북</div>
    <div role="gridcell">전자제품</div>
    <div role="gridcell">100만원</div>
    <div role="gridcell">있음</div>
  </div>
  <div role="row">
    <div role="gridcell">스마트폰</div>
    <div role="gridcell">전자제품</div>
    <div role="gridcell">80만원</div>
    <div role="gridcell">없음</div>
  </div>
</div>
```

### **13. aria-colindex (property)**    
aria-colindex 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 그리드 또는 테이블 구조에서 특정 셀(gridcell 또는 cell)이 어느 열에 위치하는지를 명시적으로 지정합니다. 이 속성은 스크린 리더와 같은 보조 기술이 현재 셀의 위치를 정확하게 파악하고 사용자에게 전달할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-colindex)](https://www.w3.org/TR/wai-aria-1.2/#aria-colindex){: target="_blank"}   
[MDN Web Docs (aria-colindex)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-colindex){: target="_blank"}   


**aria-colindex 속성 값**  
- aria-colindex의 값은 1 이상의 양의 정수로, 그리드나 테이블의 열(column) 번호를 나타냅니다.    
- 예), aria-colindex="1"은 해당 셀이 첫 번째 열에 위치함을 의미합니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, td, th, li 등 그리드 또는 테이블 셀을 나타내는 요소에서 사용됩니다.   
- **연관된 역할**: gridcell, columnheader, rowheader, cell 등의 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 인덱스 제공**: aria-colindex 값은 시각적으로 표시되는 순서와 일치해야 합니다. 이 속성을 사용하여 보조 기술이 테이블이나 그리드의 정확한 구조를 인식할 수 있도록 해야 합니다.   
- **스패닝 셀**: 셀이 여러 열에 걸쳐(span) 있는 경우, aria-colindex는 셀의 시작 위치를 나타내며, colspan 속성과 함께 사용될 수 있습니다.   
- **동적 콘텐츠**: 동적으로 생성되거나 수정되는 그리드 또는 테이블에서는 이 속성을 사용하여 보조 기술이 전체 데이터 구조를 올바르게 이해할 수 있도록 해야 합니다.    


**단순 테이블에서의 사용 예시**      
이 예시에서는 각 th와 td 요소에 aria-colindex 속성을 사용하여 열의 위치를 명확히 지정합니다. 스크린 리더는 이 정보를 사용하여 테이블의 구조를 올바르게 사용자에게 전달할 수 있습니다.    
```sh
<table role="grid">
  <tr>
    <th role="columnheader" aria-colindex="1">이름</th>
    <th role="columnheader" aria-colindex="2">나이</th>
    <th role="columnheader" aria-colindex="3">직업</th>
    <th role="columnheader" aria-colindex="4">국가</th>
  </tr>
  <tr>
    <td role="gridcell" aria-colindex="1">김철수</td>
    <td role="gridcell" aria-colindex="2">30</td>
    <td role="gridcell" aria-colindex="3">개발자</td>
    <td role="gridcell" aria-colindex="4">한국</td>
  </tr>
</table>
```

**동적으로 생성되는 그리드에서의 사용 예시**      
이 그리드 구조에서는 각 셀이 어느 열에 위치하는지 aria-colindex를 사용하여 명확히 정의합니다. 이는 스크린 리더가 그리드의 셀 위치를 사용자에게 정확히 전달하는 데 도움이 됩니다.    
```sh
<div role="grid">
  <div role="row">
    <div role="gridcell" aria-colindex="1">제품명</div>
    <div role="gridcell" aria-colindex="2">가격</div>
    <div role="gridcell" aria-colindex="3">재고 상태</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-colindex="1">노트북</div>
    <div role="gridcell" aria-colindex="2">100만원</div>
    <div role="gridcell" aria-colindex="3">재고 있음</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-colindex="1">스마트폰</div>
    <div role="gridcell" aria-colindex="2">80만원</div>
    <div role="gridcell" aria-colindex="3">재고 없음</div>
  </div>
</div>
```

**시멘틱 구조의 예시**      
이 예시에서는 aria-colindex와 함께 aria-colcount, aria-rowcount 등의 속성을 사용하여 그리드의 전체 구조를 명확히 나타내고 있습니다. 이러한 정보는 스크린 리더가 그리드의 셀 위치를 정확하게 파악하고 사용자에게 전달하는 데 도움을 줍니다.    
```sh
<div role="grid" aria-colcount="4" aria-rowcount="3">
  <div role="row">
    <div role="columnheader" aria-colindex="1">제품명</div>
    <div role="columnheader" aria-colindex="2">카테고리</div>
    <div role="columnheader" aria-colindex="3">가격</div>
    <div role="columnheader" aria-colindex="4">재고</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-colindex="1">노트북</div>
    <div role="gridcell" aria-colindex="2">전자제품</div>
    <div role="gridcell" aria-colindex="3">100만원</div>
    <div role="gridcell" aria-colindex="4">있음</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-colindex="1">스마트폰</div>
    <div role="gridcell" aria-colindex="2">전자제품</div>
    <div role="gridcell" aria-colindex="3">80만원</div>
    <div role="gridcell" aria-colindex="4">없음</div>
  </div>
</div>
```

### **14. aria-colspan (property)**    
aria-colspan 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 테이블 또는 그리드 구조에서 특정 셀이 몇 개의 열을 차지하는지를 명시적으로 지정하는 데 사용됩니다. 이 속성은 HTML의 colspan 속성과 유사한 역할을 하며, 스크린 리더와 같은 보조 기술이 셀의 레이아웃을 정확하게 이해하고 사용자에게 전달할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-colspan)](https://www.w3.org/TR/wai-aria-1.2/#aria-colspan){: target="_blank"}   
[MDN Web Docs (aria-colspan)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-colspan){: target="_blank"}   


**aria-colspan 속성 값**  
- aria-colspan의 값은 1 이상의 양의 정수로, 셀이 차지하는 열의 수를 나타냅니다.    
- 예), aria-colspan="3"은 해당 셀이 세 개의 열을 차지함을 의미합니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: div, span, td, th 등 테이블 또는 그리드 셀을 나타내는 요소에서 사용됩니다.
- **연관된 역할**: gridcell, columnheader, rowheader, cell 등의 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 열 병합**: aria-colspan은 div 요소에 사용되며, HTML의 colspan 속성은 td 또는 th 요소에서만 사용됩니다. div 요소에서는 colspan 속성을 사용할 수 없습니다. 대신, aria-colspan을 사용하여 보조 기술이 셀의 병합을 올바르게 이해하도록 합니다.   
- **동적 콘텐츠**: 동적으로 생성되거나 수정되는 테이블이나 그리드에서 이 속성을 사용하여 보조 기술이 셀의 레이아웃을 정확하게 이해할 수 있도록 해야 합니다.   
- **보완적 속성 사용**: aria-colindex, aria-rowspan, aria-rowindex 등 다른 ARIA 속성과 함께 사용하여 전체 그리드 구조를 명확히 나타낼 수 있습니다.    


**단순 테이블에서의 사용 예시**      
aria-colspan 속성과 관련된 역할 및 접근성 문제를 고려할 때, 기본적으로 HTML의 table 요소, colspan 속성, 그리고 관련 태그(th, td)를 사용하여 테이블 구조를 구현하는 것이 가장 표준적이고 접근성 있는 방법입니다. aria-colspan 속성은 주로 div나 span 등의 요소로 테이블과 유사한 레이아웃을 만들 때 사용될 수 있지만, 실제로 HTML의 table 요소를 사용할 때는 role="grid" 및 aria-* 속성을 추가로 사용하는 것이 필요하지 않습니다. HTML 표준에서 제공하는 colspan 속성만으로도 접근성을 충분히 지원할 수 있습니다.   
따라서, 테이블을 구성할 때는 HTML의 기본 구조와 속성을 사용하는 것이 바람직하며, 이 경우 role 속성이나 aria-* 속성을 추가할 필요는 없습니다.      
```sh
<table>
  <thead>
    <tr>
      <th>이름</th>
      <th>나이</th>
      <th colspan="2">직업 및 국가</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>김철수</td>
      <td>30</td>
      <td colspan="2">개발자, 한국</td>
    </tr>
    <tr>
      <td>이영희</td>
      <td>25</td>
      <td colspan="2">디자이너, 미국</td>
    </tr>
  </tbody>
</table>
```

**동적으로 생성되는 그리드에서의 사용 예시**      
이 그리드 구조에서는 두 번째 셀이 두 개의 열을 병합하고 있으므로 aria-colspan="2"를 사용합니다. div 요소에서는 colspan 속성을 사용할 수 없으므로, aria-colspan만을 사용하여 보조 기술이 그리드의 구조를 정확하게 전달할 수 있도록 합니다.    
```sh
<div role="grid">
  <div role="row">
    <div role="gridcell" aria-colindex="1">제품명</div>
    <div role="gridcell" aria-colindex="2" aria-colspan="2">가격 및 재고 상태</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-colindex="1">노트북</div>
    <div role="gridcell" aria-colindex="2" aria-colspan="2">100만원, 재고 있음</div>
  </div>
</div>
```

**시멘틱 구조의 예시**      
이 예시에서는 두 번째 열이 두 개의 열을 병합하여 사용하고 있습니다. aria-colspan 속성을 사용하여 보조 기술이 그리드의 구조를 정확하게 이해할 수 있도록 도와줍니다.    
```sh
<div role="grid" aria-colcount="4" aria-rowcount="3">
  <div role="row">
    <div role="columnheader" aria-colindex="1">제품명</div>
    <div role="columnheader" aria-colindex="2" aria-colspan="2">가격 및 재고</div>
    <div role="columnheader" aria-colindex="4">카테고리</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-colindex="1">노트북</div>
    <div role="gridcell" aria-colindex="2" aria-colspan="2">100만원, 있음</div>
    <div role="gridcell" aria-colindex="4">전자제품</div>
  </div>
  <div role="row">
    <div role="gridcell" aria-colindex="1">스마트폰</div>
    <div role="gridcell" aria-colindex="2" aria-colspan="2">80만원, 없음</div>
    <div role="gridcell" aria-colindex="4">전자제품</div>
  </div>
</div>
```

### **15. aria-rowcount (property)**    
aria-rowcount 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 테이블, 그리드 또는 트리 구조에서 전체 행(row)의 총 수를 명시하는 데 사용됩니다. 이 속성은 스크린 리더와 같은 보조 기술이 테이블이나 그리드의 전체 크기를 이해하고, 사용자에게 현재 탐색 중인 항목이 전체 행 중 몇 번째에 위치하는지를 더 잘 전달할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-rowcount)](https://www.w3.org/TR/wai-aria-1.2/#aria-rowcount){: target="_blank"}   
[MDN Web Docs (aria-rowcount)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-rowcount){: target="_blank"}   


**aria-rowcount 속성 값**  
- aria-rowcount의 값은 양의 정수로, 테이블 또는 그리드 내에 있는 전체 행의 수를 나타냅니다. 전체 행 수를 알 수 없거나 동적으로 변경될 경우, -1 값을 사용하여 행 수가 불확실함을 나타낼 수 있습니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: table, div, ul, li 등 테이블, 그리드 또는 트리 구조를 나타내는 요소에서 사용됩니다.   
- **연관된 역할**: table, grid, tree, row 등의 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 행 수 제공**: aria-rowcount는 테이블이나 그리드의 전체 행 수를 정확하게 반영해야 합니다. 잘못된 값은 보조 기술 사용자에게 혼란을 줄 수 있습니다.   
- **동적 콘텐츠에서의 활용**: 동적으로 생성되거나 수정되는 테이블이나 그리드에서 이 속성을 사용하여 보조 기술이 전체 구조를 정확하게 이해할 수 있도록 해야 합니다.   
- **다른 ARIA 속성과의 조합**: aria-rowcount는 aria-colcount, aria-rowindex, aria-colindex 등 다른 ARIA 속성과 함께 사용하여 테이블 구조를 명확히 정의할 수 있습니다.    


**단순 테이블에서의 사용 예시**      
이 예시에서는 table 요소에 aria-rowcount 속성을 사용하여 테이블 내의 전체 행 수가 3개임을 명시하고 있습니다. 스크린 리더는 이 정보를 사용하여 사용자가 테이블 내에서 탐색할 때 전체 행 수를 알려줄 수 있습니다.      
```sh
<table aria-rowcount="3">
  <tr>
    <th>이름</th>
    <th>직책</th>
    <th>지역</th>
  </tr>
  <tr>
    <td>김철수</td>
    <td>개발자</td>
    <td>서울</td>
  </tr>
  <tr>
    <td>이영희</td>
    <td>디자이너</td>
    <td>부산</td>
  </tr>
</table>
```

**동적으로 생성되는 그리드에서의 사용 예시**      
이 예시에서는 div 요소에 aria-rowcount 속성을 사용하여 그리드 내의 전체 행 수가 3개임을 명시합니다. 이 정보는 스크린 리더가 그리드의 전체 구조를 이해하는 데 도움이 됩니다.    
```sh
<div role="grid" aria-rowcount="3">
  <div role="row">
    <div role="gridcell">제품명</div>
    <div role="gridcell">가격</div>
  </div>
  <div role="row">
    <div role="gridcell">노트북</div>
    <div role="gridcell">100만원</div>
  </div>
  <div role="row">
    <div role="gridcell">스마트폰</div>
    <div role="gridcell">80만원</div>
  </div>
</div>
```

**시멘틱 구조의 예시**      
이 예시에서는 HTML 표 요소 대신 div 요소를 사용하여 테이블 구조를 시멘틱하게 나타냅니다. aria-rowcount 속성은 테이블의 전체 행 수를 명확히 하여 스크린 리더가 이 구조를 올바르게 해석하고 사용자에게 전달할 수 있도록 돕습니다.    
```sh
<div role="table" aria-rowcount="3" aria-colcount="3">
  <div role="row">
    <div role="columnheader">이름</div>
    <div role="columnheader">직책</div>
    <div role="columnheader">지역</div>
  </div>
  <div role="row">
    <div role="rowheader">김철수</div>
    <div role="gridcell">개발자</div>
    <div role="gridcell">서울</div>
  </div>
  <div role="row">
    <div role="rowheader">이영희</div>
    <div role="gridcell">디자이너</div>
    <div role="gridcell">부산</div>
  </div>
</div>
```

### **16. aria-rowindex (property)**    
aria-rowindex 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 테이블이나 그리드에서 특정 행(row)의 위치를 명시하는 데 사용됩니다. 이 속성은 스크린 리더와 같은 보조 기술이 테이블 구조를 정확하게 이해하고, 현재 행이 전체 테이블이나 그리드 내에서 몇 번째에 위치하는지를 사용자에게 전달할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-rowindex)](https://www.w3.org/TR/wai-aria-1.2/#aria-rowindex){: target="_blank"}   
[MDN Web Docs (aria-rowindex)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-rowindex){: target="_blank"}   


**aria-rowindex 속성 값**  
- aria-rowindex의 값은 1 이상의 양의 정수로, 행이 전체 테이블 또는 그리드에서 몇 번째 위치에 있는지를 나타냅니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: tr, div, li 등 행을 나타내는 요소에서 사용됩니다.   
- **연관된 역할**: row, gridcell, columnheader, rowheader 등의 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 위치 명시**: aria-rowindex 속성은 테이블 또는 그리드 내에서 행의 정확한 위치를 명시해야 합니다. 잘못된 인덱스 값은 보조 기술 사용자에게 혼란을 줄 수 있습니다.   
- **동적 콘텐츠에서의 활용**: 동적으로 생성되거나 수정되는 테이블이나 그리드에서 이 속성을 사용하여 보조 기술이 행의 위치를 정확하게 이해할 수 있도록 해야 합니다.   
- **다른 ARIA 속성과의 조합**: aria-rowindex는 aria-colindex, aria-rowspan, aria-colspan 등 다른 ARIA 속성과 함께 사용하여 테이블 구조를 명확히 정의할 수 있습니다.    


**단순 테이블에서의 사용 예시**      
이 예시에서는 각 tr 요소가 aria-rowindex 속성을 통해 테이블 내에서 행의 위치를 명시하고 있습니다. 스크린 리더는 이 정보를 사용하여 사용자가 현재 탐색 중인 행이 테이블의 몇 번째 행인지 알 수 있습니다.      
```sh
<table>
  <tr aria-rowindex="1">
    <th>이름</th>
    <th>직책</th>
    <th>지역</th>
  </tr>
  <tr aria-rowindex="2">
    <td>김철수</td>
    <td>개발자</td>
    <td>서울</td>
  </tr>
  <tr aria-rowindex="3">
    <td>이영희</td>
    <td>디자이너</td>
    <td>부산</td>
  </tr>
</table>
```

**동적으로 생성되는 그리드에서의 사용 예시**      
이 예시에서는 div 요소가 aria-rowindex 속성을 사용하여 그리드 내에서 각 행의 위치를 명시합니다. 이 정보는 스크린 리더가 그리드의 구조를 이해하는 데 도움이 됩니다.    
```sh
<div role="grid">
  <div role="row" aria-rowindex="1">
    <div role="gridcell">제품명</div>
    <div role="gridcell">가격</div>
  </div>
  <div role="row" aria-rowindex="2">
    <div role="gridcell">노트북</div>
    <div role="gridcell">100만원</div>
  </div>
  <div role="row" aria-rowindex="3">
    <div role="gridcell">스마트폰</div>
    <div role="gridcell">80만원</div>
  </div>
</div>
```

**시멘틱 구조의 예시**      
이 예시에서는 HTML의 표 요소 대신 div 요소를 사용하여 테이블과 유사한 구조를 시멘틱하게 나타냅니다. aria-rowindex 속성은 스크린 리더가 각 행의 위치를 올바르게 해석하고 사용자에게 전달할 수 있도록 돕습니다.    
```sh
<div role="table" aria-colcount="3" aria-rowcount="3">
  <div role="row" aria-rowindex="1">
    <div role="columnheader">이름</div>
    <div role="columnheader">직책</div>
    <div role="columnheader">지역</div>
  </div>
  <div role="row" aria-rowindex="2">
    <div role="rowheader">김철수</div>
    <div role="gridcell">개발자</div>
    <div role="gridcell">서울</div>
  </div>
  <div role="row" aria-rowindex="3">
    <div role="rowheader">이영희</div>
    <div role="gridcell">디자이너</div>
    <div role="gridcell">부산</div>
  </div>
</div>
```

### **17. aria-rowspan (property)**    
aria-rowspan 속성은 WAI-ARIA(Accessible Rich Internet Applications)에서 제공하는 속성으로, 테이블 또는 그리드 구조에서 특정 셀이 여러 행(row)에 걸쳐 있음을 명시적으로 정의하는 데 사용됩니다. 이 속성은 HTML의 rowspan 속성과 유사하며, 스크린 리더와 같은 보조 기술이 테이블의 구조를 정확하게 이해하고 사용자에게 전달할 수 있도록 돕습니다.     
[WAI-ARIA 1.2 Specification (aria-rowspan)](https://www.w3.org/TR/wai-aria-1.2/#aria-rowspan){: target="_blank"}   
[MDN Web Docs (aria-rowspan)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-rowspan){: target="_blank"}   


**aria-rowspan 속성 값**  
- aria-rowspan의 값은 1 이상의 양의 정수로, 셀이 차지하는 행의 수를 나타냅니다.   


**연관된 Tag 및 역할**   
- **연관된 태그**: td, th 등 표 또는 그리드 셀을 나타내는 요소에서 사용됩니다.   
- **연관된 역할**: gridcell, columnheader, rowheader, cell 등의 ARIA 역할과 함께 사용됩니다.    

**사용 시 주의사항**   
- **정확한 행 병합**: aria-rowspan 속성은 HTML의 rowspan 속성과 일관되게 사용되어야 합니다. 두 속성이 서로 다른 값을 가지면 보조 기술이 테이블이나 그리드의 레이아웃을 올바르게 해석하지 못할 수 있습니다.   
- **동적 콘텐츠**: 동적으로 생성되거나 수정되는 표 또는 그리드에서 이 속성을 사용하여 보조 기술이 셀의 레이아웃을 정확하게 이해할 수 있도록 해야 합니다.   
- **보완적 속성 사용**: aria-colspan, aria-rowindex, aria-colindex 등 다른 ARIA 속성과 함께 사용하여 전체 표 구조를 명확히 나타낼 수 있습니다.    


**단순 테이블에서의 사용 예시**      
이 예시에서는 td 요소가 rowspan과 aria-rowspan 속성을 통해 두 개의 행에 걸쳐 있음을 명시하고 있습니다. 스크린 리더는 이 정보를 사용하여 테이블의 구조를 올바르게 해석하고 사용자에게 전달합니다. 이 방법은 표준 HTML의 rowspan 속성을 사용하면서 접근성을 강화하는 aria-rowspan을 함께 사용한 예시입니다.      
```sh
<table>
  <tr>
    <th>이름</th>
    <th>직책</th>
    <th>지역</th>
  </tr>
  <tr>
    <td rowspan="2" aria-rowspan="2">김철수</td>
    <td>개발자</td>
    <td>서울</td>
  </tr>
  <tr>
    <td>디자이너</td>
    <td>부산</td>
  </tr>
</table>
```

**동적으로 생성되는 그리드에서의 사용 예시**      
이 예시에서는 div 요소가 aria-rowspan 속성을 사용하여 그리드 내에서 두 개의 행에 걸쳐 있음을 명시합니다. 이 정보는 스크린 리더가 그리드의 구조를 이해하는 데 도움이 됩니다. 동적 콘텐츠에서 유용하게 사용되며, HTML table 요소를 사용하지 않고도 접근성을 강화할 수 있습니다.    
```sh
<div role="grid">
  <div role="row">
    <div role="gridcell" aria-rowspan="2">제품명</div>
    <div role="gridcell">가격</div>
  </div>
  <div role="row">
    <div role="gridcell">100만원</div>
  </div>
  <div role="row">
    <div role="gridcell">스마트폰</div>
    <div role="gridcell">80만원</div>
  </div>
</div>
```

**시멘틱 구조의 예시**      
이 예시에서는 HTML의 표 요소 대신 div 요소를 사용하여 테이블과 유사한 구조를 시멘틱하게 나타냅니다. aria-rowspan 속성은 스크린 리더가 두 개의 행에 걸친 셀을 올바르게 해석하고 사용자에게 전달할 수 있도록 돕습니다. 이 구조는 동적 콘텐츠와 복잡한 레이아웃에서 유용하게 사용될 수 있습니다.    
```sh
<div role="table" aria-colcount="3" aria-rowcount="3">
  <div role="row">
    <div role="columnheader">이름</div>
    <div role="columnheader">직책</div>
    <div role="columnheader">지역</div>
  </div>
  <div role="row">
    <div role="rowheader" aria-rowspan="2">김철수</div>
    <div role="gridcell">개발자</div>
    <div role="gridcell">서울</div>
  </div>
  <div role="row">
    <div role="gridcell">디자이너</div>
    <div role="gridcell">부산</div>
  </div>
</div>
```


## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  