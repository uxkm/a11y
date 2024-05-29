## KWCAG 항목별 준수 가이드

**이해의 용이성 (Understandable)**
>**이해의 용이성 (Understandable)** 은 사용자가 장애 유무 등에 관계없이 웹 사이트에서 제공하는 콘텐츠를 이해할 수 있도록 제공하는 것을 의미한다.    
KWCAG 2.1 **이해의 용이성**은 가독성, 예측 가능성, 콘텐츠의 논리성, 입력 도움의 **4 가지 지침**으로 구성되어 있다.       
KWCAG 2.2 **이해의 용이성**은 가독성, 예측 가능성, 입력 도움의 **3가지 지침**으로 구성되어 있다.   

### 7.1. 가독성

#### 7.1.1. 기본 언어 표시
>**주로 사용하는 언어를 명시해야 한다.**   
웹 브라우저는 웹 페이지를 구성하는 텍스트 콘텐츠의 언어 정보를 바탕으로 텍스트 콘텐츠를 화면에 표시하거나 보조 기술로 전달한다. 다국어를 지원하는 화면 낭독 프로그램을 사용하는 경우, 텍스트 콘텐츠의 언어 정보를 화면 낭독 프로그램으로 전달하여 정확한 발음으로 읽어주도록 제어하기도 한다. 따라서 웹 페이지의 기본 언어는 정확히 정의해야 한다.       
WCAG 2.1 부분 참조.   
[3.1.1 Language of Page (Level A)](https://www.w3.org/TR/WCAG21/#language-of-page){: target="_blank"}   


**고려 사항**    
1. 웹 페이지의 언어 명시   
   - 웹 페이지에서 제공하는 콘텐츠에 적용되는 기본 언어를 반드시 정의해야 한다.


**기대 효과**    
- 화면 낭독 프로그램과 점역 프로그램과 같은 보조 기술은 웹 페이지의 기본 언어를 인식하여 자동적으로 음성 모듈을 선택하거나 해당 언어에 적합한 점역 방법을 선택할 수 있는 편리함이 있다.   

### 7.2. 예측 가능성

#### 7.2.1. 사용자 요구에 따른 실행
>**사용자가 의도하지 않은 기능(새 창, 초점에 의한 맥락 변화 등)은 실행되지 않아야 한다.**     
컨트롤이나 사용자 입력은 초점을 받았을 때에 의도하지 않는 기능이 자동적으로 실행되지 않도록 콘텐츠를 개발해야 한다.     
즉, 컨트롤이나 사용자 입력의 기능은 사용자의 마우스 클릭이나 키보드 조작에 의하여 실행되어야 한다. 특히 사용자가 인지하지 못한 상황에서 새 창, 팝업 창 등이 열리지 않아야 한다.    
WCAG 2.1 부분 참조.   
[3.2.1 On Focus (Level A)](https://www.w3.org/TR/WCAG21/#on-focus){: target="_blank"}    
[3.2.2 On Input (Level A)](https://www.w3.org/TR/WCAG21/#on-input){: target="_blank"}   


**고려 사항**    
1. 초점에 의한 맥락 변화    
   - 웹 콘텐츠를 구성하는 컨트롤이 초점을 받았을 경우, 사용자가 의도하지 않은 기능이 실행되지 않아야 한다. 단, 기능의 실행이 아니라 초점을 받은 요소의 색깔이 반전되거나 테두리가 생기는 것과 같은 시각적인 변화, 또는 사용자 제어가 이동하지 않은 상태에서 나타나는 추가 정보 등은 초점에 의한 맥락 변화를 일으키는 기능의 실행으로 간주하지 않는다.    
    다음은 종종 발생하는 대표적인 오류들이다.    
     - 온라인 서식이 자동적으로 제출됨.
     - 새 창이 열림.
     - 드롭다운 메뉴가 열림만으로 특정 메뉴 항목이 실행됨.   
     - 풀다운 메뉴를 사용하는 콘텐츠에서 초점을 받는 것만으로 특정 메뉴의 기능이 실행됨.   
     - 사용자 제어(초점)가 다른 컨트롤로 이동하거나 사라지거나 또는 그 위치를 예측할 수 없음.    
2. 입력에 따른 변화   
   - 사용자가 선택할 수 있는 컨트롤(예 : 콤보 상자, 라디오 버튼, 체크 상자 등)에서 어떤 항목을 선택하는 경우, 해당 항목이 의미하는 기능이 실행되거나 서식 제출이 일어나지 않아야 한다. 실제로 해당 기능이 실행되거나 서식 제출이 일어나는 것은 사용자가 선택할 수 있는 컨트롤과 함께 제공되는 실행 버튼을 활성화(클릭)하였을 때 비로소 실행되어야 한다. 단, 기능의 실행이 아니라 초점을 받은 사용자 입력 또는 컨트롤의 색깔이 반전되거나 테두리가 생기는 것과 같은 시각적인 변화, 또는 사용자 제어(초점)가 이동하지 않은 상태에서 나타나는 추가 정보 등은 입력 변화에 따른 기능의 실행으로 간주하지 않는다.   
3. 새 창/팝업 창   
   - 사용자가 예측할 수 없는 상황에서 새 창을 열어 정보를 전달해서는 안 된다.   
4. 레이어 팝업   
   - 레이어 팝업은 콘텐츠의 논리적 초점 이동 및 콘텐츠의 선형 구조를 위반할 가능성이 많으므로 사용하지 않는 것이 바람직하다.   
5. 새 창/팝업 창/레이어 팝업의 닫음   
   - 새 창/팝업 창/레이어 팝업에 초점이 있을 경우 새 창/팝업 창/레이어 팝업을 닫거나 종료 버튼을 클릭하였을 경우, 해당 창 또는 팝업 등이 종료되어야 한다. 사용자가 화면에 나타난 새 창/팝업 창/레이어 팝업을 닫거나 종료하도록 요구하였음에도 불구하고 해당 창 또는 팝업 등이 종료되지 않으면 사용자는 매우 당황하게 된다. 특히 레이어 팝업의 경우에 이러한 혼란이 가중될 수 있다.    

**기대 효과**    
- 시각 장애, 지적 장애 또는 지체 장애가 있는 사람들도 초점 및 문맥의 변화를 이해할 수 있게 된다.   
- 사용자에게 미리 새 창 열림을 경고하면 뒤로 가기 버튼이 더 이상 예상처럼 동작하지 않는다는 사실을 알 수 있으므로 이용하는데 따른 혼란이 줄어든다.   


### 7.3. 콘텐츠의 논리성

#### 7.3.1. 콘텐츠의 선형 구조
>**콘텐츠는 논리적인 순서로 제공해야 한다.**   
콘텐츠는 보조 기술 사용자가 맥락을 이해할 수 있도록 논리적인 순서로 제공해야 한다.    
WCAG 2.1 부분 참조.   
[1.3.2 Meaningful Sequence (Level A)](https://www.w3.org/TR/WCAG21/#meaningful-sequence){: target="_blank"}   


**고려 사항**    
1. 콘텐츠의 선형 구조 유지   
   - 웹 페이지를 구성하는 모든 콘텐츠는 사용자가 그 내용을 이해할 수 있도록 선형 구조로 작성되어야 한다.    
2. 내용, 표현 및 기능 분리   
   - 브라우저 화면에 표시되는 콘텐츠의 순서는 웹 페이지에 수록된 콘텐츠의 선형 구조와 항상 같은 것은 아니다.    
     예) 스타일 시트를 사용하면 웹 페이지를 구성하는 콘텐츠의 순서를 변경하지 않고도 화면에 표시되는 콘텐츠의 배치를 임의로 변경할 수 있다.    
     따라서 웹 페이지를 구성하는 콘텐츠의 나열 순서는 그 맥락을 이해할 수 있도록 논리적으로 구성해야 한다. 시각적으로 배치를 변경해야 하는 경우에도 콘텐츠의 선형 구조는 유지되어야 한다.   


**기대 효과**    
- 콘텐츠의 선형 구조가 논리적인 콘텐츠는 지적 장애, 언어 장애 및 학습 장애가 있는 사용자들이 콘텐츠를 이해하는 데 도움을 준다.    
- 콘텐츠의 선형 구조가 논리적인 웹 콘텐츠는 스타일 시트(style sheet)를 바꾸거나 기능을 제거하더라도 그 내용을 순서대로 읽어 문서의 의미를 이해하기가 쉽다.   


#### 7.3.2. 표의 구성
>**표는 이해하기 쉽게 구성해야 한다.**   
표를 제공할 경우, 표의 이해를 돕기 위한 내용 및 구조에 대한 정보를 제공해야 한다.   
WCAG 2.1 부분 참조.    
[1.3.1 Info and Relationships (Level A)](https://www.w3.org/TR/WCAG21/#info-and-relationships){: target="_blank"}   


**고려 사항**    
1. 표 정보 제공
   - 데이터를 표로 구성할 경우, 표의 내용, 구조 등을 이해할 수 있도록 정보를 제공하여 표의 이용 방법을 예측할 수 있도록 한다.    
2. 표의 구성   
   - 표의 내비게이션을 위하여 표의 셀은 제목 셀과 데이터 셀이 구분되도록 구성해야 한다.   

**기대 효과**    
- 제목 셀과 데이터 셀이 구분되도록 구현한 데이터 테이블은 시각 장애인에게 데이터 셀에 대한 제목 셀의 내용 또는 제목 셀과의 관계를 알려주므로 내용 파악이 쉽다.   


### 7.4. 입력의 도움

#### 7.4.1. 레이블(label) 제공
>**사용자 입력에는 대응하는 레이블(label)을 제공해야 한다.**    
사용자 입력은 용도를 이해할 수 있도록 레이블(label)을 제공해야 한다.    
WCAG 2.1 부분 참조.    
[3.3.2 Labels or Instructions (Level A)](https://www.w3.org/TR/WCAG21/#labels-or-instructions){: target="_blank"}   


**고려 사항**    
1. 사용자 입력에 대응하는 레이블 제공
   - 사용자 입력의 근처에 사용법을 알려주는 레이블(label)을 보조 기술이 알 수 있도록 해당 컨트롤과 대응하여 제공해야 한다. 레이블(label)과 사용자 입력 간의 관계를 보조 기술이 인식할 수 있도록 대응시키지 않고 단순히 텍스트로만 제공할 경우, 보조 기술은 해당 사용자 입력에 대한 레이블(label)을 인식할 수 없다.   

**기대 효과**    
- 레이블(label)과 사용자 입력 간의 관계를 보조 기술이 인식할 수 있도록 대응시키면 화면 낭독 프로그램을 사용하는 시각 장애인에게 해당 컨트롤이 어떤 용도로 사용되는지를 알려줄 수 있으므로 잘못된 데이터의 입력을 방지할 수 있다.   



#### 7.4.2. 오류 정정
>**입력 오류를 정정할 수 있는 방법을 제공해야 한다.**    
입력 서식 작성 시, 사용자의 실수로 오류가 발생할 경우 이를 정정할 수 있는 방법을 제공해야 한다.   
WCAG 2.1 부분 참조.    
[3.3.1 Error Identification (Level A)](https://www.w3.org/TR/WCAG21/#error-identification){: target="_blank"}   


**고려 사항**    
1. 사용자 입력 오류 안내   
   - 온라인 서식에서 오류가 발생하는 경우, 사용자에게 오류가 발생한 위치와 오류를 유발하게 된 이유 등에 관한 정보를 알려 주어야 한다.    
     예) 이름, 주소, 전화번호, 이메일 주소를 입력하도록 구성한 입력 서식에서 일부 항목을 기입하지 않고 제출하였을 경우, 어떤 항목의 입력이 누락되었는지를 알려 주어야 한다.    
     시스템 또는 플랫폼에서 발생한 오류에는 이 검사 항목이 적용되지 않는다.    

**기대 효과**    
- 입력 오류를 수정할 수 있는 방법에 대한 정보를 텍스트로 자세하게 제공하는 것은 학습 장애가 있는 사용자들이 입력 서식을 성공적으로 작성할 수 있도록 도와준다. 오류가 있는 곳에만 오류 표시를 하면 시각 장애인이나 저시력 장애인은 오류가 난 곳에 도달하기 전까지는 어떤 오류가 발생했는지 알기 어렵지만, 오류의 내용을 먼저 텍스트로 설명해주거나, 프로그램을 통해 오류가 난 위치로 초점을 이동시킨 후에 오류의 내용을 설명해 주면 입력 오류를 더 쉽게 정정할 수 있다.   
- 실수로 인해 빚어지는 심각한 결과 또는 과실을 피하기 위해 오류 정정에 필요한 정보나 수단을 제공하는 것은 장애인뿐 아니라 모든 사용자들에게 도움을 준다.   



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
   - [인식의 용이성(Perceivable)-tab](05-a11yCagGuide/perceivable.md)   
   - [운용의 용이성(Operable)-tab](05-a11yCagGuide/operable.md)   
   - [이해의 용이성(Understandable)-tab](05-a11yCagGuide/understandable.md)   
   - [견고성(Robust)-tab](05-a11yCagGuide/robust.md)   
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