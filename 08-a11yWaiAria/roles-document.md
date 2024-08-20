# WAI-ARIA 역할

## Document Structure Roles (문서 구조 역할)
> **Document Structure Roles**는 웹 페이지나 애플리케이션의 콘텐츠를 논리적이고 의미 있는 방식으로 구성하는 데 사용됩니다. 이 역할은 문서의 주요 부분을 정의하고, 보조 기술이 이 구조를 이해할 수 있도록 도와줍니다. Document Structure 역할은 페이지를 효율적으로 탐색할 수 있도록 콘텐츠를 구조화하는 데 필수적입니다.   
[W3C ARIA Document Structure Roles](https://www.w3.org/TR/wai-aria-1.2/#document_structure_roles){: target="_blank"}   


### **1. application 역할**    
application 역할은 웹 페이지의 특정 영역이 일반적인 웹 콘텐츠와는 다른, 고도의 상호작용이 필요한 애플리케이션처럼 동작함을 보조 기술에 알리는 데 사용됩니다. 이 역할은 웹 페이지에서 데스크탑 애플리케이션과 유사한 상호작용을 제공하는 UI 요소에 사용되며, 사용자에게 더 복잡한 기능을 제공하기 위해 사용됩니다.   
[W3C ARIA application](https://www.w3.org/TR/wai-aria-1.2/#application){: target="_blank"}   
[MDN ARIA application](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/application_role){: target="_blank"}   

**기본 설명**  
- application 역할은 특정 영역이 웹 애플리케이션처럼 동작하도록 정의합니다. 이는 일반적인 문서 탐색 모드 대신, 애플리케이션 모드에서 더 복잡한 상호작용을 지원합니다.    
- 이 역할이 사용된 영역에서는 보조 기술이 일반적인 문서 탐색 명령(예: 헤딩, 링크 탐색 등)을 제한하고, 대신 애플리케이션의 상호작용에 집중할 수 있도록 합니다.    
- application 역할은 특히 키보드 중심의 상호작용, 사용자 지정 위젯, 복잡한 사용자 인터페이스를 구현할 때 유용합니다.    

**사용 시 주의사항**   
- application 역할은 주로 웹 페이지의 특정 영역이 애플리케이션처럼 동작해야 할 때 사용됩니다. 이 역할이 적용되면 보조 기술은 일반적인 문서 탐색 명령을 제한하고, 애플리케이션의 상호작용에 집중하게 됩니다.   
- 이 역할은 사용자가 페이지의 다른 부분에서 벗어나지 않고 복잡한 상호작용을 수행할 수 있도록 설계되어야 합니다.
- application 역할이 적용된 영역은 키보드 내비게이션이 원활히 작동하도록 설계되어야 하며, 적절한 aria-labelledby, aria-describedby 속성을 사용하여 레이블과 설명을 제공해야 합니다.
- 이 역할은 문서 탐색을 방해할 수 있으므로, 필요할 때만 제한적으로 사용하는 것이 좋습니다. 애플리케이션 모드로 전환되면 보조 기술 사용자들이 문서의 다른 부분을 탐색하는 데 어려움을 겪을 수 있습니다.

**상속된 상태 및 속성**   
- aria-labelledby: 애플리케이션 영역의 레이블을 참조합니다.    
- aria-describedby: 애플리케이션 영역에 대한 추가 설명을 제공합니다.    
- aria-live: 애플리케이션 내에서 실시간으로 업데이트되는 정보를 사용자에게 전달할 수 있습니다.    


**기본 application 역할 사용 예시**
이 예시는 웹 애플리케이션 내에서 계산기와 같은 상호작용 요소를 구현한 것입니다. application 역할을 사용해, 보조 기술이 이 영역을 일반적인 문서로 인식하지 않고, 애플리케이션처럼 동작하도록 합니다. 사용자는 계산기 버튼을 키보드로 탐색하고, 입력할 수 있습니다.    
```sh
<div role="application">
  <h2>Interactive Calculator</h2>
  <div id="calc-display" aria-label="Calculator Display">0</div>
  <button>1</button>
  <button>2</button>
  <button>3</button>
  <button>+</button>
  <button>=</button>
</div>
```

**application 역할이 적용된 복잡한 UI 예시**
이 예시는 사용자 지정 스프레드시트 UI를 application 역할과 함께 구현한 것입니다. 사용자는 키보드를 사용하여 스프레드시트 셀 간을 이동할 수 있으며, 보조 기술은 이 영역을 일반적인 웹 페이지의 일부로 인식하지 않고, 애플리케이션처럼 처리합니다.    
```sh
<div role="application" aria-labelledby="app-title">
  <h1 id="app-title">Custom Spreadsheet</h1>
  <div role="grid" aria-label="Spreadsheet Grid">
    <div role="row">
      <div role="gridcell" tabindex="0">A1</div>
      <div role="gridcell" tabindex="-1">B1</div>
      <div role="gridcell" tabindex="-1">C1</div>
    </div>
    <div role="row">
      <div role="gridcell" tabindex="-1">A2</div>
      <div role="gridcell" tabindex="-1">B2</div>
      <div role="gridcell" tabindex="-1">C2</div>
    </div>
  </div>
</div>
```

**고급 상호작용이 필요한 애플리케이션 예시**
이 예시는 드로잉 애플리케이션을 구현한 것으로, 사용자에게 그리기 도구를 선택하고, 캔버스에 그림을 그릴 수 있는 기능을 제공합니다. application 역할은 보조 기술이 이 영역을 복잡한 상호작용을 필요로 하는 애플리케이션으로 인식하게 합니다.    
```sh
<div role="application" aria-labelledby="app-label">
  <h1 id="app-label">Drawing Application</h1>
  <canvas id="drawing-canvas" aria-label="Drawing Canvas"></canvas>
  <div>
    <button aria-label="Select Pencil Tool">Pencil</button>
    <button aria-label="Select Eraser Tool">Eraser</button>
  </div>
</div>
```


다음 역할은 페이지에서 콘텐츠를 구성하는 구조를 설명합니다. 문서 구조는 일반적으로 대화형이 아닙니다.

application
article
blockquote
caption
cell
columnheader
definition
deletion
directory
document
emphasis
feed
figure
generic
group
heading
img
insertion
list
listitem
math
meter
none
note
paragraph
presentation
row
rowgroup
rowheader
separator (when not focusable)
strong
subscript
superscript
table
term
time
toolbar
tooltip

## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  