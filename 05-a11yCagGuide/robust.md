## KWCAG 항목별 준수 가이드

**견고성 (Robust)**
>**견고성 (Robust)** 은 사용자가 콘텐츠를 이용할 수 있도록 기술에 영향을 받지 않아야 함을 의미한다.
KWCAG 2.1, KWCAG 2.2 **견고성**은 문법 준수, 웹 애플리케이션 접근성의 **2가지 지침**으로 구성되어 있다. 

### 8.1. 문법 준수

#### 8.1.1. 마크업 오류 방지
>**마크업 언어의 요소는 열고 닫음, 중첩 관계 및 속성 선언에 오류가 없어야 한다.**   
마크업 언어로 작성된 콘텐츠는 해당 마크업 언어의 문법을 최대한 준수하여 제공하는 것이 바람직하다. 특히 요소의 열고 닫음, 중첩 관계의 오류가 없도록 제공해야 한다. 또한 요소의 속성도 마크업 문법을 최대한 준수하여 제공하는 것이 바람직하다.    
WCAG 2.1 부분 참조.   
[4.1.1 Parsing (Obsolete and removed) (Level A)](https://www.w3.org/TR/WCAG21/#parsing){: target="_blank"}


**고려 사항**   
1. 요소의 열고 닫음 일치   
   - 마크업 언어로 작성된 콘텐츠는 표준에서 특별히 정한 경우를 제외하고는 시작 요소와 끝나는 요소가 정의되어야 한다.   
2. 요소의 중첩 방지   
   - 시작 요소와 끝나는 요소의 나열 순서는 포함 관계가 어긋나지 않아야 한다.    
3. 중복된 속성 사용 금지   
   - 하나의 요소 안에서 속성을 중복하여 선언하지 않아야 한다.   
4. id 속성 값 중복 선언 금지   
   - 하나의 마크업 문서에서는 같은 id 값을 중복하여 선언하지 않아야 한다.   

**기대 효과**   
- 시작 요소와 끝나는 요소가 잘 대응되고 요소 간의 포함 관계가 어긋나지 않도록 웹 페이지의 마크업 문서를 구성하면, 웹 브라우저나 보조 기술이 작동을 멈추지 않고 콘텐츠를 명확히 전달할 수 있다.   
- 콘텐츠에 필요한 속성의 누락이나 중복된 경우를 없애 콘텐츠의 일부 기능이 누락되는 것을 방지할 수 있다.   

### 8.2. 웹 애플리케이션 접근성

#### 8.2.1. 웹 애플리케이션 접근성 준수
>**콘텐츠에 포함된 웹 애플리케이션은 접근성이 있어야 한다.**   
웹 콘텐츠를 사용하는 데 필요한 플러그인 또는 웹 페이지의 기능을 실행하는 데 필요한 웹 애플리케이션은 사용자가 웹 페이지에 접근하여 사용하는 것을 방해하지 않아야 한다. 웹 애플리케이션은 다음에 설명한 모든 요구사항을 적용하여 제작하여야 한다.
WCAG 2.1 부분 참조.   
[4.1.2 Name, Role, Value (Level A)](https://www.w3.org/TR/WCAG21/#name-role-value){: target="_blank"}

**고려 사항**   
1. 접근성 프로그래밍 인터페이스 사용 지원   
   - 웹 애플리케이션은 운영체제 또는 플랫폼이 제공하는 접근성 프로그래밍 인터페이스를 사용하여 제작되어야 한다. 그렇지 않으면 보조 기술이 웹 애플리케이션의 접근성 기능을 지원하지 못하는 경우가 발생할 수 있다.    
2. 접근성 프로그래밍 인터페이스 대체 수단 제공   
   - 웹 애플리케이션을 구현하는 과정에서 운영체제(플랫폼 포함)가 제공하는 접근성 프로그래밍 인터페이스가 정의되지 않은 새로운 기능을 구현할 경우에는 그 기능의 명칭, 역할, 상태 및 값에 관한 정보를 운영체제(또는 플랫폼)의 접근성 프로그래밍 인터페이스로 전달하도록 구현함으로써 보조 기술이 그 정보를 이용할 수 있게 해야 한다.    
3. 보조 기술 지원   
   - 국내의 보조 기술로 접근이 불가능한 웹 애플리케이션은 가능한 한 사용하지 않는 것이 좋으며, 꼭 사용해야 하는 경우에는 해당 웹 애플리케이션에 대한 대체 수단을 제공해야 한다.    


**기대 효과**   
- 웹 애플리케이션이 접근성을 제공할 경우 보조 기술이 웹 애플리케이션과 상호작용이 가능하므로 보조 기술 사용자가 웹 애플리케이션을 활용할 수 있다.   
- 웹 애플리케이션에 적용하려는 기능이 플랫폼 접근성 프로그래밍 인터페이스를 지원하지 못하더라도 필수적인 접근성 정보를 플랫폼 접근성 프로그래밍 인터페이스를 통하여 보조 기술로 제공할 수 있게 되므로 새롭고 접근성이 있는 기술의 개발이 가능하다.   


#### 참조
- [W3C WCAG 1.0](https://www.w3.org/TR/WCAG10/){: target="_blank"}
- [W3C WCAG 2.0](https://www.w3.org/TR/WCAG20/){: target="_blank"}
- [W3C WCAG 2.1](https://www.w3.org/TR/WCAG21/){: target="_blank"}
- [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/){: target="_blank"}
- [W3C WCAG 3.0 Draft](https://www.w3.org/TR/2021/WD-wcag-3.0-20210121/){: target="_blank"}
- [W3C WCAG 2.1 한국어](http://www.kwacc.or.kr/WAI/wcag21/){: target="_blank"}
- [W3C Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/){: target="_blank"}
- [W3C WCAG2 ko](https://www.w3.org/WAI/standards-guidelines/ko#wcag2){: target="_blank"}
- [W3C Accessibility Guidelines Working Group](https://www.w3.org/WAI/GL/){: target="_blank"}
- [W3C W3C 접근성의 4가지 원칙](https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head){: target="_blank"}
- [MDN 웹 컨텐츠 접근성 지침 이해하기](https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG){: target="_blank"}
- [MDN 접근성이란?](https://developer.mozilla.org/ko/docs/Learn/Accessibility/What_is_accessibility#accessibility_guidelines_and_the_law){: target="_blank"}
- [NULI WCAG 2.2에서 변경된 사항](https://nuli.navercorp.com/community/article/1133181){: target="_blank"}
- [brunch WCAG 2.2 작업 초안](https://brunch.co.kr/@snclab/55){: target="_blank"}
- [GITBOOK WCAG 2.1](https://a11y.gitbook.io/wcag/international-standards){: target="_blank"}
- [WAI 문서로 접근성 이해하기](https://iyu88.github.io//a11y/2023/12/24/web-accessibility-1.html){: target="_blank"}
- [deque blog WCAG 2.1](https://www.deque.com/blog/wcag-2-1-what-is-next-for-accessibility-guidelines/){: target="_blank"}
- [웹접근성 국가표준 개정 소개](https://seculayerlab.tistory.com/m/48){: target="_blank"}

- [한국형 웹 콘텐츠 접근성 지침 2.2](https://www.samsungfashion.com/webacc.do){: target="_blank"}
- [AOA GITBOOK](https://aoa.gitbook.io/skymimo/undefined){: target="_blank"}


---
# INDEX
1. [접근성이란?](01-a11yStart/start.md)  
2. [장애인차별금지법 관련 지침](02-a11yGuideline/guideline.md)  
3. [접근성 인증 마크](03-a11yMark/mark.md)  
4. [웹 콘텐츠 접근성 가이드라인](04-a11yCag/wcag.md)   
   4.1. [WCAG](04-a11yCag/wcag.md)   
   4.2. [KWCAG](04-a11yCag/kwcag.md)   
      - [웹 접근성](04-a11yCag/kwcag.md)   
      - [모바일 접근성](04-a11yCag/kwcagMobile.md)   
      - [무인정보단밀기 접근성](04-a11yCag/kwcagKiosk.md)   
5. [KWCAG 항목별 준수 가이드](05-a11yCagGuide/perceivable.md)   
   - [인식의 용이성(Perceivable)](05-a11yCagGuide/perceivable.md)   
   - [운용의 용이성(Operable)](05-a11yCagGuide/operable.md)   
   - [이해의 용이성(Understandable)](05-a11yCagGuide/understandable.md)   
   - [견고성(Robust)](05-a11yCagGuide/robust.md)   
6. [KWCAG 체크리스트](06-a11yCheck/web.md)   
   - [웹 접근성](06-a11yCheck/web.md)   
   - [모바일 접근성](06-a11yCheck/mobile.md)   
   - [무인정보단말기 접근성](06-a11yCheck/kiosk.md)   
7. [KWCAG 콘텐츠 제작 방법](07-a11yDevelop/develop.md)   
   == KWCAG 콘텐츠 제작 방법 및 예시 설명 ==   
8. [WAI-ARIA 가이드라인](08-a11yAriaGuide/ariaguide.md)   
9. [WAI-ARIA 구조](09-a11yAria/role.md)   
   - [역할(Role)](09-a11yAria/role.md)   
   - [상태(Attributes) 및 속성(States)](09-a11yAria/states.md)   
10. [ARIA 역할(Role)](10-a11yRole/01-alert.md)   
11. [ARIA 상태(Attributes) 및 속성(States)](11-a11yAria/01-activedescendant.md)   
12. [접근성(a11y) 참조](13-a11yBookmark/bookmark.md)   