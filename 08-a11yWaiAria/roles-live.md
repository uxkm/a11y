# WAI-ARIA 역할

## Widget Roles (위젯 역할)
> **Widget Roles**은 다른 역할을 정의하는 데 사용되는 개념적 역할입니다. 이러한 역할들은 웹 페이지에 직접 사용되지 않으며, 구체적인 역할을 정의하고 이들 간의 관계를 설명하고,        
웹 접근성을 높이는 데 중요한 역할을 합니다. 올바르게 이해하고 사용하여 웹 콘텐츠의 접근성을 개선할 수 있습니다.

### **1. button (버튼 역할)**    
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

다음 역할은 라이브 지역이며 라이브 지역 특성에 의해 수정될 수 있습니다.

alert
log
marquee
status
timer



## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
   