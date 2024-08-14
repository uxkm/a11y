# WAI-ARIA란?
> **WAI-ARIA (Web Accessibility Initiative - Accessible Rich Internet Applications)** 는  웹 콘텐츠와 웹 애플리케이션이 장애인에게 더 접근 가능하도록 돕기 위한 W3C의 표준 기술이며, 스크린 리더와 같은 보조 기술이 웹 페이지의 구조와 목적을 이해하고 상호작용할 수 있도록 하는 **역할**, **상태** 및 **속성**을 정의하고 있다.    

## WAI-ARIA 핵심 목표 및 기능 요약
- 동적인 콘텐츠와 고급 사용자 인터페이스 컨트롤을 대상으로 하는 웹 접근성 표준으로, 특히 스크린 리더 사용자와 같은 보조 기술 사용자가 웹 애플리케이션을 효과적으로 사용할 수 있도록 돕기 위해 설계됨.    
- HTML에 추가적인 속성을 제공하여 접근성을 높이며, 이 속성들은 웹 요소의 역할, 상태, 속성을 설명하여 보조 기술이 이를 더 잘 이해하고 사용자에게 전달할 수 있도록 한다. 이를 통해 복잡한 웹 애플리케이션에서도 모든 사용자가 원활하게 상호작용할 수 있는 환경을 제공.   
   
[W3C WAI-ARIA 개요 참조](https://www.w3.org/WAI/standards-guidelines/aria/){: target="_blank"}


<figure style="text-align:center">
  <a href="https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg" target="_blank" title="새 창 열림"><img src="https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg" alt="Class diagram of the relationships described in the role data model."></a>
  <figcaption><strong>역할 데이터 모델에 설명된 관계 클래스 다이어그램 (크게 보기)</strong></figcaption>
</figure>


## WAI-ARIA의 연혁 및 발전
1. **2004년: 초기**    
   - WAI-ARIA의 개념은 2004년 W3C에서 처음 논의되었으며, 당시 웹 애플리케이션이 점점 더 복잡해지면서 접근성을 보장하는 새로운 방법이 필요하다는 인식이 있었음.       
2. **2006년: 첫 번째 공개 작업 초안 (Working Draft)**    
   - WAI-ARIA의 첫 번째 공개 작업 초안 발표. 이 초안은 복잡한 웹 애플리케이션에서 동적 콘텐츠와 고급 위젯을 정의하는 방법을 설명.       
   - 이 초기 버전은 기본적인 롤(roles), 속성(properties), 상태(states) 등을 정의.       
3. **2009년: WAI-ARIA 1.0 발표**    
   - WAI-ARIA 1.0의 첫 번째 권고 초안이 W3C에서 발표. 이 버전은 웹 접근성 향상을 위한 표준을 제시.       
   - 새로운 롤(Role), 속성(Properties), 상태(States) 정의.       
   - 사용자 인터페이스 구성 요소(UI Components)의 접근성을 정의하는 방법 제시.       
4. **2014년: WAI-ARIA 1.0 권고안 (Recommendation)**    
   - WAI-ARIA 1.0이 W3C의 권고안으로 공식 발표. 이 버전은 웹 접근성 커뮤니티에서 널리 채택되었으며, 다양한 브라우저와 보조 기술에서 지원하기 시작.       
5. **2017년: WAI-ARIA 1.1 발표**    
   - WAI-ARIA 1.1 버전 발표. 이 버전은 WAI-ARIA 1.0의 개선 및 확장을 포함하며, 사용자 경험을 개선하는 새로운 롤과 속성들이 추가.       
   - 기존 롤(Role)과 속성(Property)에 대한 추가 명세 개선.       
   - 새로운 롤(Role) 및 속성(Property) 도입.       
   - 스크린 리더와 같은 보조 기술과의 호환성 향상.       
6. **2021년: WAI-ARIA 1.2 발표**    
   - WAI-ARIA 1.2 권고안으로 발표. 이 버전은 이전 버전들의 피드백을 반영하여 더욱 정교한 접근성 요구 사항을 추가.       
   - 복합 위젯에 대한 추가 정의.       
   - 사용자 정의 위젯에 대한 접근성 지원.       
   - 라이브 영역(live regions)에 대한 개선된 지침 제공.       
7. **현재 ~ : WAI-ARIA 1.3**    
   - WAI-ARIA의 다음 버전인 1.3에 대한 논의가 진행 중이며, 웹 접근성 표준의 계속적인 개선이 목표. WAI-ARIA 1.3은 더 많은 사용자 정의 위젯 지원과 접근성 테스트 및 지원의 자동화를 목표로 할 가능성.       


## WAI-ARIA의 중요성
1. **웹 접근성 표준화**    
   - WAI-ARIA는 동적 콘텐츠와 복잡한 사용자 인터페이스를 포함하는 웹 애플리케이션의 접근성을 보장하기 위해 필수적인 기술 표준.     
2. **보조 기술과의 통합**    
   - WAI-ARIA는 스크린 리더, 화면 확대 소프트웨어 등 보조 기술이 웹 콘텐츠를 보다 정확하게 해석하고 사용자에게 전달할 수 있도록 돕는다.   
3. **포용적인 웹 환경 조성**    
   - 모든 사용자가 웹 애플리케이션을 사용할 수 있도록 보장하여 포용적인 웹 환경을 조성.    
   - WAI-ARIA를 웹 사이트와 애플리케이션에 적절히 적용하면, 장애를 가진 사용자를 포함한 모든 사용자가 웹 콘텐츠를 보다 쉽게 접근하고 사용할 수 있게 된다.    

## WAI-ARIA 적용 시 주의사항
1. **WAI-ARIA의 남용 방지**   
   - 이미 접근성이 내장된 네이티브 HTML 요소에 불필요하게 WAI-ARIA를 추가하지 않도록 주의    
   - 예) &lt;button&gt; 요소는 이미 접근성이 확보되어 있으므로 추가적인 role="button" 속성 불필요.    
2. **테스트 필수**   
   - 다양한 보조 기술(스크린 리더, 키보드 내비게이션 등)과 다양한 브라우저에서 충분히 테스트하여, WAI-ARIA 적용이 의도한 대로 작동하는지 확인.    
3. **웹 표준 준수**   
   - WAI-ARIA를 적용할 때 웹 표준을 준수하고, 가이드라인에 따라 역할, 속성, 상태를 올바르게 사용.    



## WAI-ARIA의 주요 역할(Role)
> WAI-ARIA에서 **역할(Role)** 은 특정 HTML 요소가 웹 페이지 내에서 어떤 역할을 하는지를 정의하며, 스크린 리더와 같은 보조 기술이 이 정보를 이용해 사용자가 웹 콘텐츠를 더 잘 이해하고 탐색할 수 있도록 돕는다.   
대부분의 시멘틱 마크업의 요소들은 기본적인 **역할(Role)** 이 지원되고 있으며,    
기존 레거시 시스템이나 특정 요구 사항으로 인해 div 요소를 사용해야 하는 상황에서 동일한 접근성 역할을 부여하여 사용 가능하다.    
[Accessible Rich Internet Applications (WAI-ARIA) 1.2 - Roles Model](https://www.w3.org/TR/wai-aria/#roles){: target="_blank"}
[MDN WAI-ARIA 역할](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles){: target="_blank"}

### ARIA 역할 유형
> ARIA 역할 유형은 웹 페이지와 애플리케이션에서 다양한 요소의 기능과 구조를 정의하여, 보조 기술이 이를 올바르게 인식하고 사용자에게 전달할 수 있도록 돕는다.     
각 역할 유형은 특정 UI 구성 요소나 문서 구조를 설명하며, 이들 역할을 올바르게 사용하면 웹 접근성을 크게 향상시킬 수 있다. 작업시 이러한 역할을 잘 이해하고 적절히 활용하여 모든 사용자가 웹 콘텐츠에 효과적으로 접근할 수 있도록 해야 한다.   
1. **Abstract Roles (추상적 역할)**  
   - 문서를 구성하고 간소화하는 데 도움이 되도록 브라우저에서만 사용하기 위한 것. HTML 마크업을 작성하는 개발자가 사용해서는 안 됨. 참조용으로만 포함.    
   - 주요 예시)command, composite, input, landmark, range, roletype, section, sectionhead, select, structure, widget 및 window.
2. **Widget Roles (위젯 역할)**   
   - 사용자의 상호작용을 처리하는 UI 요소들을 정의하는 역할이며, 버튼, 슬라이더, 탭 등과 같은 상호작용 가능한 위젯을 나타내며, 사용자가 직접 조작할 수 있는 요소들. Widget Roles는 보조 기술이 이러한 요소의 기능과 상태를 이해하고 사용자에게 올바르게 전달하도록 돕는다.    
   - 주요 예시)button, checkbox, gridcell, link, menuitem, menuitemcheckbox, menuitemradio, option, progressbar, radio, textbox.
3. **Document Structure (문서 구조 역할)**    
   - 문서 구조 역할은 콘텐츠 섹션에 대한 구조적 설명을 제공하는 데 사용.    
   - 브라우저가 동일한 의미의 시맨틱 HTML 요소를 지원하므로 이러한 역할의 대부분은 더 이상 사용해서는 안 됨.    
   - 프리젠테이션, 도구 모음 및 도구 설명 역할과 같이 HTML에 해당하는 역할이 없는 역할은 동일한 기본 HTML 태그를 사용할 수 없으므로 보조 기술에 문서 구조에 대한 정보를 제공.    
   - 대부분의 문서 구조 역할의 경우 시맨틱 HTML에 해당하는 요소를 사용할 수 있으며 지원되고 있음.    
   - 주요 예시) toolbar, tooltip, feed, math, presentation / none, note, application, directory, document, group, 
   - 시멘틱 예시)    
     article (&lt;article&gt;)   
     cell (&lt;td&gt;)    
     columnheader (&lt;th scope="col"&gt;)    
     definition (&lt;dfn&gt;)    
     figure (&lt;figure&gt;)    
     heading (h1~h6)    
     img (&lt;img&gt; or &lt;picture&gt;)    
     list (&lt;ul&gt; or &lt;ol&gt;)    
     listitem (&lt;li&gt;)    
     meter (&lt;meter&gt;)    
     row (&lt;tr&gt; with &lt;table&gt;)    
     rowgroup (&lt;thead&gt;, &lt;tfoot&gt; and &lt;tbody&gt;)    
     rowheader (&lt;th scope="row"&gt;)    
     separator (&lt;hr&gt;)    
     table (use &lt;table&gt;)      
     term (use &lt;dfn&gt;)     
4. **Landmark Roles (랜드마크 역할)**    
   - 랜드마크 역할은 웹 페이지의 구성과 구조를 식별하는 방법을 제공.    
   - 페이지의 섹션을 분류하고 레이블을 지정하면 레이아웃을 통해 시각적으로 전달되는 구조적 정보가 프로그래밍 방식으로 표현.    
   - 시멘틱 예시)    
     banner (document &lt;header&gt;)   
     complementary (&lt;aside&gt;)   
     contentinfo (document &lt;footer&gt;)    
     form (&lt;form&gt;)   
     main (&lt;main&gt;)   
     navigation (&lt;nav&gt;)   
     region (&lt;section&gt;)   
     search (&lt;search&gt;)   
5. **Live Region Roles (라이브 영역 역할)**   
   - 동적으로 변경되는 콘텐츠를 사용자에게 실시간으로 알리기 위해 사용되는 역할.    
   - 시력이 있는 사용자는 시각적으로 눈에 띄는 동적 변화를 볼 수 있지만, 저시력 및 시각 장애인 사용자가 콘텐츠가 업데이트되었는지 확인하는 데 스크린 리더와 같은 보조 기술이 콘텐츠의 변경 사항을 사용자에게 전달하도록 하는 데 필수적이다.    
   - 주요 예시)alert, log, marquee, status, timer.
6. **Window Roles (윈도우 역할)**    
   - 사용자 인터페이스의 창 요소를 정의하는 역할로, 주로 대화 상자, 모달 창, 툴팁과 같은 UI 구성 요소를 나타냄.    
   - 웹 애플리케이션에서 중요한 정보를 전달하거나 사용자와 상호작용을 하는 데 사용되며, 보조 기술이 이들 요소를 인식하고 사용자에게 알리도록 제공한다.    
   - 주요 예시)alertdialog, dialog, tooltip.

### 자주 사용되는 역할(Role) 예시
1. **Role: button**   
- 요소를 "버튼"으로(클릭 가능한 요소) 인식.   

```sh
// 기본 시멘틱 마크업 예시
<button type="button">UXKM</button>

// role 부여 예시
<div role="button" tabindex="0">UXKM</div>
```

2. **Role: alert**   
- 중요한 메시지를 사용자에게 즉시 전달해야 할 때 사용. 스크린 리더는 이 요소가 등장할 때 자동으로 읽어줌.   
- 폼 제출 시 오류 메시지를 표시할 때 유용.   

```sh
// 예시
<div role="alert">중요한 알림 메시지입니다!</div>
```

3. **Role: dialog**   
- 대화 상자(Dialog)를 나타냄. 주로 모달 창에 사용되며, 사용자가 상호작용할 수 있는 창을 보여준다.   

```sh
// 예시
<div role="dialog" aria-labelledby="dialogTitle">
    <h2 id="dialogTitle">Confirm Action</h2>
    <p>Are you sure you want to proceed?</p>
</div>
```

4. **Role: heading**   
- 섹션 제목을 정의. 레벨(aria-level 속성으로 설정)이 포함되어 콘텐츠의 계층 구조를 정의할 수 있다.     

```sh
// 기본 시멘틱 마크업 예시
<h1>Heading h1</h1>

// role 부여 예시
<div role="heading" aria-level="1">Heading h1</div>
```

5. **Role: navigation**   
- 페이지 내의 내비게이션 링크 그룹을 정의. 메뉴, 탐색 바 등에서 사용.     

```sh
// 기본 시멘틱 마크업 예시
<nav>
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
    </ul>
</nav>

// role 부여 예시
<div role="navigation">
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
    </ul>
</div>
```

6. **Role: tab**   
- 탭 인터페이스에서 탭 요소를 정의. tablist와 함께 사용.     

```sh
// 예시
<div role="tablist">
    <div role="tab" tabindex="0" aria-selected="true">Tab 1</div>
    <div role="tab" tabindex="-1" aria-selected="false">Tab 2</div>
</div>
```

7. **Role: tabpanel**   
- 탭이 선택되었을 때 표시되는 콘텐츠 패널을 정의.     

```sh
// 예시
<div role="tabpanel" aria-labelledby="tab1">Content for Tab 1</div>
```

8. **Role: header**   
- header 요소의 역할을 수행하는 div요소에 role="banner" 속성을 추가     

```sh
// 기본 시멘틱 마크업 예시
<header>
    <h1>Website Title</h1>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
        </ul>
    </nav>
</header>

// role 부여 예시 - header 역할을 하는 div
<div role="banner">
    <h1>Website Title</h1>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
        </ul>
    </nav>
</div>
```

9. **Role: main**   
- main 요소의 역할을 수행하는 div요소에 role="main" 속성을 추가     

```sh
// 기본 시멘틱 마크업 예시
<header>
    <h1>Website Title</h1>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
        </ul>
    </nav>
</header>

// role 부여 예시 - main 역할을 하는 div
<div role="banner">
    <h1>Website Title</h1>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
        </ul>
    </nav>
</div>
```

10. **Role: section**   
- section 요소의 역할을 수행하는 div요소에 role="region" 속성을 추가. 이때, aria-labelledby를 사용하여 섹션 제목을 참조할 수 있다.     

```sh
// 기본 시멘틱 마크업 예시
<section>
    <h2 id="section-title">Section Title</h2>
    <p>This is a section of the document.</p>
</section>

// role 부여 예시 - section 역할을 하는 div
<div role="region" aria-labelledby="section-title">
    <h2 id="section-title">Section Title</h2>
    <p>This is a section of the document.</p>
</div>
```

11. **Role: article**   
- article 요소의 역할을 수행하는 div요소에 role="article" 속성을 추가.      

```sh
// 기본 시멘틱 마크업 예시
<article>
    <h2>Article Title</h2>
    <p>This is an article content that stands alone and could be distributed separately from the rest of the document.</p>
</article>

// role 부여 예시 - article 역할을 하는 div
<div role="article">
    <h2>Article Title</h2>
    <p>This is an article content that stands alone and could be distributed separately from the rest of the document.</p>
</div>
```

12. **Role: footer**   
- footer 요소의 역할을 수행하는 div요소에 role="contentinfo" 속성을 추가.      

```sh
// 기본 시멘틱 마크업 예시
<footer>
    <p>&copy; 2024 Company Name. All rights reserved.</p>
</footer>

// role 부여 예시 - footer 역할을 하는 div
<div role="contentinfo">
    <p>&copy; 2024 Company Name. All rights reserved.</p>
</div>
```

13. **Role: aside**   
- aside  요소의 역할을 수행하는 div요소에 role="complementary" 속성을 추가.      

```sh
// 기본 시멘틱 마크업 예시
<aside>
    <h3>Related Links</h3>
    <ul>
        <li><a href="#link1">Link 1</a></li>
        <li><a href="#link2">Link 2</a></li>
    </ul>
</aside>

// role 부여 예시 - aside  역할을 하는 div
<div role="complementary">
    <h3>Related Links</h3>
    <ul>
        <li><a href="#link1">Link 1</a></li>
        <li><a href="#link2">Link 2</a></li>
    </ul>
</div>
```

### 역할(Role) 요약 및 주의사항
1. **역할 부여**   
   - div 요소에 role 속성을 추가하여, 특정 HTML5 요소가 제공하는 접근성 역할을 구현할 수 있다.   
2. **일관된 접근성**   
   - 보조 기술은 이러한 role 속성을 사용하여 요소를 올바르게 해석하고, 사용자가 페이지의 구조와 내용에 대해 명확하게 이해할 수 있도록 돕는다.   
3. **네이티브 요소 사용 권장**   
   - 가능한 경우에는 role 속성을 사용하는 대신, HTML5에서 제공하는 네이티브 요소(header, main, section, article, footer, aside 등)를 사용하는 것이 좋다.   
   - 네이티브 요소는 이미 접근성을 고려하여 설계되었기 때문에, 별도의 role 속성 없이도 보조 기술에 의해 올바르게 해석된다.   

```sh
// 잘못된 예시 - 이미 접근성을 지원하는 네이티브 HTML 요소에 불필요하게 WAI-ARIA 속성을 사용하는 것
<button role="button" aria-pressed="false">Submit</button>

// 올바른 예시1 - HTML5에서는 일부 요소가 이미 접근성을 기본적으로 지원
<button type="button">Submit</button>

// 올바른 예시2 - 네이티브 HTML 요소를 사용할 수 없거나, 사용자 정의 요소를 사용하여 접근성을 구현해야 하는 상황에서 올바르게 WAI-ARIA를 사용하는 방법
<div role="button" tabindex="0" aria-pressed="false">Submit</div>
```


## 상태 및 속성(State and Properties)
> WAI-ARIA에서 **상태(State)** 와 **속성(Properties)** 은 웹 콘텐츠와 애플리케이션의 접근성을 향상시키기 위해 사용.    
둘 다 보조 기술이 웹 요소의 현재 상태나 특성을 이해하도록 돕지만, 약간의 차이가 있다.
[Accessible Rich Internet Applications (WAI-ARIA) 1.2 - Supported States and Properties](https://www.w3.org/TR/wai-aria/#states_and_properties){: target="_blank"}
[MDN WAI-ARIA states and properties](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes){: target="_blank"}

### 상태(State)와 속성(Properties)의 차이점
- **상태(State)**   
  * 동적이거나 시간에 따라 변할 수 있는 정보.   
  * 사용자가 상호작용할 때 자주 변경됨.   
  * HTML 요소의 상태나 특성을 정의하며, 보조 기술이 웹 요소의 현재 상태를 이해하고 사용자에게 전달할 수 있도록 돕고, 역할(Role)과 함께 사용되어 웹 콘텐츠의 접근성을 강화한다.    
  * 예) 선택 여부, 확장 여부, 활성화 상태 등을 포함.   
- **속성(Properties)**    
  * 일반적으로 변경되지 않거나 요소의 본질적인 특성을 나타내는 정적 정보.   
  * 페이지 로딩 시 설정되고 보통 변경되지 않는다.   
  * 예) 요소의 레이블, 설명, 역할 등이 속성에 해당.    



## WAI-ARIA 적용 방법
> WAI-ARIA를 실제 웹 사이트와 애플리케이션에 적용하는 방법과 몇 가지 사례를 제시하여 웹 접근성을 개선하고 모든 사용자가 웹 콘텐츠에 접근할 수 있도록 제공.    

### 적절한 ARIA 역할(Role) 사용
- WAI-ARIA 역할을 사용하여 HTML 요소의 목적을 명확하게 정의   
- 예) div나 span 같은 요소에 role="button"을 사용하여 해당 요소가 버튼 역할을 수행하도록 해준다.

```sh
// 스크린 리더에게 해당 요소가 클릭 가능한 버튼임을 알려주고 tabindex를 제공하여 초점(포커스)이 발생할 수 있게 제공.
<div role="button" tabindex="0">Click Me</div>
```

### ARIA 속성(Properties) 활용
- 요소의 상태나 특성을 명확히 하기 위해 적절한 ARIA 속성을 추가   
- 예) aria-expanded를 사용하여 요소가 확장되었는지 여부를 나타낼 수 있다.

```sh
// 드롭다운 메뉴의 확장/축소 상태를 보조 기술에 전달.
<button aria-expanded="false" aria-controls="submenu">Menu</button>
<ul id="submenu" aria-hidden="true">
    <li><a href="#">Item 1</a></li>
    <li><a href="#">Item 2</a></li>
</ul>
```

### ARIA 상태(States) 적용
- 사용자의 상호작용에 따라 변할 수 있는 요소에 대해 ARIA 상태를 설정   
- 예) 체크박스의 상태를 aria-checked로 표시.

```sh
// 사용자가 체크박스를 선택하거나 해제할 때 이 속성이 업데이트됨.
<div role="checkbox" aria-checked="false" tabindex="0">Accept Terms</div>
```

### 정확한 레이블 제공
- aria-label 또는 aria-labelledby를 사용하여 요소에 명확한 텍스트 레이블을 제공함으로써 스크린 리더 사용자가 요소의 목적을 이해할 수 있도록 함   

```sh
// "X" 버튼이 "닫기 또는 취소" 버튼임을 보조 기술 사용자에게 알림.
<button type="button" aria-label="닫기">X</button>
<button type="button" aria-label="취소">X</button>
```

### 동적 콘텐츠에 aria-live 적용
- 실시간으로 변경되는 콘텐츠에 aria-live 속성을 사용하여 스크린 리더가 해당 변화를 사용자에게 알릴 수 있도록 한다   

```sh
// 메시지가 추가되면 스크린 리더가 사용자에게 이를 알려준다.
<div aria-live="polite">New message received.</div>
```

## 관련 도구 및 리소스
> WAI-ARIA 적용을 돕는 도구와 추가 학습을 위한 리소스.

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
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   