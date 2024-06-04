# WAI-ARIA란?
> **WAI-ARIA (Web Accessibility Initiative - Accessible Rich Internet Applications)** 는 웹 콘텐츠와 웹 응용 프로그램의 접근성을 향상시키기 위해 W3C(Web Accessibility Initiative)에서 개발한 기술 사양입니다.    
> - 동적인 콘텐츠와 고급 사용자 인터페이스 컨트롤을 대상으로 합니다.    
> - 특히 스크린 리더 사용자와 같은 보조 기술 사용자가 웹 애플리케이션을 효과적으로 사용할 수 있도록 돕습니다.   
> - HTML에 추가적인 속성을 제공하여 접근성을 높입니다. 이 속성들은 웹 요소의 역할, 상태, 속성을 설명하여 보조 기술이 이를 더 잘 이해하고 사용자에게 전달할 수 있도록 합니다.   
[W3C WAI-ARIA 개요 참조](https://www.w3.org/WAI/standards-guidelines/aria/){: target="_blank"}


<figure style="text-align:center">
  <a href="https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg" target="_blank" title="새 창 열림"><img src="https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg" alt="Class diagram of the relationships described in the role data model."></a>
  <figcaption><strong>역할 데이터 모델에 설명된 관계 클래스 다이어그램 (크게 보기)</strong></figcaption>
</figure>


## 1. 주요 역할(Role)
> 역할(role)은 웹 요소의 목적이나 종류를 정의합니다.  
WAI-ARIA는 다양한 역할을 정의하여 스크린 리더가 요소를 더 잘 이해할 수 있게 합니다.    
예) role="button"은 해당 요소가 버튼임을 명시합니다.  

주요 역할 예시:

button: 버튼 역할
checkbox: 체크박스 역할
dialog: 대화 상자 역할
navigation: 내비게이션 역할
관련 링크:

WAI-ARIA Roles

1. 속성(Properties)
정의: 속성은 역할을 보완하여 요소의 추가적인 특성을 설명합니다.

상세 설명: 속성은 요소의 상태나 추가 정보를 제공합니다. 예를 들어 aria-labelledby 속성은 특정 요소가 레이블로 지정된 다른 요소를 참조하도록 합니다.

주요 속성 예시:

aria-labelledby: 요소를 설명하는 레이블의 ID를 참조
aria-describedby: 요소를 설명하는 추가 정보의 ID를 참조
aria-hidden: 요소를 스크린 리더에서 숨김
관련 링크:

WAI-ARIA Properties
4. 상태 및 속성(State and Properties)
정의: 상태 및 속성은 요소의 동적 특성과 상태를 설명합니다.

상세 설명: 상태와 속성은 요소의 현재 상태(예: 활성화됨, 선택됨 등)를 설명합니다. 예를 들어 aria-checked 속성은 체크박스의 선택 상태를 나타냅니다.

주요 상태 및 속성 예시:

aria-checked: 체크박스의 선택 상태
aria-expanded: 요소가 확장되었는지 여부
aria-disabled: 요소가 비활성화되었는지 여부
관련 링크:

WAI-ARIA State and Properties
5. 실무 적용 사례
정의: WAI-ARIA를 실제 웹 사이트와 애플리케이션에 적용하는 방법과 사례.

상세 설명: 실무 적용에서는 WAI-ARIA 속성을 사용하여 웹 요소의 접근성을 개선하는 방법을 설명합니다. 예를 들어, 동적 메뉴나 모달 창을 구현할 때 WAI-ARIA를 적용하여 스크린 리더 사용자가 더 쉽게 탐색할 수 있게 합니다.

관련 링크:

Practical ARIA Examples
6. 관련 도구 및 리소스
정의: WAI-ARIA 적용을 돕는 도구와 추가 학습을 위한 리소스.

상세 설명: 접근성 검토 도구와 학습 자료를 소개합니다. 이러한 도구는 WAI-ARIA 적용 상태를 확인하고, 웹 콘텐츠의 접근성을 평가하는 데 유용합니다.

관련 도구 예시:

WAVE: Web Accessibility Evaluation Tool
AXE: Accessibility Testing Tools
관련 링크:

W3C ARIA Authoring Practices
MDN Web Docs on ARIA

## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   