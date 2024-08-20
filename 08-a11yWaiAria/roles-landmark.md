# WAI-ARIA 역할

## Landmark Roles (랜드마크 역할)
> **Landmark Roles**는 웹 페이지에서 주요 영역을 식별하고 쉽게 탐색할 수 있도록 도와주는 ARIA 역할입니다. 이 역할들은 페이지의 중요한 섹션을 구분하여 보조 기술을 사용하는 사용자들이 빠르게 페이지의 주요 콘텐츠로 이동할 수 있도록 합니다. 이러한 역할들은 웹 페이지의 구조를 정의하고, 페이지 내에서 중요한 영역을 강조하는 데 사용됩니다.   
[W3C ARIA Landmark Roles](https://www.w3.org/TR/wai-aria-1.2/#landmark_roles){: target="_blank"}   


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

다음 역할은 탐색 랜드마크로 의도된 페이지의 영역입니다. 이러한 모든 역할은 기본 형식에서 상속되며 역할 특성 [ROLE-ATTRIBUTE]에서 가져옵니다. 역할은 WAI-ARIA 역할 모델의 일부로 명확하게 만들기 위해 여기에 포함되어 있습니다.landmark

banner
complementary
contentinfo
form
main
navigation
region
search



## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
   