# WAI-ARIA 상태 및 속성

## Drag-and-Drop Attributes (드래그 앤 드롭 속성)
>    
[W3C ARIA Drag-and-Drop Attributes](https://www.w3.org/TR/wai-aria-1.2/#attrs_dragdrop){: target="_blank"}   


### **1. aria-dropeffect**    
banner 역할은 기본적으로 시멘틱 마크업 사용을 권장하며 웹 페이지의 상단에 위치하는 주목할 만한 영역을 나타냅니다. 이 역할은 일반적으로 웹사이트의 로고, 제목, 주요 탐색 링크 등을 포함하는 페이지의 헤더 부분에 사용됩니다. banner 역할은 사이트 전체에 걸쳐 일관되게 반복되는 콘텐츠를 나타내며, 사용자가 페이지의 주요 제목과 탐색 메뉴를 쉽게 찾을 수 있도록 돕습니다.   
[W3C ARIA aria-autocomplete](https://www.w3.org/TR/wai-aria-1.2/#aria-autocomplete){: target="_blank"}   
[MDN ARIA states and properties : aria-autocomplete](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-autocomplete){: target="_blank"}   

**기본 설명**  
- ㅇㅇㅇ   


**사용 시 주의사항**   
- ㅇㅇㅇ   

**상속된 상태 및 속성**   
- ㅇㅇㅇ    


**잘못된 예시**
이 예시는 한 페이지에 두 개의 banner 역할을 사용하고 있습니다. banner 역할은 페이지에 하나만 사용해야 하며, 중복 사용은 접근성을 저해할 수 있습니다.    
```sh

```

**올바른 예시**
이 예시는 하나의 banner 역할을 사용하여 페이지의 주요 헤더를 명확하게 정의합니다. 이 헤더는 사이트의 제목, 로고, 주요 탐색 메뉴를 포함하고 있습니다.    
```sh

```

**(권장) 시멘틱 사용 예시**
이 예시는 시멘틱 요소인 &lt;header&gt;를 사용하여 banner 역할을 자연스럽게 수행합니다. HTML5 시멘틱 마크업을 사용하면, 보조 기술은 자동으로 이 영역을 페이지의 헤더로 인식합니다. 추가적인 ARIA 속성 없이도 접근성이 보장되며, 코드의 가독성도 높아집니다.    
```sh

```
aria-dropeffect
aria-grabbed


## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  