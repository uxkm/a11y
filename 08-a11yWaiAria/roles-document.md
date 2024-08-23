# WAI-ARIA 역할

## Document Structure Roles (문서 구조 역할)
> **Document Structure Roles**는 웹 페이지나 애플리케이션의 콘텐츠를 논리적이고 의미 있는 방식으로 구성하는 데 사용됩니다. 이 역할은 문서의 주요 부분을 정의하고, 보조 기술이 이 구조를 이해할 수 있도록 도와줍니다. Document Structure 역할은 페이지를 효율적으로 탐색할 수 있도록 콘텐츠를 구조화하는 데 필수적입니다.   
[W3C ARIA Document Structure Roles](https://www.w3.org/TR/wai-aria-1.2/#document_structure_roles){: target="_blank"}   


### **1. application 역할**    
application 역할은 웹 페이지의 특정 영역이 일반적인 웹 콘텐츠와는 다른, 고도의 상호작용이 필요한 애플리케이션처럼 동작함을 보조 기술에 알리는 데 사용됩니다. 이 역할은 웹 페이지에서 데스크탑 애플리케이션과 유사한 상호작용을 제공하는 UI 요소에 사용되며, 사용자에게 더 복잡한 기능을 제공하기 위해 사용됩니다.   
[W3C ARIA application](https://www.w3.org/TR/wai-aria-1.2/#application){: target="_blank"}   
[MDN ARIA application](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/application_role){: target="_blank"}   

**기본 설명**  
- application 역할은 복잡한 상호작용을 요구하는 웹 애플리케이션의 특정 영역을 나타냅니다. 이 역할을 사용하면 보조 기술이 이 콘텐츠를 데스크탑 애플리케이션처럼 처리할 수 있게 되며, 사용자는 더 정교한 상호작용을 수행할 수 있습니다.    
- **적절한 사용 필수**: application 역할은 복잡한 기능이 필요한 웹 애플리케이션에만 사용해야 하며, 일반적인 웹 페이지나 단순 인터페이스에는 사용하지 않는 것이 좋습니다. 이는 사용자의 웹 탐색 경험을 보호하고, 불필요한 복잡성을 피하는 데 중요합니다.    
- **중요한 점**: application 역할을 사용하는 경우, 사용자가 애플리케이션 모드에서 필요한 상호작용 방법을 이해할 수 있도록 충분한 안내를 제공해야 합니다. 이를 통해 사용자 경험과 접근성을 모두 향상시킬 수 있습니다.    

**사용 시 주의사항**   
- **적절한 사용 범위 설정**: application 역할은 특정 기능이 복잡하고, 상호작용이 고도화된 영역에만 사용해야 합니다. 예를 들어, 사용자 입력과 피드백이 빈번하고 즉각적인 처리가 필요한 인터페이스에 사용됩니다.   
- **일반적인 웹 페이지에는 사용하지 않기**: 일반적인 콘텐츠 탐색을 필요로 하는 웹 페이지나 단순한 인터페이스에는 application 역할을 사용하지 않는 것이 좋습니다. 이는 사용자가 웹 페이지와 상호작용하는 기본적인 방법을 방해할 수 있습니다.
- **스크린 리더와의 상호작용 주의**: application 역할을 사용하면 스크린 리더는 기본 탐색 모드를 비활성화하고, 애플리케이션 모드로 전환됩니다. 이로 인해 사용자는 일반적인 문서 탐색 키보드 명령을 사용할 수 없게 되므로, 필요한 경우 키보드 단축키와의 상호작용 방법을 안내해야 합니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: 애플리케이션 영역의 레이블을 참조합니다.    
- **aria-describedby**: 애플리케이션 영역에 대한 추가 설명을 제공합니다.    
- **aria-live**: 애플리케이션 내에서 실시간으로 업데이트되는 정보를 사용자에게 전달할 수 있습니다.    


**잘못된 예시**
이 예시는 application 역할을 일반적인 웹 콘텐츠에 사용하고 있습니다. application 역할은 복잡한 웹 애플리케이션 기능을 제공하는 영역에만 사용되어야 합니다. 단순한 정보 제공에는 적합하지 않습니다.    
```sh
<div role="application">
  <p>Welcome to our website. Here is some basic information.</p>
</div>
```

**올바른 예시**
이 예시는 복잡한 상호작용이 필요한 스프레드시트 애플리케이션을 나타내며, application 역할을 사용하여 사용자가 이 인터페이스를 데스크탑 애플리케이션처럼 사용할 수 있도록 설정했습니다.    
```sh
<div role="application" aria-labelledby="spreadsheetTitle">
  <h2 id="spreadsheetTitle">Spreadsheet Application</h2>
  <!-- Complex spreadsheet interface goes here -->
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

**복잡한 그래픽 에디터 예시**
이 예시는 사용자가 다양한 도구를 사용하여 그래픽 작업을 수행할 수 있는 그래픽 에디터를 나타냅니다. application 역할은 이 영역을 일반적인 웹 콘텐츠와 구분하여, 보조 기술이 이를 애플리케이션으로 인식하게 합니다.    
```sh
<div role="application" aria-labelledby="editorTitle">
  <h2 id="editorTitle">Graphic Editor</h2>
  <div class="toolbar">
    <!-- Toolbar with various tools -->
  </div>
  <div class="canvas">
    <!-- Canvas for drawing -->
  </div>
</div>
```

### **2. article 역할**    
article 역할은 웹 페이지에서 독립적으로 구분될 수 있는 콘텐츠 블록을 나타냅니다. 이 콘텐츠 블록은 독립적으로 배포하거나 재사용할 수 있으며, 문서의 다른 부분과 구별되는 자체적인 의미를 가지고 있습니다. 예를 들어, 뉴스 기사, 블로그 포스트, 포럼의 글 등이 이에 해당됩니다.   
[W3C ARIA article](https://www.w3.org/TR/wai-aria-1.2/#article){: target="_blank"}   
[MDN ARIA article](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/article_role){: target="_blank"}   
[UXKM : article element](https://uxkm.io/publishing/html/03-sections/05-article_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- article 역할은 웹 페이지에서 독립적으로 이해될 수 있는 콘텐츠를 정의하는 데 사용됩니다. 이 역할을 사용하면 보조 기술이 이 콘텐츠를 독립적인 문서로 처리할 수 있도록 도와줍니다.    
- **시멘틱 마크업 추천**: 가능하면 HTML5 시멘틱 요소인 &lt;article&gt;을 사용하여 독립적인 콘텐츠를 정의하는 것이 좋습니다. 이 방법은 문서의 의미를 명확히 하고, 접근성을 자연스럽게 향상시킵니다.    
- **중요한 점**: article 역할은 독립적인 의미를 가지는 콘텐츠에만 사용해야 하며, 문서의 다른 부분과 함께 이해되어야 하는 콘텐츠에는 적합하지 않습니다. 이를 통해 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 필요한 경우 aria-labelledby와 aria-describedby 속성을 사용해 콘텐츠의 제목과 설명을 명확히 제공하여, 보조 기술 사용자가 콘텐츠를 쉽게 이해할 수 있도록 해야 합니다.    

**사용 시 주의사항**   
- **독립적인 콘텐츠에 사용**: article 역할은 독립적으로 읽히고 이해될 수 있는 콘텐츠에만 사용해야 합니다. 문서나 페이지의 일부로만 의미가 있는 콘텐츠에는 사용하지 않습니다.   
- **HTML5 시멘틱 요소 사용 권장**: 가능하면 HTML5의 &lt;article&gt; 요소를 사용하여 시멘틱하게 콘텐츠를 정의하는 것이 좋습니다. 이는 보조 기술이 콘텐츠를 올바르게 인식하고 처리할 수 있도록 도와줍니다.
- **중복 사용 방지**: 문서 내에서 중복되는 article 역할을 사용할 경우, 콘텐츠의 독립적인 의미를 잃을 수 있으므로 주의해야 합니다. 각각의 article은 고유한 의미를 가져야 합니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: article의 제목을 지정하여 보조 기술이 이를 콘텐츠의 제목으로 식별하게 합니다. 이 속성은 콘텐츠의 제목 요소를 참조하도록 설정할 수 있습니다.    
- **aria-describedby**: article의 설명을 제공하여 보조 기술이 이 콘텐츠의 목적이나 추가적인 설명을 사용자에게 전달할 수 있게 합니다.    
- **aria-label**: article의 목적을 명확히 설명하는 레이블을 제공합니다. 이 속성은 article이 어떤 역할을 하는지 명확히 하여, 보조 기술 사용자가 이해하기 쉽게 합니다.    
- **기타 상속된 속성**: article 역할은 일반적으로 특정 상태를 상속받지 않지만, 필요에 따라 aria-live나 aria-busy 속성 등을 추가하여 콘텐츠가 동적으로 업데이트될 때 정보를 사용자에게 제공할 수 있습니다.       


**잘못된 예시**
이 예시는 회사 소개를 나타내는 콘텐츠에 article 역할을 사용하고 있지만, 이 콘텐츠는 독립적으로 이해되기보다는 문서 전체와 연관된 설명입니다. 이 경우, article 역할보다는 다른 시멘틱 역할이나 일반적인 블록 요소를 사용하는 것이 적합합니다.    
```sh
<div role="article">
  <h2>Our Company</h2>
  <p>We provide the best services to our customers.</p>
</div>
```

**올바른 예시**
이 예시는 독립적인 뉴스 기사 또는 블로그 게시물로 읽힐 수 있는 콘텐츠에 article 역할을 적절히 사용하고 있습니다. 이 콘텐츠는 자체적으로 의미가 있으며, 다른 문맥에서도 이해될 수 있습니다. aria-labelledby 속성을 사용해 article의 제목을 보조 기술이 인식할 수 있도록 설정했습니다.    
```sh
<div role="article" aria-labelledby="climateChangeTitle">
  <h2 id="climateChangeTitle">The Impact of Climate Change</h2>
  <p>Climate change has significant effects on the environment...</p>
</div>
```

**(권장) 시멘틱 사용 예시**
이 예시는 HTML5 시멘틱 요소인 &lt;article&gt;을 사용하여 블로그 게시물을 정의한 것입니다. &lt;article&gt; 요소는 기본적으로 article 역할을 가지며, aria-labelledby와 aria-describedby 속성을 통해 제목과 설명을 명확히 지정하여 보조 기술이 이 콘텐츠를 올바르게 처리할 수 있도록 돕습니다.    
```sh
<article aria-labelledby="writingSkillsTitle" aria-describedby="writingSkillsDesc">
  <h2 id="writingSkillsTitle">How to Improve Your Writing Skills</h2>
  <p id="writingSkillsDesc">Writing is a critical skill that can be improved with practice...</p>
</article>
```

### **3. cell 역할**    
cell 역할은 ARIA 문서 구조 역할 중에서 표(table)의 개별 셀을 나타내는 중요한 역할입니다. HTML의 &lt;td&gt;(표의 데이터 셀)와 &lt;th&gt;(표의 헤더 셀) 요소는 기본적으로 cell 역할을 수행하며, 이 역할은 표의 구조를 정의하고 각 셀이 데이터를 어떻게 표현하는지를 보조 기술에 설명하는 역할을 합니다.   
[W3C ARIA cell](https://www.w3.org/TR/wai-aria-1.2/#cell){: target="_blank"}   
[MDN ARIA cell](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/cell_role){: target="_blank"}   
[UXKM : td element](https://uxkm.io/publishing/html/08-table/10-td_element){: target="_blank"}   

**기본 설명**  
- cell 역할은 표의 각 셀을 시멘틱하게 정의하는 중요한 역할을 수행합니다. &lt;td&gt;와 &lt;th&gt; 요소를 사용하여 데이터를 명확하게 구조화하고, 보조 기술이 이를 올바르게 해석할 수 있도록 돕습니다.    
- **적절한 사용**: scope, headers, aria-colindex, aria-rowindex 등의 속성을 활용하여 표의 구조를 명확히 하고, 복잡한 표에서도 셀 간의 관계를 명확히 정의할 수 있습니다.    
- **중요한 점**: 표의 각 셀을 정확하게 정의함으로써, 사용자가 표 데이터를 쉽게 탐색하고 이해할 수 있도록 돕는 중요한 도구입니다.    

**사용 시 주의사항**   
- **시멘틱 마크업 사용**: 표의 셀을 정의할 때는 시멘틱한 마크업을 사용하여 표의 구조와 의미를 명확히 해야 합니다. &lt;th&gt;와 &lt;td&gt; 요소를 적절하게 사용하고, 필요에 따라 scope 및 headers 속성을 추가하여 셀과 헤더 간의 관계를 명확히 정의하는 것이 중요합니다.   
- **복잡한 표에서의 역할**: 복잡한 표에서 aria-colindex, aria-rowindex, aria-colspan, aria-rowspan과 같은 ARIA 속성을 활용하여, 보조 기술이 셀의 위치와 범위를 정확히 이해할 수 있도록 해야 합니다.
- **일관성 유지**: 표의 셀에 대한 속성 설정 시 일관성을 유지하여, 사용자가 표를 쉽게 탐색하고 이해할 수 있도록 해야 합니다. 특히 복잡한 표의 경우, 일관성 있는 인덱스와 범위 설정이 중요합니다.

**상속된 상태 및 속성**   
- **scope 속성**: &lt;th&gt; 요소에 사용되어 해당 헤더 셀이 적용되는 셀의 범위를 지정합니다. 예를 들어, scope="col"은 열 헤더, scope="row"는 행 헤더를 나타냅니다.    
- **headers 속성**: &lt;td&gt; 요소에 사용되어 이 셀이 참조하는 헤더 셀의 id를 지정합니다. 이는 특히 복잡한 표에서 셀과 관련 헤더 간의 관계를 명확하게 설명하는 데 유용합니다.    
- **aria-colindex 및 aria-rowindex**: ARIA 속성 중 하나로, 셀이 속한 열과 행의 인덱스를 지정하여 보조 기술이 표의 셀 위치를 정확히 이해할 수 있도록 합니다.    
- **aria-colspan 및 aria-rowspan**: ARIA 속성으로, 셀이 가로 또는 세로로 몇 개의 셀을 병합하는지 설명합니다. 이는 복잡한 테이블 레이아웃에서 특히 유용합니다.       


**기본 데이터 셀 및 헤더 셀**
이 예시는 th와 td 요소를 사용하여 각각의 셀을 정의하고 있습니다. th 요소는 열 헤더로 설정되며, scope="col" 속성을 통해 명확히 정의됩니다. 이 구조는 ARIA 문서 구조 역할에서 기본적인 cell 역할을 수행합니다.    
```sh
<table>
  <tr>
    <th scope="col">Name</th>
    <th scope="col">Age</th>
  </tr>
  <tr>
    <td>John Doe</td>
    <td>30</td>
  </tr>
</table>
```

**복잡한 표 구조에서의 cell 역할**
이 예시는 thead와 tbody 요소를 사용하여 복잡한 표 구조를 시멘틱하게 나누고 있습니다. th 요소는 행과 열 헤더로 사용되며, 각 데이터 셀(td)은 headers 속성을 사용해 관련 헤더를 참조합니다.    
```sh
<table>
  <thead>
    <tr>
      <th scope="col">Department</th>
      <th scope="col">Q1</th>
      <th scope="col">Q2</th>
      <th scope="col">Q3</th>
      <th scope="col">Q4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Sales</th>
      <td headers="Q1">5000</td>
      <td headers="Q2">7000</td>
      <td headers="Q3">8000</td>
      <td headers="Q4">9000</td>
    </tr>
    <tr>
      <th scope="row">Marketing</th>
      <td headers="Q1">6000</td>
      <td headers="Q2">8000</td>
      <td headers="Q3">7500</td>
      <td headers="Q4">8500</td>
    </tr>
  </tbody>
</table>
```

**ARIA 속성을 활용한 예시**
이 예시는 복잡한 표에서 각 셀의 정확한 위치를 나타내기 위해 aria-colindex와 aria-rowindex 속성을 사용하고 있습니다. 이러한 속성들은 보조 기술이 셀의 위치를 올바르게 파악할 수 있도록 도와줍니다.    
```sh
<table>
  <thead>
    <tr>
      <th scope="col" aria-colindex="1">Name</th>
      <th scope="col" aria-colindex="2">Age</th>
      <th scope="col" aria-colindex="3">Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td aria-rowindex="2" aria-colindex="1">John Doe</td>
      <td aria-rowindex="2" aria-colindex="2">30</td>
      <td aria-rowindex="2" aria-colindex="3">Sales</td>
    </tr>
    <tr>
      <td aria-rowindex="3" aria-colindex="1">Jane Smith</td>
      <td aria-rowindex="3" aria-colindex="2">28</td>
      <td aria-rowindex="3" aria-colindex="3">Marketing</td>
    </tr>
  </tbody>
</table>
```

### **4. columnheader 역할**    
columnheader 역할은 HTML 테이블에서 열의 제목을 나타내는 헤더 셀을 정의합니다. 이 역할은 주로 &lt;th&gt; 요소와 함께 사용되며, 특정 열의 데이터를 설명하거나 요약하는 기능을 합니다. columnheader 역할을 통해 보조 기술은 해당 열이 무엇을 나타내는지 사용자에게 명확하게 전달할 수 있습니다.   
[W3C ARIA columnheader](https://www.w3.org/TR/wai-aria-1.2/#columnheader){: target="_blank"}   
[MDN ARIA columnheader](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/columnheader_role){: target="_blank"}   
[UXKM : th element](https://uxkm.io/publishing/html/08-table/09-th_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- columnheader 역할은 HTML 테이블에서 열의 제목을 나타내며, &lt;th&gt; 요소와 함께 사용됩니다. 이 역할은 테이블의 열이 나타내는 데이터 유형을 설명하고, 보조 기술이 이를 올바르게 해석하도록 돕습니다.    
- **적절한 사용**: &lt;th&gt; 요소와 scope, aria-sort, aria-colspan 등의 속성을 적절히 사용하여, 열 헤더의 역할과 상태를 명확히 정의하는 것이 중요합니다.    
- **중요한 점**: 테이블의 각 열을 시멘틱하게 정의함으로써, 사용자가 테이블 데이터를 쉽게 이해하고 탐색할 수 있도록 돕는 중요한 도구입니다. 표의 일관성과 명확성을 유지하여 사용자 경험과 접근성을 모두 향상시킬 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업 사용**: &lt;th&gt; 요소와 scope="col" 속성을 함께 사용하여 열 헤더의 역할을 명확히 정의하는 것이 중요합니다. 이는 보조 기술이 표의 구조를 이해하는 데 도움을 줍니다.   
- **정렬 상태 명확히 지정**: 열 헤더가 정렬 가능하다면, aria-sort 속성을 사용해 현재 열의 정렬 상태를 명확히 지정해야 합니다. 이는 사용자에게 현재 테이블의 데이터 정렬 상태를 쉽게 이해할 수 있도록 돕습니다.
- **병합된 셀의 명확한 정의**: aria-colspan 및 aria-rowspan 속성을 사용해 병합된 셀의 범위를 명확히 정의해야 합니다. 이는 복잡한 테이블에서 셀 간의 관계를 이해하는 데 필수적입니다.

**상속된 상태 및 속성**   
- **scope 속성**: &lt;th&gt; 요소에서 사용되며, 열 헤더가 적용되는 범위를 정의합니다. 예를 들어, scope="col"은 열 전체에 적용되는 헤더임을 나타냅니다.    
- **aria-sort 속성**: 정렬 가능한 열 헤더에 사용되며, 열이 오름차순(ascending), 내림차순(descending), 정렬되지 않음(none), 또는 기타 사용자 정의 정렬(other) 상태 중 어떤 상태인지 지정합니다. 이는 보조 기술이 현재 테이블의 정렬 상태를 사용자에게 전달하는 데 도움을 줍니다.    
- **aria-colspan**: 열 헤더가 가로로 병합된 열의 수를 지정합니다.    
- **aria-rowspan**: 열 헤더가 세로로 병합된 행의 수를 지정합니다.       


**기본 열 헤더 사용 예시**
이 예시는 열 제목을 나타내기 위해 &lt;th&gt; 요소를 사용하고 있으며, scope="col" 속성을 통해 열 전체에 적용되는 헤더임을 명확히 하고 있습니다. 이 구조는 ARIA에서 columnheader 역할을 암시적으로 수행합니다.    
```sh
<table>
  <thead>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">Age</th>
      <th scope="col">Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Doe</td>
      <td>30</td>
      <td>Sales</td>
    </tr>
    <tr>
      <td>Jane Smith</td>
      <td>28</td>
      <td>Marketing</td>
    </tr>
  </tbody>
</table>
```

**정렬 가능한 열 헤더 예시**
이 예시는 aria-sort="ascending" 속성을 사용하여 현재 열이 오름차순으로 정렬되어 있음을 나타냅니다. 이는 보조 기술이 현재 열의 정렬 상태를 사용자에게 전달하는 데 유용합니다.    
```sh
<table>
  <thead>
    <tr>
      <th scope="col" aria-sort="ascending">Name</th>
      <th scope="col">Age</th>
      <th scope="col">Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Doe</td>
      <td>30</td>
      <td>Sales</td>
    </tr>
    <tr>
      <td>Jane Smith</td>
      <td>28</td>
      <td>Marketing</td>
    </tr>
  </tbody>
</table>
```

**병합된 열 헤더 예시**
이 예시는 aria-colspan 속성을 사용해 첫 번째 행의 "Employee Details" 헤더 셀이 두 개의 열을 병합하고 있음을 명확히 나타냅니다. 보조 기술은 이 정보를 바탕으로 셀이 포함하는 열의 범위를 이해할 수 있습니다.    
```sh
<table>
  <thead>
    <tr>
      <th scope="col" colspan="2" aria-colspan="2">Employee Details</th>
      <th scope="col">Department</th>
    </tr>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">Age</th>
      <th scope="col">Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Doe</td>
      <td>30</td>
      <td>Sales</td>
    </tr>
    <tr>
      <td>Jane Smith</td>
      <td>28</td>
      <td>Marketing</td>
    </tr>
  </tbody>
</table>
```

### **5. definition 역할**    
definition 역할은 웹 콘텐츠에서 용어의 정의를 제공하는 콘텐츠를 나타냅니다. 이 역할은 일반적으로 텍스트 내에서 중요한 용어의 의미를 명확하게 설명할 때 사용됩니다. definition 역할은 보조 기술이 특정 용어의 정의를 사용자에게 올바르게 전달할 수 있도록 도와줍니다.   
[W3C ARIA definition](https://www.w3.org/TR/wai-aria-1.2/#definition){: target="_blank"}   
[MDN ARIA definition](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/definition_role){: target="_blank"}   
[MDN dfn element](https://developer.mozilla.org/ko/docs/Web/HTML/Element/dfn){: target="_blank"}   

**기본 설명**  
- definition 역할은 웹 콘텐츠에서 용어의 정의를 명확히 설명하는 데 사용됩니다. 이 역할을 통해 보조 기술은 사용자에게 특정 용어가 정의되고 있음을 알릴 수 있습니다.    
- **적절한 사용**: 용어의 정의를 제공할 때는 시멘틱하게 &lt;dfn&gt; 요소를 사용하여, 정의가 명확히 구분되도록 하는 것이 중요합니다.    
- **중요한 점**: 용어의 정의는 문서 내에서 일관되고 명확하게 제공되어야 하며, 이를 통해 사용자가 용어를 쉽게 이해하고 문서의 내용을 효과적으로 학습할 수 있도록 해야 합니다.    

**사용 시 주의사항**   
- **시멘틱 마크업 사용**: 용어의 정의를 나타낼 때는 &lt;dfn&gt; 요소를 사용하여 용어를 정의하는 콘텐츠를 명확히 구분하는 것이 중요합니다.   
- **명확한 정의 제공**: 용어의 정의는 간결하고 명확하게 작성되어야 하며, 사용자가 해당 용어를 이해하는 데 도움이 되어야 합니다.
- **용어의 일관성 유지**: 문서 내에서 동일한 용어에 대해 일관된 정의를 제공하여, 사용자 경험의 일관성을 유지하는 것이 중요합니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. definition 역할은 용어의 정의를 시멘틱하게 나타내기 위한 역할이므로, 추가적인 ARIA 상태나 속성은 필요하지 않습니다.       


**기본 용어 정의 사용 예시**
이 예시는 &lt;dfn&gt; 요소를 사용하여 "HyperText" 용어의 정의를 제공하고 있습니다. 보조 기술은 이 요소를 통해 "HyperText"가 정의되고 있음을 사용자에게 전달합니다.    
```sh
<p>HTML은 HyperText Markup Language의 약자입니다. <dfn>HyperText</dfn>는 웹 페이지 간의 연결을 의미합니다.</p>
```

**용어와 정의의 시멘틱 구분 예시**
이 예시는 &lt;dfn&gt; 요소를 사용하여 "API" 용어를 정의하고 있으며, 링크를 통해 동일한 정의로 참조할 수 있도록 설정했습니다. 이는 문서 내에서 용어의 의미를 명확하게 구분하는 데 도움이 됩니다.    
```sh
<p>용어 <dfn id="dfn-api">API</dfn>는 응용 프로그램 인터페이스(Application Programming Interface)의 약자로, 소프트웨어 간의 상호작용을 정의합니다.</p>
<p>예를 들어, <a href="#dfn-api">API</a>는...</p>
```

**학술 자료에서의 정의 사용 예시**
이 예시는 학술 문서에서 사용되는 중요한 용어를 정의하는 예시입니다. &lt;dfn&gt; 요소는 용어 "엔트로피"의 정의를 제공하며, 독자가 문서의 내용을 더 잘 이해할 수 있도록 돕습니다.    
```sh
<p>과학에서, <dfn>엔트로피</dfn>는 시스템의 무질서 정도를 나타내는 물리적 개념입니다.</p>
```

### **6. directory 역할**    
directory 역할은 트리 구조로 조직된 목차나 파일 목록과 같은 계층적인 항목의 집합을 나타냅니다. 이 역할은 파일 시스템, 카탈로그, 탐색 메뉴와 같은 콘텐츠에서 사용될 수 있습니다. directory 역할은 보조 기술이 이 목록을 탐색할 때, 항목 간의 계층 구조를 이해할 수 있도록 돕습니다.   
[W3C ARIA directory](https://www.w3.org/TR/wai-aria-1.2/#directory){: target="_blank"}   
[MDN ARIA directory](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/directory_role){: target="_blank"}   

**기본 설명**  
- directory 역할은 트리 구조로 구성된 항목의 집합을 나타내며, 사용자가 이러한 구조를 쉽게 탐색할 수 있도록 돕습니다. 시멘틱 마크업에서는 기본적인 HTML 요소를 사용하여 이 역할을 자연스럽게 수행하며, 비표준 마크업에서는 다른 HTML 요소에 role="directory"와 관련 ARIA 속성을 사용해 명시적으로 정의할 수 있습니다.    
- **적절한 사용**: 계층 구조를 명확히 정의하고, aria-expanded와 aria-level 속성을 사용하여 항목 간의 관계를 정확히 설정하는 것이 중요합니다. 시멘틱 마크업을 사용하면 자연스럽게 보조 기술이 이를 인식할 수 있으며, 비표준 마크업에서는 ARIA 속성을 적절히 활용해야 합니다.    
- **중요한 점**: directory 역할을 사용하여 복잡한 목록 구조를 시멘틱하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 트리 구조를 보다 쉽게 탐색하고, 필요한 정보를 효율적으로 찾을 수 있습니다.    

**사용 시 주의사항**   
- **목록 항목 간의 계층 구조 정의**: directory 역할을 사용할 때는 각 항목의 계층 구조를 명확히 정의해야 합니다. 이를 통해 보조 기술이 목록을 올바르게 해석하고, 사용자에게 효율적인 탐색 경험을 제공합니다.   
- **적절한 확장 상태 관리**: aria-expanded 속성을 사용해 항목의 확장 상태를 명확히 지정해야 합니다. 사용자가 목록을 탐색할 때, 현재 어떤 항목이 확장되어 있는지 알 수 있도록 해야 합니다.
- **중첩된 목록 관리**: directory 역할은 중첩된 목록 구조에서 사용될 때 효과적입니다. 중첩된 항목은 계층 구조를 명확히 나타내야 하며, 이를 위해 aria-level 속성을 적절히 설정해야 합니다.

**상속된 상태 및 속성**   
- **aria-expanded**: 이 속성은 디렉토리 항목이 확장되어 있는지 여부를 나타냅니다. true로 설정하면 항목이 확장되어 하위 항목이 표시되고, false로 설정하면 하위 항목이 숨겨집니다.       
- **aria-level**: 디렉토리 항목이 트리 구조에서 어느 계층에 속하는지를 지정합니다. 이 속성을 사용하여 보조 기술이 항목 간의 계층 구조를 이해할 수 있도록 합니다。       


**잘못된 예시**
이 예시는 &lt;div&gt; 요소를 사용하여 디렉토리 구조를 표현했지만, role="directory"와 같은 ARIA 속성 없이 사용되었습니다. 이로 인해 보조 기술이 이 구조를 올바르게 해석하지 못할 수 있습니다.    
```sh
<div>
  <div>Documents</div>
  <div>Pictures
    <div>
      <div>Vacation</div>
      <div>Family</div>
    </div>
  </div>
  <div>Music</div>
</div>
```

**올바른 예시 - div 요소 마크업을 사용한 디렉토리 구조**
이 예시는 &lt;div&gt; 요소에 role="directory"를 사용하여 디렉토리 구조를 명시적으로 나타냅니다. aria-expanded와 aria-level 속성을 사용해 항목의 계층 구조와 확장 상태를 지정하고 있습니다.   
```sh
<div role="directory">
  <div role="treeitem">Documents</div>
  <div role="treeitem" aria-expanded="false">Pictures
    <div role="group">
      <div role="treeitem" aria-level="2">Vacation</div>
      <div role="treeitem" aria-level="2">Family</div>
    </div>
  </div>
  <div role="treeitem">Music</div>
</div>
```

**시멘틱 마크업을 사용한 기본 디렉토리 구조 예시**
이 예시는 기본적인 디렉토리 구조를 시멘틱한 &lt;ul&gt; 및 &lt;li&gt; 요소를 사용하여 나타내고 있습니다. 이 구조는 기본적으로 보조 기술이 올바르게 인식할 수 있습니다.    
```sh
<ul>
  <li>Documents</li>
  <li>Pictures
    <ul>
      <li>Vacation</li>
      <li>Family</li>
    </ul>
  </li>
  <li>Music</li>
</ul>
```

### **7. document 역할**    
document 역할은 웹 페이지에서 특정 섹션이 독립된 문서나 주요 콘텐츠 블록을 나타내도록 지정하는 데 사용됩니다. 이 역할은 웹 애플리케이션의 일부가 아닌 문서형 콘텐츠(예: 텍스트, 이미지, 비디오 등)를 설명하는 데 유용합니다. document 역할은 주로 전체 페이지가 아닌 특정 섹션이 문서로서 해석되도록 할 때 사용됩니다.   
[W3C ARIA document](https://www.w3.org/TR/wai-aria-1.2/#document){: target="_blank"}   
[MDN ARIA document](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/document_role){: target="_blank"}   

**기본 설명**  
- document 역할은 웹 애플리케이션 내 특정 섹션이 독립된 문서로서 해석되어야 할 때 유용합니다. 이를 통해 보조 기술은 해당 섹션을 문서 탐색 모드에서 처리할 수 있습니다.    
- **적절한 사용**: document 역할은 전체 웹 페이지가 아닌, 독립된 문서로 간주해야 하는 특정 섹션에만 사용해야 합니다. 이 역할은 시멘틱하게 문서의 범위를 명확히 지정하고, 보조 기술이 이를 올바르게 인식할 수 있도록 해야 합니다.    
- **중요한 점**: document 역할을 사용하여 웹 애플리케이션 내에서 중요한 문서 콘텐츠를 명확히 지정함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 문서 콘텐츠를 더 쉽게 탐색하고, 필요한 정보를 효율적으로 찾을 수 있습니다.    

**사용 시 주의사항**   
- **웹 애플리케이션 내에서 사용**: document 역할은 주로 웹 애플리케이션 내에서 독립적인 문서 콘텐츠를 설명할 때 사용됩니다. 전체 웹 페이지에 이 역할을 사용하는 것은 적절하지 않습니다.   
- **문서 탐색 모드 활성화**: 이 역할을 사용하면 보조 기술은 문서 탐색 모드를 활성화하여 콘텐츠를 더 쉽게 탐색할 수 있습니다.
- **적절한 문서 범위 지정**: document 역할을 사용할 때는 정확하게 해당 섹션만 독립된 문서로 지정해야 합니다. 잘못된 위치에 사용하면 사용자 경험에 혼란을 줄 수 있습니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: 이 속성은 문서의 제목을 지정하여 보조 기술이 이를 문서의 주요 제목으로 식별하도록 합니다.       
- **aria-describedby**: 이 속성은 문서에 대한 설명을 제공하여 보조 기술이 이 콘텐츠의 목적이나 추가 정보를 사용자에게 전달할 수 있게 합니다.       


**잘못된 예시 - 웹 애플리케이션 전체에 사용**
이 예시는 role="document"를 전체 웹 애플리케이션에 적용했으나, 이 역할은 특정 섹션을 독립된 문서로 나타낼 때 사용해야 하므로 부적절합니다.    
```sh
<div role="document">
  <header>
    <h1>My Web Application</h1>
  </header>
  <nav>
    <ul>
      <li>Home</li>
      <li>About</li>
      <li>Contact</li>
    </ul>
  </nav>
  <main>
    <p>Welcome to my web application!</p>
  </main>
</div>
```

**올바른 예시 - 문서 섹션에 사용**
이 예시는 &lt;div&gt; 요소에 role="directory"를 사용하여 디렉토리 구조를 명시적으로 나타냅니다. aria-expanded와 aria-level 속성을 사용해 항목의 계층 구조와 확장 상태를 지정하고 있습니다.   
```sh
<section role="document" aria-labelledby="doc-title">
  <h1 id="doc-title">User Guide</h1>
  <p>This guide provides detailed instructions on how to use the web application...</p>
</section>
```

**(권장) 시멘틱 마크업에서의 기본 사용**
이 예시는 시멘틱 마크업을 사용하여 &lt;article&gt; 요소로 독립된 문서 콘텐츠를 나타냅니다. 보조 기술은 이 콘텐츠를 문서로 인식하고 탐색할 수 있습니다.    
```sh
<article>
  <h1>Understanding Climate Change</h1>
  <p>Climate change is a long-term shift in weather patterns...</p>
</article>
```

### **8. feed 역할**    
feed 역할은 소셜 미디어 타임라인, 뉴스 피드, 블로그 목록과 같이 지속적으로 업데이트되는 항목의 집합을 나타냅니다. 이 역할은 보조 기술이 이러한 콘텐츠의 특성을 이해하고, 사용자에게 적절히 전달할 수 있도록 돕습니다. feed 역할은 주로 소셜 네트워크, 뉴스 애그리게이터, 블로그 플랫폼에서 사용됩니다.   
[W3C ARIA feed](https://www.w3.org/TR/wai-aria-1.2/#feed){: target="_blank"}   
[MDN ARIA feed](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/feed_role){: target="_blank"}   

**기본 설명**  
- feed 역할은 지속적으로 업데이트되는 콘텐츠 목록을 나타내며, 사용자가 이러한 동적 콘텐츠를 더 쉽게 탐색할 수 있도록 돕습니다. 이 역할은 보조 기술이 피드의 특성을 이해하고, 새로운 항목이 추가될 때 이를 사용자에게 전달할 수 있도록 설계되었습니다.    
- **적절한 사용**: feed 역할은 동적으로 갱신되는 콘텐츠에만 사용해야 하며, 각 피드 항목에 article 역할을 지정하여 보조 기술이 이를 독립적인 콘텐츠로 인식할 수 있도록 해야 합니다.    
- **중요한 점**: feed 역할을 사용하여 동적인 콘텐츠를 명확히 지정함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 피드를 쉽게 탐색하고, 최신 정보를 놓치지 않고 확인할 수 있습니다.    

**사용 시 주의사항**   
- **피드의 동적 특성 반영**: feed 역할은 지속적으로 갱신되는 콘텐츠 목록에 사용되어야 합니다. 사용자가 피드 내에서 항목을 쉽게 탐색하고, 새롭게 추가된 콘텐츠를 인식할 수 있도록 해야 합니다.   
- **실시간 업데이트 관리**: aria-live와 aria-busy 속성을 사용해 피드가 업데이트 중일 때 사용자에게 이를 명확히 알릴 수 있어야 합니다.
- **피드 항목에 적절한 역할 지정**: 피드 내의 각 항목에는 article 역할을 지정하여, 보조 기술이 각 항목을 독립적인 콘텐츠로 인식하고 처리할 수 있도록 해야 합니다.

**상속된 상태 및 속성**   
- **aria-busy**: 피드가 업데이트 중임을 나타내는 속성입니다. true로 설정되면 피드가 갱신 중임을 의미하며, 사용자가 새로운 콘텐츠가 추가되고 있음을 알 수 있습니다.       
- **aria-live**: 피드의 실시간 업데이트를 사용자에게 알릴 수 있도록 설정합니다. polite나 assertive로 설정하여 피드 항목이 업데이트될 때 보조 기술이 이를 어떻게 처리할지 지정할 수 있습니다.       
- **aria-relevant**: 피드에서 어떤 종류의 변경 사항(추가, 삭제, 텍스트 변경 등)을 보조 기술이 사용자에게 알릴지 지정합니다.       


**잘못된 예시 - 피드 역할의 부적절한 사용**
이 예시는 role="feed"를 단순한 콘텐츠 블록에 적용했으나, 이 블록은 지속적으로 갱신되는 동적 콘텐츠가 아니므로 부적절합니다. feed 역할은 주기적으로 업데이트되는 콘텐츠에만 사용해야 합니다.    
```sh
<div role="feed">
  <div>
    <h2>Welcome to Our Website</h2>
    <p>This is the homepage of our website...</p>
  </div>
  <div>
    <h2>About Us</h2>
    <p>Learn more about our company and team...</p>
  </div>
</div>
```

**올바른 예시 - 피드 역할의 적절한 사용**
이 예시는 role="feed"를 적절하게 사용하여 동적으로 갱신되는 콘텐츠 목록을 나타내고 있습니다. aria-live="polite"와 aria-relevant="additions" 속성을 사용해 피드가 업데이트될 때 사용자에게 알리도록 설정했습니다.   
```sh
<div role="feed" aria-live="polite" aria-relevant="additions">
  <div role="article">
    <h2>Latest Blog Post: The Future of AI</h2>
    <p>Artificial intelligence continues to advance...</p>
  </div>
  <div role="article">
    <h2>Health Tips: Staying Active in Winter</h2>
    <p>Winter can be a tough time to stay active...</p>
  </div>
</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용 예시**
이 예시는 시멘틱 마크업을 사용하여 &lt;article&gt; 요소로 독립된 문서 콘텐츠를 나타냅니다. 보조 기술은 이 콘텐츠를 문서로 인식하고 탐색할 수 있습니다.    
```sh
<article>
  <h1>Understanding Climate Change</h1>
  <p>Climate change is a long-term shift in weather patterns...</p>
</article>
```

**div 요소 마크업을 사용한 피드 예시**
&lt;div&gt; 요소에 role="feed"를 지정하여 피드 역할을 명시적으로 나타냅니다. 각 피드 항목은 role="article"을 사용해 독립적인 콘텐츠로 처리됩니다. aria-busy="true"로 설정하여 피드가 업데이트 중임을 알립니다.    
```sh
<div role="feed" aria-busy="true">
  <div role="article">
    <h2>Breaking News: Market Hits All-Time High</h2>
    <p>The stock market reached an all-time high today...</p>
  </div>
  <div role="article">
    <h2>New Tech Innovations in 2024</h2>
    <p>The tech industry is abuzz with new innovations...</p>
  </div>
</div>
```

**시멘틱 마크업을 사용한 피드 예시**
이 예시는 시멘틱 마크업을 사용하여 &lt;section&gt; 요소에 role="feed"를 지정했습니다. 각 피드 항목은 &lt;article&gt; 요소로 구성되어 있어 보조 기술이 이를 독립적인 콘텐츠로 처리할 수 있도록 했습니다.    
```sh
<section role="feed" aria-busy="false">
  <article>
    <h2>Breaking News: Market Hits All-Time High</h2>
    <p>The stock market reached an all-time high today...</p>
  </article>
  <article>
    <h2>New Tech Innovations in 2024</h2>
    <p>The tech industry is abuzz with new innovations...</p>
  </article>
</section>
```

### **9. figure 역할**    
figure 역할은 이미지, 차트, 삽화, 코드 블록 등 독립적으로 설명할 수 있는 콘텐츠의 묶음을 나타냅니다. 이 역할은 콘텐츠가 본문 내의 특정 부분과 관련이 있지만, 독립적으로 이해될 수 있는 것을 나타낼 때 사용됩니다. 일반적으로 figcaption 요소를 사용하여 설명(캡션)을 포함하며, 이 설명은 figure 요소에 속한 콘텐츠를 보충하는 데 사용됩니다.   
[W3C ARIA figure](https://www.w3.org/TR/wai-aria-1.2/#figure){: target="_blank"}   
[MDN ARIA figure](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/figure_role){: target="_blank"}   
[UXKM : figure element](https://uxkm.io/publishing/html/04-grouping/10-figure_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- figure 역할은 이미지나 그래픽과 같은 시각적 콘텐츠, 코드 블록 등 본문과 관련된 정보를 시각적으로 묶어주는 역할을 합니다.    
- figure 요소는 콘텐츠의 본문 흐름과는 독립적으로 재배치될 수 있으며, 콘텐츠의 참조로 사용될 수 있습니다. 이는 보조 기술이 이 콘텐츠를 별도로 인식하고, 사용자에게 전달할 수 있도록 돕습니다.    
- figcaption 요소는 figure 내에 포함된 콘텐츠를 설명하는 텍스트를 제공하며, 보조 기술은 이를 사용하여 콘텐츠의 의미를 사용자에게 전달합니다.    
- **적절한 사용**: figure 요소는 시각적 콘텐츠나 코드 블록을 그룹화하고, figcaption 요소를 사용해 설명을 제공하여 콘텐츠의 의미를 명확히 해야 합니다.    
- **중요한 점**: figure 역할을 사용하여 콘텐츠를 시멘틱하게 그룹화함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 시각적 콘텐츠의 맥락을 쉽게 이해하고, 필요한 정보를 효율적으로 찾을 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업 사용**: 시각적 콘텐츠나 코드 블록을 그룹화할 때는 &lt;figure&gt; 요소를 사용하여 시멘틱하게 표현하는 것이 중요합니다. 이는 콘텐츠의 의미를 명확히 하고, 보조 기술이 이를 올바르게 해석할 수 있도록 돕습니다.   
- **적절한 설명 제공**: figcaption 요소를 사용하여 figure 내 콘텐츠를 설명하는 캡션을 제공해야 합니다. 이는 콘텐츠의 맥락을 명확히 하여, 사용자가 내용을 이해하는 데 도움이 됩니다.
- **독립적인 콘텐츠로 취급**: figure 요소 내 콘텐츠는 본문 흐름과 독립적으로 이해될 수 있어야 하며, 이를 통해 다양한 위치에서 참조될 수 있습니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. figure 역할은 콘텐츠를 시멘틱하게 그룹화하는 역할을 하므로, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - 독립적인 콘텐츠로 취급되지 않는 경우**
이 예시는 &lt;div&gt; 요소를 사용하여 이미지를 설명하지만, 이 콘텐츠는 본문과 독립적으로 취급되지 않으며, 보조 기술이 이를 독립적인 콘텐츠로 인식하지 못할 수 있습니다. figure 요소를 사용하는 것이 더 적절합니다.    
```sh
<div>
  <img src="climate-change-graph.png" alt="Graph showing climate change over the last century">
  <p>This graph illustrates climate change over the past century.</p>
</div>
```

**올바른 예시 - 피드 역할의 적절한 사용**
이 예시는 role="feed"를 적절하게 사용하여 동적으로 갱신되는 콘텐츠 목록을 나타내고 있습니다. aria-live="polite"와 aria-relevant="additions" 속성을 사용해 피드가 업데이트될 때 사용자에게 알리도록 설정했습니다.   
```sh
<div role="feed" aria-live="polite" aria-relevant="additions">
  <div role="article">
    <h2>Latest Blog Post: The Future of AI</h2>
    <p>Artificial intelligence continues to advance...</p>
  </div>
  <div role="article">
    <h2>Health Tips: Staying Active in Winter</h2>
    <p>Winter can be a tough time to stay active...</p>
  </div>
</div>
```

**(권장) 올바른 예시 - 시멘틱 마크업에서의 기본 사용**
이 예시는 &lt;figure&gt; 요소를 사용하여 콘텐츠를 그룹화하고, figcaption 요소를 사용하여 설명을 제공합니다. 이 구조는 시멘틱하게 올바르며, 보조 기술이 이 콘텐츠를 올바르게 해석할 수 있도록 합니다.    
```sh
<figure>
  <img src="climate-change-graph.png" alt="Graph showing climate change over the last century">
  <figcaption>Figure 1: Climate change trends over the last 100 years.</figcaption>
</figure>
```

**div 요소 마크업을 사용한 figure 역할 예시**
이 예시는 &lt;div&gt; 요소에 role="figure"를 사용하여 figure 역할을 명시적으로 지정합니다. div 요소를 사용하여 설명 텍스트를 제공하고 있지만, figcaption 요소를 사용하는 것이 더 적절합니다.    
```sh
<div role="figure">
  <img src="climate-change-graph.png" alt="Graph showing climate change over the last century">
  <div>Figure 1: Climate change trends over the last 100 years.</div>
</div>
```

**시멘틱 마크업을 사용한 피드 예시**
이 예시는 시멘틱 마크업을 사용하여 &lt;section&gt; 요소에 role="feed"를 지정했습니다. 각 피드 항목은 &lt;article&gt; 요소로 구성되어 있어 보조 기술이 이를 독립적인 콘텐츠로 처리할 수 있도록 했습니다.    
```sh
<section role="feed" aria-busy="false">
  <article>
    <h2>Breaking News: Market Hits All-Time High</h2>
    <p>The stock market reached an all-time high today...</p>
  </article>
  <article>
    <h2>New Tech Innovations in 2024</h2>
    <p>The tech industry is abuzz with new innovations...</p>
  </article>
</section>
```

### **10. generic 역할**    
generic 역할은 특정 시멘틱한 의미를 가지지 않는 일반적인 컨테이너를 나타냅니다. 이 역할은 기본적으로 아무 의미도 부여되지 않는 요소를 설명하며, HTML의 기본적인 &lt;div&gt;와 &lt;span&gt; 요소와 유사한 역할을 합니다. generic 역할은 보조 기술이 해당 요소에 특별한 시멘틱이 부여되지 않았음을 이해하도록 돕습니다.   
[W3C ARIA generic](https://www.w3.org/TR/wai-aria-1.2/#generic){: target="_blank"}   
[MDN ARIA generic](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/generic_role){: target="_blank"}   

**기본 설명**  
- generic 역할은 시멘틱적으로 특별한 의미가 없는 요소에 할당됩니다. 특별한 의미 없이 레이아웃을 구성하거나 스타일링을 적용할 때 사용됩니다.    
- 보조 기술은 generic 역할을 가진 요소를 단순히 구조적인 컨테이너로 이해하며, 특별한 시멘틱 역할을 부여하지 않습니다.    
- generic 역할은 대부분의 경우 명시적으로 지정할 필요가 없으며, 기본적으로 시멘틱한 의미가 없는 요소에 암시적으로 적용됩니다.    
- **적절한 사용**: generic 역할은 기본적으로 HTML의 &lt;div&gt;나 &lt;span&gt; 요소에 적용되며, 특별한 의미를 부여할 필요가 없는 경우에 사용됩니다. 대부분의 경우 명시적으로 지정할 필요는 없으며, 가능한 경우 시멘틱한 HTML 요소를 사용하는 것이 좋습니다.    
- **중요한 점**: 시멘틱한 의미가 중요한 요소에 generic 역할을 부여하는 것은 피해야 하며, 문서의 구조와 의미를 명확히 하는 데 중점을 두어야 합니다. 이를 통해 사용자 경험과 접근성을 향상시킬 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱한 의미를 부여할 필요가 없는 경우에 사용**: generic 역할은 콘텐츠에 특별한 시멘틱 의미를 부여할 필요가 없는 경우에 사용됩니다. 레이아웃이나 스타일링을 위한 단순한 컨테이너를 만들 때 적합합니다.   
- **필요하지 않은 경우 명시적으로 사용하지 않음**: 대부분의 경우 &lt;div&gt;나 &lt;span&gt; 같은 요소는 자동으로 generic 역할을 수행하므로, 명시적으로 role="generic"을 지정할 필요가 없습니다.
- **시멘틱 마크업을 우선 사용**: 가능한 경우, generic 역할보다는 시멘틱한 HTML 요소를 사용하여 문서 구조와 의미를 명확히 하는 것이 좋습니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. generic 역할은 의미 없는 일반적인 컨테이너를 나타내므로, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - generic 역할을 사용하지 않아야 하는 경우**
이 예시는 header 요소에 role="generic"을 지정하여 시멘틱한 의미를 제거했으나, header 요소는 시멘틱하게 중요한 역할을 하므로 generic 역할을 사용하지 말아야 합니다.    
```sh
<header role="generic">
  <h1>Website Header</h1>
</header>
```

**올바른 예시 - 시멘틱한 요소를 유지**
이 예시는 header 요소에 시멘틱한 역할을 유지하여 웹 페이지의 구조와 의미를 명확히 합니다. 이 경우, generic 역할을 사용하지 않고 기본 시멘틱 역할을 유지하는 것이 적절합니다.   
```sh
<header>
  <h1>Website Header</h1>
</header>
```

**(권장) 마크업에서의 기본 사용**
이 예시는 &lt;div&gt; 요소를 사용하여 단순히 레이아웃을 구성하고 있습니다. 이 경우, div는 암시적으로 generic 역할을 수행합니다.    
```sh
<div>
  <p>This is a paragraph inside a div.</p>
</div>
```

### **11. group 역할**    
group 역할은 여러 요소를 논리적으로 묶어 하나의 그룹으로 취급하는 데 사용됩니다. 이 역할은 보조 기술이 이러한 요소들이 하나의 논리적 단위로 묶여 있음을 인식하게 하여, 사용자에게 이를 일관되게 전달할 수 있도록 합니다. group 역할은 주로 폼 요소, 메뉴 항목, 또는 기타 연관된 컨텐츠를 그룹화할 때 사용됩니다.   
[W3C ARIA group](https://www.w3.org/TR/wai-aria-1.2/#group){: target="_blank"}   
[MDN ARIA group](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role){: target="_blank"}   
[UXKM : fieldset element](https://uxkm.io/publishing/html/09-forms/13-fieldset_element){: target="_blank"}   
[UXKM : legend element](https://uxkm.io/publishing/html/09-forms/14-legend_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- group 역할은 연관된 요소들을 논리적으로 그룹화하여, 보조 기술이 이들 요소를 하나의 단위로 인식하도록 돕습니다.    
- 이 역할은 보통 여러 개의 컨트롤(예: 라디오 버튼 그룹, 체크박스 그룹) 또는 메뉴 항목, 대화 상자에서 연관된 섹션을 그룹화할 때 사용됩니다.    
- group 역할은 그룹화된 요소들을 보조 기술이 올바르게 이해하고, 사용자에게 논리적인 단위로 전달할 수 있도록 합니다.    
- **적절한 사용**: group 역할은 논리적으로 관련된 요소들을 묶는 데 사용해야 하며, 불필요한 경우에는 사용하지 않는 것이 좋습니다. 시멘틱한 HTML 요소를 사용하는 것이 가능하다면, 이를 우선적으로 사용해야 합니다.    
- **중요한 점**: group 역할을 통해 웹 페이지의 구조를 명확하게 하고, 사용자 경험과 접근성을 향상시킬 수 있습니다. 이를 통해 사용자는 그룹화된 콘텐츠를 쉽게 탐색하고 이해할 수 있습니다.    

**사용 시 주의사항**   
- **연관된 요소를 논리적으로 그룹화**: group 역할은 연관된 요소들을 묶어서 하나의 논리적인 단위로 처리해야 할 때 사용됩니다. 이를 통해 보조 기술이 요소들 간의 관계를 이해하고 사용자에게 전달할 수 있습니다.   
- **적절한 제목과 설명 제공**: aria-labelledby와 aria-describedby 속성을 사용해 그룹의 제목과 설명을 제공하면, 보조 기술이 이를 올바르게 사용자에게 전달할 수 있습니다.
- **사용하지 말아야 할 경우**: 시멘틱하게 그룹화가 필요한 경우에는, 시멘틱 HTML 요소(예: &lt;fieldset&gt;과 &lt;legend&gt; 조합)를 사용하는 것이 좋습니다. 불필요하게 group 역할을 사용하는 것은 피해야 합니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: 그룹의 제목을 지정하여, 보조 기술이 이 그룹의 제목을 그룹과 연관지어 사용자에게 전달할 수 있게 합니다.       
- **aria-describedby**: 그룹에 대한 추가 설명을 제공하여, 보조 기술이 이 설명을 그룹과 연관지어 사용자에게 전달할 수 있게 합니다.       


**잘못된 예시 - 불필요한 그룹화**
이 예시는 논리적인 그룹화가 필요하지 않은 콘텐츠에 role="group"을 사용했습니다. 불필요한 그룹화는 보조 기술의 해석을 혼란스럽게 할 수 있으므로 피해야 합니다.    
```sh
<div role="group">
  <h1>Welcome to Our Website</h1>
  <p>Explore our features and content to learn more.</p>
</div>
```

**올바른 예시 - 의미 있는 그룹화**
이 예시는 네비게이션 메뉴를 &lt;div&gt; 요소에 role="group"을 사용해 논리적으로 그룹화한 예시입니다. aria-labelledby 속성을 통해 그룹의 제목을 지정하여, 보조 기술이 이 정보를 사용자에게 전달할 수 있게 했습니다.   
```sh
<header>
  <h1>Website Header</h1>
</header>
```

**(권장) 시멘틱 마크업을 사용한 기본 그룹화 사용 예시**
이 예시는 &lt;fieldset&gt;과 &lt;legend&gt; 요소를 사용하여 라디오 버튼을 그룹화하고 있습니다. 보조 기술은 이 그룹을 논리적 단위로 인식하여 사용자에게 전달합니다.    
```sh
<fieldset>
  <legend>Select your favorite fruit:</legend>
  <label><input type="radio" name="fruit" value="apple"> Apple</label>
  <label><input type="radio" name="fruit" value="banana"> Banana</label>
  <label><input type="radio" name="fruit" value="cherry"> Cherry</label>
</fieldset>
```

**div 요소 마크업을 사용한 그룹화 예시**
이 예시는 &lt;div&gt; 요소에 role="group"을 지정하고, aria-labelledby 속성을 사용해 그룹의 제목을 연결한 예시입니다. &lt;fieldset&gt;을 사용할 수 없는 상황에서 유용합니다.    
```sh
<div role="group" aria-labelledby="fruit-group-label">
  <span id="fruit-group-label">Select your favorite fruit:</span>
  <label><input type="radio" name="fruit" value="apple"> Apple</label>
  <label><input type="radio" name="fruit" value="banana"> Banana</label>
  <label><input type="radio" name="fruit" value="cherry"> Cherry</label>
</div>
```

### **12. heading 역할**    
heading 역할은 웹 페이지나 애플리케이션의 구조를 정의하는 데 사용되는 제목을 나타냅니다. 이 역할은 콘텐츠의 계층적 구조를 명확히 하여, 보조 기술이 문서의 내용과 구조를 쉽게 파악할 수 있도록 돕습니다. HTML에서 &lt;h1&gt;부터 &lt;h6&gt;까지의 제목 요소가 기본적으로 이 역할을 수행합니다.   
[W3C ARIA heading](https://www.w3.org/TR/wai-aria-1.2/#heading){: target="_blank"}   
[MDN ARIA heading](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/heading_role){: target="_blank"}   
[UXKM : heading element](https://uxkm.io/publishing/html/03-sections/02-heading_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- heading 역할은 콘텐츠의 주요 섹션을 설명하거나 요약하는 제목을 나타내며, 문서나 애플리케이션의 구조를 이해하는 데 중요한 역할을 합니다.    
- 이 역할은 HTML의 제목 요소(h1, h2, h3, h4, h5, h6)에서 자동으로 적용되지만, 필요에 따라 다른 요소에도 적용할 수 있습니다.    
- 보조 기술은 heading 역할을 통해 제목의 중요도와 문서의 계층적 구조를 인식하여, 사용자에게 적절한 정보로 전달할 수 있습니다.    
- **적절한 사용**: 시멘틱한 제목 요소(&lt;h1&gt; ~ &lt;h6&gt;)를 사용하여 문서의 구조를 명확히 하고, 필요할 경우 다른 요소에 role="heading"과 aria-level 속성을 지정할 수 있습니다. 계층 구조는 일관되게 유지해야 합니다.    
- **중요한 점**: heading 역할을 통해 웹 페이지의 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 콘텐츠를 쉽게 탐색하고, 문서의 흐름을 이해할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 제목 요소(&lt;h1&gt; ~ &lt;h6&gt;)를 사용하는 것이 좋습니다. 이들은 자동으로 heading 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **적절한 계층 구조 유지**: 제목 요소나 heading 역할을 사용할 때, aria-level 속성을 통해 문서의 계층 구조를 일관되게 유지해야 합니다. 올바른 계층 구조는 보조 기술이 콘텐츠를 정확하게 이해하고 전달하는 데 필수적입니다.
- **과도한 사용 피하기**: heading 역할은 중요하지 않은 텍스트나 단락에 사용하지 않도록 주의해야 합니다. 제목의 의미가 있는 콘텐츠에만 사용해야 합니다.

**상속된 상태 및 속성**   
- **aria-level**: 이 속성은 제목의 계층 구조를 나타냅니다. 1에서 6까지의 숫자로 설정할 수 있으며, 이는 HTML의 &lt;h1&gt;에서 &lt;h6&gt;까지와 대응됩니다. 예를 들어, aria-level="1"은 가장 높은 수준의 제목을 나타냅니다.       


**잘못된 예시 - 일관되지 않은 계층 구조**
이 예시는 제목 요소의 계층 구조가 일관되지 않아, 보조 기술이 문서의 구조를 올바르게 해석하는 데 어려움을 겪을 수 있습니다. 제목의 순서를 일관되게 유지해야 합니다.    
```sh
<h1>Main Title</h1>
<h3>Subheading 1</h3>
<p>This is a paragraph under Subheading 1.</p>
<h2>Subheading 2</h2>
<p>This is a paragraph under Subheading 2.</p>
```

**(권장) 올바른 예시 - 시멘틱 마크업을 사용**
이 예시는 HTML 제목 요소(&lt;h1&gt;, &lt;h2&gt;)를 사용하여 문서의 계층 구조를 정의하고 있습니다. 이 구조는 보조 기술이 문서의 내용을 쉽게 탐색하고 이해하는 데 도움을 줍니다.    
```sh
<h1>Main Title</h1>
<h2>Subheading 1</h2>
<p>This is a paragraph under Subheading 1.</p>
<h2>Subheading 2</h2>
<p>This is a paragraph under Subheading 2.</p>
```

**명시적으로 heading 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="heading"과 aria-level 속성을 사용하여 제목의 계층 구조를 정의하고 있습니다. 이는 시멘틱한 제목 요소를 사용할 수 없는 상황에서 유용합니다.    
```sh
<div role="heading" aria-level="1">Main Title</div>
<div role="heading" aria-level="2">Subheading 1</div>
<p>This is a paragraph under Subheading 1.</p>
<div role="heading" aria-level="2">Subheading 2</div>
<p>This is a paragraph under Subheading 2.</p>
```

### **13. img 역할**    
img 역할은 웹 페이지에서 이미지 콘텐츠를 나타내는 데 사용됩니다. 이 역할은 시각적 정보를 전달하는 이미지를 설명하며, 보조 기술이 이러한 이미지를 사용자에게 올바르게 전달할 수 있도록 돕습니다. HTML의 &lt;img&gt; 요소는 자동으로 img 역할을 수행합니다. 이 역할은 특히 접근성 측면에서 중요한 역할을 하며, 적절한 대체 텍스트(alt 텍스트)를 제공하는 것이 핵심입니다.   
[W3C ARIA img](https://www.w3.org/TR/wai-aria-1.2/#img){: target="_blank"}   
[MDN ARIA img](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/img_role){: target="_blank"}   
[UXKM : img element](https://uxkm.io/publishing/html/06-embedded/02-img_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- img 역할은 이미지를 나타내며, HTML의 &lt;img&gt; 요소에 암시적으로 적용됩니다. 그러나 다른 요소(예: CSS 배경 이미지가 없는 &lt;div&gt; 등)를 이미지로 처리할 때 이 역할을 명시적으로 지정할 수 있습니다.    
- 보조 기술은 img 역할을 통해 이미지의 의미나 용도를 사용자에게 전달합니다. 이때 중요한 것은 이미지의 대체 텍스트(alt 텍스트)입니다. 대체 텍스트는 이미지의 내용이나 기능을 설명하는 중요한 정보로, 모든 사용자가 이미지의 의미를 이해할 수 있도록 돕습니다.    
- 시각적 정보가 중요하지 않은 장식용 이미지는 aria-hidden="true"를 사용하거나, 빈 대체 텍스트(alt="")를 지정하여 보조 기술이 이를 무시하도록 해야 합니다.    
- **적절한 사용**: 모든 &lt;img&gt; 요소에 의미 있는 alt 속성을 제공하고, 비표준 마크업에서 이미지를 사용할 때는 role="img"와 aria-label을 명시적으로 지정해야 합니다. 장식용 이미지는 사용자에게 불필요한 정보를 제공하지 않도록 해야 합니다.    
- **중요한 점**: img 역할을 통해 웹 페이지의 시각적 콘텐츠를 명확하게 정의하고, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 시각적 정보를 효과적으로 이해하고, 필요한 내용을 효율적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **적절한 대체 텍스트 제공**: 모든 &lt;img&gt; 요소에 적절한 alt 속성을 제공해야 합니다. 이 속성은 이미지의 의미나 기능을 설명하며, 보조 기술이 이를 사용자에게 전달할 수 있도록 돕습니다.   
- **장식용 이미지 무시**: 시각적 정보가 중요하지 않은 장식용 이미지는 aria-hidden="true"를 사용하거나, 빈 대체 텍스트(alt="")를 지정하여 보조 기술이 이를 무시하도록 해야 합니다.
- **비표준 마크업 사용 시 명시적 역할 지정**: &lt;img&gt; 요소 대신 다른 요소(예: CSS로 배경 이미지를 설정한 &lt;div&gt;)에 이미지를 사용할 때는, role="img"와 aria-label 또는 aria-labelledby를 사용해 이미지의 의미를 명확히 전달해야 합니다.

**상속된 상태 및 속성**   
- **alt 속성**: 이미지의 대체 텍스트를 지정하여, 보조 기술이 이 텍스트를 사용자에게 전달할 수 있도록 합니다.       
- **aria-label**: 이미지에 설명을 추가할 수 있는 속성으로, alt 속성 대신 사용할 수 있지만, 대부분의 경우 alt 속성이 선호됩니다.       
- **aria-hidden**: 장식용 이미지나 사용자에게 제공될 필요가 없는 이미지를 숨길 때 사용됩니다.       


**잘못된 예시 - 대체 텍스트가 없는 이미지**
이 예시는 중요한 다이어그램 이미지를 대체 텍스트 없이 사용하고 있으며, 이는 접근성에 부정적인 영향을 미칩니다. 모든 중요한 이미지에는 적절한 alt 속성을 제공해야 합니다.    
```sh
<img src="important-diagram.png">
```

**(권장) 올바른 예시 - 대체 텍스트가 포함된 이미지**
이 예시는 중요한 다이어그램 이미지를 설명하는 대체 텍스트와 함께 사용하여, 보조 기술이 이미지를 사용자에게 올바르게 전달할 수 있도록 했습니다.    
```sh
<img src="important-diagram.png" alt="Diagram showing the process of photosynthesis">
```

**(권장) 시멘틱 마크업에서의 기본 사용**
이 예시는 &lt;img&gt; 요소를 사용하여 회사 로고를 나타내고 있으며, alt 속성으로 대체 텍스트를 제공하고 있습니다. 보조 기술은 이 텍스트를 사용자에게 전달하여 이미지의 의미를 이해할 수 있도록 합니다.    
```sh
<img src="logo.png" alt="Company Logo">
```

**명시적으로 img 역할 지정 예시**
이 예시는 CSS 배경 이미지를 사용한 &lt;div&gt; 요소에 role="img"와 aria-label을 사용해 이미지의 의미를 지정하고 있습니다. 이는 &lt;img&gt; 요소를 사용할 수 없는 상황에서 유용합니다.    
```sh
<div role="img" aria-label="Company Logo" style="background-image: url('logo.png'); width: 100px; height: 100px;"></div>
```

**장식용 이미지 처리 예시**
이 예시는 장식용 이미지를 나타내며, alt=""와 aria-hidden="true"를 사용하여 보조 기술이 이 이미지를 무시하도록 설정했습니다. 이로 인해 사용자는 불필요한 시각적 정보에 방해받지 않습니다.    
```sh
<img src="decorative.png" alt="" aria-hidden="true">
```

### **14. list 역할**    
list 역할은 항목들이 모여 있는 목록을 나타내는 데 사용됩니다. 이 역할은 항목들 간의 관계를 정의하고, 보조 기술이 이러한 항목들이 논리적으로 그룹화되어 있음을 인식할 수 있도록 돕습니다. HTML에서 &lt;ul&gt;, &lt;ol&gt;, &lt;dl&gt; 요소가 기본적으로 list 역할을 수행합니다.   
[W3C ARIA list](https://www.w3.org/TR/wai-aria-1.2/#list){: target="_blank"}   
[MDN ARIA list](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/list_role){: target="_blank"}   
[UXKM : ul element](https://uxkm.io/publishing/html/04-grouping/04-ul_element#gsc.tab=0){: target="_blank"}   
[UXKM : ol element](https://uxkm.io/publishing/html/04-grouping/03-ol_element#gsc.tab=0){: target="_blank"}   
[UXKM : dl element](https://uxkm.io/publishing/html/04-grouping/06-dl_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- list 역할은 항목들의 집합을 의미하며, 목록 구조를 정의하는 데 사용됩니다. 이는 보조 기술이 목록을 그룹으로 인식하고, 항목들 간의 관계를 올바르게 전달할 수 있도록 합니다.    
- 이 역할은 주로 &lt;ul&gt;(비순서형 목록), &lt;ol&gt;(순서형 목록), &lt;dl&gt;(정의 목록) 요소에서 자동으로 적용됩니다.    
- list 역할은 다른 요소에 적용할 수 있으며, 해당 요소가 목록처럼 동작하도록 할 수 있습니다.    
- **적절한 사용**: 시멘틱한 HTML 목록 요소(&lt;ul&gt;, &lt;ol&gt;, &lt;dl&gt;)를 사용하여 목록을 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="list"와 role="listitem"을 명시적으로 지정해야 합니다. 목록 구조는 일관되게 유지되어야 하며, 불필요한 경우에 list 역할을 사용하지 않는 것이 좋습니다.    
- **중요한 점**: list 역할을 통해 웹 페이지의 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 목록을 쉽게 탐색하고, 항목들 간의 관계를 명확히 이해할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업 우선 사용**: 가능한 경우, 시멘틱한 HTML 목록 요소(&lt;ul&gt;, &lt;ol&gt;, &lt;dl&gt;)를 사용하여 목록을 정의하는 것이 좋습니다. 이들은 자동으로 list 역할을 수행하며, 문서의 구조를 명확하게 정의합니다.   
- **일관된 구조 유지**: 목록을 정의할 때는 일관된 구조를 유지하여, 보조 기술이 목록 항목 간의 관계를 명확하게 인식할 수 있도록 해야 합니다.
- **목록 항목 정의**: list 역할과 함께 listitem 역할을 사용하여 목록 항목을 명확하게 정의해야 합니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: 목록의 제목을 지정하여, 보조 기술이 목록을 사용자에게 명확하게 설명할 수 있도록 돕습니다.       
- **aria-describedby**: 목록에 대한 추가 설명을 제공하여, 보조 기술이 이 설명을 목록과 연관지어 사용자에게 전달할 수 있게 합니다.       


**잘못된 예시 - 목록 항목에 listitem 역할 누락**
이 예시는 listitem 역할을 명시하지 않아 보조 기술이 목록 항목을 올바르게 인식하지 못할 수 있습니다. 목록 항목에는 반드시 listitem 역할을 지정해야 합니다.    
```sh
<div role="list">
  <div>Apples</div>
  <div>Bananas</div>
  <div>Cherries</div>
</div>
```

**올바른 예시 - 일관된 목록 구조 유지**
이 예시는 role="list"와 role="listitem"을 사용하여 목록과 목록 항목을 명확하게 정의하고, aria-labelledby 속성으로 목록의 제목을 지정하여 보조 기술이 목록을 올바르게 설명할 수 있도록 했습니다.    
```sh
<div role="list" aria-labelledby="fruit-list">
  <h2 id="fruit-list">Favorite Fruits</h2>
  <div role="listitem">Apples</div>
  <div role="listitem">Bananas</div>
  <div role="listitem">Cherries</div>
</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용**
이 예시는 HTML의 &lt;ul&gt; 요소를 사용하여 비순서형 목록을 정의하고 있습니다. 각 항목은 &lt;li&gt; 요소로 표시되며, 이 구조는 자동으로 list와 listitem 역할을 수행합니다.    
```sh
<ul>
  <li>Apples</li>
  <li>Bananas</li>
  <li>Cherries</li>
</ul>
```

**명시적으로 list 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="list"를 지정하고, 각 항목에 role="listitem"을 사용하여 비표준 마크업에서 목록을 정의한 예시입니다. 이는 시멘틱한 목록 요소를 사용할 수 없는 상황에서 유용합니다.    
```sh
<div role="list">
  <div role="listitem">Apples</div>
  <div role="listitem">Bananas</div>
  <div role="listitem">Cherries</div>
</div>
```

### **15. listitem 역할**    
listitem 역할은 목록 내의 개별 항목을 나타냅니다. 이 역할은 항목들이 논리적으로 그룹화된 list 요소 내에서 사용되며, 보조 기술이 각 항목을 독립적으로 식별하고, 사용자에게 목록의 내용을 명확하게 전달할 수 있도록 돕습니다. HTML에서 &lt;li&gt; 요소가 기본적으로 listitem 역할을 수행합니다.   
[W3C ARIA listitem](https://www.w3.org/TR/wai-aria-1.2/#listitem){: target="_blank"}   
[MDN ARIA listitem](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listitem_role){: target="_blank"}   
[UXKM : li element](https://uxkm.io/publishing/html/04-grouping/05-li_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- listitem 역할은 목록(list 역할을 가진 요소) 내에서 각 항목을 나타냅니다. 이 역할은 목록 항목을 구성하는 중요한 요소로, 보조 기술이 목록의 구조를 이해하고, 각 항목을 사용자에게 올바르게 전달할 수 있도록 합니다.    
- HTML에서 &lt;li&gt; 요소는 자동으로 listitem 역할을 수행하며, 목록의 맥락에 맞게 적절히 사용됩니다.    
- listitem 역할은 비표준 마크업에서 목록 항목을 명확히 정의할 때 유용하게 사용할 수 있습니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;li&gt;)를 사용하여 목록 항목을 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="listitem"을 명시적으로 지정해야 합니다. listitem 역할은 반드시 list 역할을 가진 요소 내에서 사용되어야 합니다.    
- **중요한 점**: listitem 역할을 통해 웹 페이지의 목록 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 목록을 쉽게 탐색하고, 항목들 간의 관계를 명확히 이해할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 목록 요소(&lt;li&gt;)를 사용하여 목록 항목을 정의하는 것이 좋습니다. 이는 자동으로 listitem 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **list 역할과 함께 사용**: listitem 역할은 반드시 list 역할을 가진 요소 내에서 사용해야 합니다. 독립적으로 사용하면 보조 기술이 이를 목록 항목으로 인식하지 못할 수 있습니다.
- **비표준 마크업에서의 사용**: 시멘틱한 HTML 요소를 사용할 수 없는 경우, role="listitem"을 사용하여 비표준 마크업에서도 목록 항목을 명확히 정의할 수 있습니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. listitem 역할은 단순히 목록 항목을 정의하는 역할을 하므로, 특별한 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - listitem 역할을 list 없이 사용**
이 예시는 list 역할을 가진 요소 없이 listitem 역할을 사용하고 있으며, 이는 보조 기술이 이 항목을 목록의 일부로 인식하지 못하게 할 수 있습니다. listitem 역할은 항상 list 역할 내에서 사용되어야 합니다.    
```sh
<div role="listitem">Item without list context</div>
```

**올바른 예시 - list 역할과 함께 사용**
이 예시는 role="list"와 role="listitem"을 함께 사용하여 목록과 목록 항목을 명확하게 정의하고, aria-labelledby 속성으로 목록의 제목을 지정하여 보조 기술이 목록을 올바르게 설명할 수 있도록 했습니다.    
```sh
<div role="list" aria-labelledby="todo-list">
  <h2 id="todo-list">To-Do List</h2>
  <div role="listitem">Buy groceries</div>
  <div role="listitem">Call the bank</div>
  <div role="listitem">Schedule a doctor's appointment</div>
</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용**
이 예시는 HTML의 &lt;ul&gt; 요소 내에서 &lt;li&gt; 요소를 사용하여 목록 항목을 정의하고 있습니다. 각 &lt;li&gt; 요소는 자동으로 listitem 역할을 수행합니다.    
```sh
<ul>
  <li>Apples</li>
  <li>Bananas</li>
  <li>Cherries</li>
</ul>
```

**명시적으로 listitem 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="listitem"을 지정하여 마크업에서 목록 항목을 정의한 예시입니다. 이는 시멘틱한 목록 요소를 사용할 수 없는 상황에서 유용합니다.    
```sh
<div role="list">
  <div role="listitem">First item</div>
  <div role="listitem">Second item</div>
  <div role="listitem">Third item</div>
</div>
```

### **16. math 역할**    
math 역할은 수학적 표현이나 수식을 나타내는 콘텐츠를 정의하는 데 사용됩니다. 이 역할은 보조 기술이 수식이나 수학적 내용을 올바르게 이해하고, 사용자에게 적절히 전달할 수 있도록 돕습니다. HTML의 &lt;math&gt; 요소 또는 MathML(Markup Language for Mathematical Notation)을 사용하여 수학적 표현을 나타낼 수 있습니다.   
[W3C ARIA math](https://www.w3.org/TR/wai-aria-1.2/#math){: target="_blank"}   
[MDN ARIA math](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/math_role){: target="_blank"}   
[MDN math element](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/math){: target="_blank"}   

**기본 설명**  
- math 역할은 수학적 표현을 나타내며, 보조 기술이 수학적 콘텐츠를 사용자에게 올바르게 전달할 수 있도록 합니다.    
- 이 역할은 복잡한 수식을 포함한 콘텐츠를 시각적으로 명확하게 표현하고, 보조 기술이 이를 음성으로 표현하거나, 다른 형식으로 변환하여 사용자에게 제공할 수 있도록 합니다.    
- math 역할은 일반적으로 MathML(Markup Language for Mathematical Notation)과 함께 사용되지만, HTML 요소에도 적용될 수 있습니다.    
- **적절한 사용**: 복잡한 수식이나 수학적 표현에는 가능한 MathML을 사용하는 것이 가장 바람직하며, HTML 요소에서 수식을 표현할 경우 role="math"를 명시적으로 지정하여 보조 기술이 이를 인식할 수 있도록 해야 합니다. 중요한 수식에는 대체 텍스트나 설명을 제공하여 접근성을 향상시킬 수 있습니다.    
- **중요한 점**: math 역할을 통해 수학적 콘텐츠를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 수식을 쉽게 이해하고, 필요한 내용을 효율적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **MathML 사용 권장**: 수학적 표현이 복잡하거나 다양한 기호를 포함하는 경우, MathML을 사용하는 것이 좋습니다. MathML은 수학적 표현을 시멘틱하게 정의하고, 다양한 출력 장치와 보조 기술에서 일관되게 표현할 수 있도록 합니다.   
- **대체 텍스트 제공**: 수학적 표현이 보조 기술에 의해 정확하게 전달되지 않을 수 있으므로, 중요한 수식에는 대체 텍스트를 제공하여 수식을 설명하는 것이 좋습니다.
- **적절한 역할 지정**: 비표준 마크업에서 수학적 표현을 정의하는 경우, role="math"를 명시적으로 지정하여 보조 기술이 이를 수학적 콘텐츠로 인식하도록 해야 합니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. math 역할은 수학적 표현을 정의하는 역할을 하므로, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - 수학적 표현을 일반 텍스트로 처리**
이 예시는 수학적 표현을 일반 텍스트로만 제공하고 있으며, math 역할이나 대체 텍스트가 없어 보조 기술이 이 수식을 올바르게 해석하지 못할 수 있습니다. 적절한 역할 지정이나 MathML 사용이 필요합니다.    
```sh
<p>a = (-b ± √(b² - 4ac)) / 2a</p>
```

**올바른 예시 - MathML과 함께 math 역할 사용**
이 예시는 MathML과 함께 role="math"을 사용하여 수학적 표현을 명확히 정의하고 있으며, aria-labelledby 속성을 통해 수식의 의미를 설명하는 레이블을 제공하고 있습니다.    
```sh
<div role="math" aria-labelledby="equation-label">
  <p id="equation-label">Quadratic formula:</p>
  <math xmlns="http://www.w3.org/1998/Math/MathML">
    <mrow>
      <mi>a</mi>
      <mo>=</mo>
      <mfrac>
        <mrow>
          <mtext>b</mtext>
          <mo>&#xB1;</mo>
          <msqrt>
            <mrow>
              <msup>
                <mi>b</mi>
                <mn>2</mn>
              </msup>
              <mo>-</mo>
              <mn>4ac</mn>
            </mrow>
          </msqrt>
        </mrow>
        <mrow>
          <mn>2a</mn>
        </mrow>
      </mfrac>
    </mrow>
  </math>
</div>
```

**(권장) MathML을 사용한 수학적 표현 예시**
이 예시는 MathML을 사용하여 이차 방정식의 해를 나타내는 수식을 표현하고 있습니다. MathML은 수학적 표현을 시멘틱하게 정의하며, 다양한 출력 장치와 보조 기술에서 일관되게 표현할 수 있도록 합니다.    
```sh
<math xmlns="http://www.w3.org/1998/Math/MathML">
  <mrow>
    <mi>a</mi>
    <mo>=</mo>
    <mfrac>
      <mrow>
        <mtext>b</mtext>
        <mo>&#xB1;</mo>
        <msqrt>
          <mrow>
            <msup>
              <mi>b</mi>
              <mn>2</mn>
            </msup>
            <mo>-</mo>
            <mn>4ac</mn>
          </mrow>
        </msqrt>
      </mrow>
      <mrow>
        <mn>2a</mn>
      </mrow>
    </mfrac>
  </mrow>
</math>
```

**명시적으로 math 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="math"를 지정하여 수학적 표현을 명시적으로 나타내고 있으며, aria-label을 사용해 수식의 의미를 설명하고 있습니다. MathML을 사용할 수 없는 상황에서 유용한 방법입니다.    
```sh
<div role="math" aria-label="Quadratic formula">
  <p>a = (-b ± √(b² - 4ac)) / 2a</p>
</div>
```

### **17. note 역할**    
note 역할은 웹 페이지나 애플리케이션에서 부가적인 정보를 제공하는 데 사용됩니다. 이 역할은 중요한 정보를 보완하거나, 추가적인 설명을 제공하기 위한 콘텐츠를 나타내며, 보조 기술이 이 정보를 사용자에게 명확히 전달할 수 있도록 돕습니다. 일반적으로 노트, 팁, 경고 등과 같은 콘텐츠를 설명하는 데 사용됩니다.   
[W3C ARIA note](https://www.w3.org/TR/wai-aria-1.2/#note){: target="_blank"}   
[MDN ARIA note](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/note_role){: target="_blank"}   

**기본 설명**  
- note 역할은 주 콘텐츠와는 별도로 부가적인 정보를 제공하는 데 사용되며, 이 정보는 본문의 내용이나 주요 콘텐츠를 보완하는 역할을 합니다.    
- note 역할은 콘텐츠의 흐름을 중단하지 않으면서 중요한 정보를 제공할 때 유용합니다.    
- 보조 기술은 이 역할을 통해 사용자가 페이지 내에서 노트나 추가 설명을 쉽게 탐색하고, 필요한 정보를 얻을 수 있도록 돕습니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(예: &lt;aside&gt;, &lt;blockquote&gt;)를 사용하여 부가적인 정보를 제공하는 것이 가장 바람직하며, 비표준 마크업에서는 role="note"를 명시적으로 지정해야 합니다. note 역할은 콘텐츠의 주요 흐름을 방해하지 않도록 주의 깊게 사용해야 합니다.    
- **중요한 점**: note 역할을 통해 부가적인 정보를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 필요한 추가 정보를 쉽게 이해하고, 문서의 내용을 효과적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **콘텐츠의 주요 흐름을 방해하지 않도록 주의**: note 역할은 부가적인 정보나 설명을 제공하기 위해 사용되므로, 콘텐츠의 주요 흐름을 방해하지 않도록 배치해야 합니다.   
- **시멘틱 마크업 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(예: &lt;aside&gt;, &lt;blockquote&gt;)를 사용하여 부가적인 정보를 제공하는 것이 좋습니다. 이들은 자동으로 부가적인 정보를 설명하는 역할을 수행합니다.
- **명확한 정보 제공**: note 역할을 사용하여 제공되는 정보는 명확하고 간결하게 작성되어야 하며, 사용자에게 중요한 추가 정보를 전달할 수 있어야 합니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. note 역할은 부가적인 정보를 제공하는 역할을 하므로, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - note 역할을 사용하지 않아야 하는 경우**
이 예시는 페이지의 주요 제목에 note 역할을 사용했으나, 이는 잘못된 사용입니다. note 역할은 부가적인 정보나 설명을 제공할 때 사용되어야 하며, 주 콘텐츠에 적용해서는 안 됩니다.    
```sh
<div role="note">
  <h1>Welcome to Our Website</h1>
</div>
```

**올바른 예시 - note 역할의 적절한 사용**
이 예시는 부가적인 정보를 제공하는 데 role="note"를 적절하게 사용하여, 보조 기술이 이 정보를 올바르게 사용자에게 전달할 수 있도록 했습니다.    
```sh
<div role="note">
  <p>Note: Make sure to check your email for order confirmation.</p>
</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용 예시**
이 예시는 HTML의 &lt;aside&gt; 요소를 사용하여 추가적인 정보를 제공하고 있습니다. &lt;aside&gt; 요소는 부가적인 정보를 나타내며, 자동으로 note 역할을 수행합니다.    
```sh
<aside>
  <p>Note: This product is only available in select regions.</p>
</aside>
```

**명시적으로 note 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="note"를 지정하여 비표준 마크업에서 추가 정보를 제공하는 예시입니다. 이 방법은 시멘틱한 요소를 사용할 수 없는 상황에서 유용합니다.    
```sh
<div role="note">
  <p>Tip: You can save 10% by signing up for our newsletter.</p>
</div>
```

### **17. paragraph 역할**    
paragraph 역할은 텍스트를 그룹화하여 하나의 논리적인 단락을 나타내는 역할을 합니다. HTML에서 &lt;p&gt; 요소가 기본적으로 paragraph 역할을 수행합니다. 이 역할은 보조 기술이 텍스트의 구조와 의미를 올바르게 이해하고, 사용자에게 전달할 수 있도록 돕습니다.   
[W3C ARIA paragraph](https://www.w3.org/TR/wai-aria-1.2/#paragraph){: target="_blank"}   
[MDN Web Docs: HTML: p element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p){: target="_blank"}   
[UXKM : p element](https://uxkm.io/publishing/html/04-grouping/02-p_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- paragraph 역할은 텍스트를 하나의 논리적 단위로 묶는 역할을 하며, 주로 텍스트 콘텐츠의 구조와 흐름을 나타내는 데 사용됩니다.    
- HTML의 &lt;p&gt; 요소는 기본적으로 paragraph 역할을 수행하여, 문서 내에서 텍스트 단락을 정의합니다.    
- paragraph 역할은 보조 기술이 문서의 텍스트를 올바르게 인식하고, 텍스트 간의 관계를 이해할 수 있도록 돕습니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;p&gt;)를 사용하여 텍스트 단락을 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="paragraph"를 명시적으로 지정해야 합니다. paragraph 역할은 논리적인 텍스트 단락을 나타낼 때만 사용해야 합니다.    
- **중요한 점**: paragraph 역할을 통해 웹 페이지의 텍스트 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 텍스트를 쉽게 탐색하고, 내용을 명확히 이해할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;p&gt;)를 사용하여 텍스트 단락을 정의하는 것이 좋습니다. 이는 자동으로 paragraph 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **적절한 텍스트 그룹화**: 텍스트를 논리적인 단락으로 묶어야 할 때, paragraph 역할을 사용하거나, &lt;p&gt; 요소를 사용하여 텍스트의 흐름과 의미를 명확히 표현해야 합니다.
- **불필요한 사용 피하기**: paragraph 역할은 단순 텍스트 블록이 아닌, 논리적으로 구분된 단락을 나타낼 때 사용해야 합니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. paragraph 역할은 텍스트 단락을 정의하는 역할을 하므로, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - paragraph 역할을 불필요하게 사용**
이 예시는 &lt;span&gt; 요소에 role="paragraph"를 지정했으나, &lt;span&gt;은 인라인 요소로 단락을 나타내는 데 적합하지 않습니다. 또한, 시멘틱한 마크업인 &lt;p&gt; 요소를 사용하는 것이 더 적절합니다.    
```sh
<span role="paragraph">This text is incorrectly marked as a paragraph.</span>
```

**(권장) 올바른 예시 - 시멘틱 마크업에서의 기본 사용 예시**
이 예시는 HTML의 &lt;p&gt; 요소를 사용하여 텍스트 단락을 정의하고 있습니다. &lt;p&gt; 요소는 자동으로 paragraph 역할을 수행하여, 보조 기술이 이 텍스트를 올바르게 인식하고 사용자에게 전달할 수 있도록 합니다.    
```sh
<p>This is a paragraph of text that provides information on a particular topic.</p>
```

**명시적으로 paragraph 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="paragraph"를 지정하여 비표준 마크업에서 텍스트 단락을 정의한 예시입니다. 이는 &lt;p&gt; 요소를 사용할 수 없는 상황에서 유용할 수 있지만, 일반적으로는 &lt;p&gt; 요소를 사용하는 것이 더 적절합니다.    
```sh
<div role="paragraph">
  This is a paragraph of text that is wrapped in a div element.
</div>
```

### **18. presentation 역할**    
presentation 역할은 HTML 요소의 시멘틱 의미를 제거하여, 보조 기술이 해당 요소를 단순히 레이아웃 목적으로만 인식하도록 하는 역할을 합니다. 이 역할은 시각적으로는 중요한 요소이지만, 접근성 측면에서는 의미를 전달할 필요가 없는 경우에 사용됩니다. 주로 시멘틱 마크업을 무효화하고, 콘텐츠를 단순히 시각적으로만 표시할 때 사용됩니다.   
[W3C ARIA presentation](https://www.w3.org/TR/wai-aria-1.2/#presentation){: target="_blank"}   
[MDN ARIA presentation](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role){: target="_blank"}   

**기본 설명**  
- presentation 역할은 HTML 요소의 시멘틱 의미를 제거하여 보조 기술이 해당 요소를 무시하도록 합니다. 예를 들어, &lt;table&gt; 요소에 role="presentation"을 지정하면, 보조 기술은 이 표를 데이터 구조가 아닌 단순한 레이아웃 도구로 인식합니다.    
- 이 역할은 주로 레이아웃을 위해 사용된 시멘틱 요소가 접근성 측면에서 불필요한 정보를 전달할 때 사용됩니다. 예를 들어, 레이아웃을 위한 표나 목록이 실제로 의미 있는 데이터나 항목을 전달하지 않을 때 사용됩니다.    
- presentation 역할을 사용하면, 해당 요소가 문서의 시멘틱 구조에 기여하지 않으며, 보조 기술이 이를 무시할 수 있습니다.    
- **적절한 사용**: 레이아웃 목적으로만 사용된 시멘틱한 HTML 요소에 role="presentation"을 사용하여, 불필요한 정보를 제거할 수 있습니다. 그러나 실제 의미 있는 콘텐츠에는 이 역할을 사용하지 않아야 합니다.    
- **중요한 점**: presentation 역할을 통해 접근성을 유지하면서 불필요한 시멘틱 정보를 제거함으로써, 사용자 경험을 향상시킬 수 있습니다. 이를 통해 사용자는 콘텐츠를 효과적으로 탐색하고, 불필요한 정보를 피할 수 있습니다.    

**사용 시 주의사항**   
- **의미 없는 시멘틱 제거**: presentation 역할은 시멘틱한 HTML 요소가 단순히 레이아웃 목적으로만 사용될 때 사용됩니다. 이 역할을 적용하면 보조 기술이 해당 요소를 무시하게 되므로, 실제 의미 있는 콘텐츠에는 사용하지 않아야 합니다.   
- **적절한 사용 사례**: 레이아웃 목적으로 사용된 표나 목록, 아이콘 폰트 등에 presentation 역할을 사용하여, 접근성 측면에서 불필요한 정보를 제거할 수 있습니다.
- **과도한 사용 피하기**: 문서의 구조를 명확히 하기 위해 시멘틱 요소를 사용하는 것이 중요합니다. presentation 역할을 과도하게 사용하여 문서의 시멘틱 구조를 무너뜨리지 않도록 주의해야 합니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. presentation 역할은 시멘틱 의미를 제거하는 역할이므로, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       

**role="presentation 과 aria-hidden="true의 비교**
- **role="presentation"**은 요소가 시각적으로 레이아웃을 유지하는데 필요하지만 접근성 도구에는 구조적 의미를 주고 싶지 않을 때 사용합니다.   
- **aria-hidden="true"**는 그 요소와 하위 요소들을 스크린 리더에서 완전히 숨기고자 할 때 사용합니다.   

**잘못된 예시 - 중요한 콘텐츠에 role="presentation"을 사용하여 스크린 리더에서 이 콘텐츠를 무시하게 만든 경우.**
이 예시에서, role="presentation"을 div 요소에 적용했기 때문에 그 안에 포함된 모든 내용(h1과 p)이 스크린 리더에 의해 무시됩니다. 하지만 이 콘텐츠는 매우 중요한 정보이므로, 사용자가 이를 인식하지 못하게 됩니다.    
```sh
<div role="presentation">
   <h1>Welcome to Our Site</h1>
   <p>This website provides important information about accessibility.</p>
</div>
```

**(권장) 올바른 예시 - 시각적인 레이아웃을 위해 사용된 비중요 요소에 role="presentation"을 사용하여 스크린 리더가 무시하도록 설정**
이 예시는 visual-separator 요소는 단순히 레이아웃 구분을 위한 것이므로, 스크린 리더가 이를 무시하도록 role="presentation"을 사용했습니다. 이로써 스크린 리더 사용자는 구분선을 읽지 않고 중요한 콘텐츠에 집중할 수 있습니다.    
```sh
<div class="layout-container">
   <div class="sidebar">
      <p>Sidebar content here</p>
   </div>
   
   <!-- 이 요소는 단순히 시각적 구분을 위한 것이므로 role="presentation"을 사용 -->
   <div class="visual-separator" role="presentation"></div>
   
   <div class="content">
      <h1>Main Content Area</h1>
      <p>This is where the main content of the page resides.</p>
   </div>
</div>
```

**표 안의 role="presentation" 상황 - 레이아웃용 표에서 의미 없는 행과 셀에 role="presentation"을 사용 예시**
이 예시는 빈 행은 시각적으로만 필요하고, 접근성 도구에서는 중요하지 않으므로 role="presentation"을 사용했습니다. 스크린 리더는 이 행을 무시하고 다른 중요한 정보로 넘어갑니다.    
```sh
<table>
   <tr>
      <td>Name:</td>
      <td>John Doe</td>
   </tr>
   <tr>
      <!-- 시각적 구분을 위한 빈 행 -->
      <td colspan="2" role="presentation"></td>
   </tr>
   <tr>
      <td>Email:</td>
      <td>johndoe@example.com</td>
   </tr>
</table>
```

**아이콘에 role="presentation" 적용 예시**
이 예시는 아이콘이 단순히 장식적인 요소라면 alt 속성을 비워두고 role="presentation"을 사용하여 스크린 리더가 이 이미지를 무시하도록 설정했습니다. 이렇게 하면 사용자가 불필요한 정보를 듣지 않게 됩니다.    
```sh
<button>
   <img src="icon.png" alt="" role="presentation">
   Submit
</button>
```

**role="presentation 과 aria-hidden="true의 비교 예시**
이 두 속성은 서로 다른 용도로 사용되므로, 어떤 상황에서 어느 속성을 사용하는 것이 적절한지 판단하는 것이 중요합니다. role="presentation"은 주로 구조적 의미가 없을 때 사용되고, aria-hidden="true"는 특정 콘텐츠를 스크린 리더에서 숨기고자 할 때 사용됩니다.   
```sh
// table 요소는 스크린 리더에게 테이블로 인식되지 않고, 단순히 텍스트와 이미지가 나열된 것처럼 인식됩니다.
<table role="presentation">
   <tr>
      <td><img src="icon.png" alt=""></td>
      <td>Item description here</td>
   </tr>
</table>

// div 요소와 그 안에 있는 모든 콘텐츠(이미지와 텍스트 포함)는 스크린 리더에 의해 완전히 무시됩니다.
<div aria-hidden="true">
    <img src="decorative-image.png" alt="Decorative">
    <p>This text is hidden from screen readers.</p>
</div>
```

### **19. row 역할**    
row 역할은 테이블, 그리드, 트리그리드 등에서 데이터를 행(row) 단위로 그룹화하여 나타내는 역할을 합니다. 이 역할은 보조 기술이 행 단위로 데이터를 올바르게 인식하고, 각 셀이나 항목 간의 관계를 사용자에게 전달할 수 있도록 돕습니다.   
[W3C ARIA row](https://www.w3.org/TR/wai-aria-1.2/#row){: target="_blank"}   
[MDN ARIA row](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/row_role){: target="_blank"}   
[UXKM : tr element](https://uxkm.io/publishing/html/08-table/08-tr_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- row 역할은 테이블이나 그리드와 같은 데이터 구조에서 행을 나타냅니다. 이 역할을 통해 보조 기술은 해당 데이터를 행 단위로 처리할 수 있으며, 사용자는 데이터의 구조를 더 쉽게 이해할 수 있습니다.    
- HTML의 &lt;tr&gt; 요소는 기본적으로 row 역할을 수행합니다. 이 역할은 테이블의 행을 나타내며, 각 행에 포함된 데이터를 그룹화합니다.    
- row 역할은 그리드, 트리그리드 등 다양한 데이터 구조에서 사용되며, 이러한 구조 내에서 데이터를 논리적으로 그룹화하는 데 중요한 역할을 합니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;tr&gt;)를 사용하여 테이블 행을 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="row"를 명시적으로 지정해야 합니다. row 역할은 반드시 데이터 구조 내에서 사용되어야 합니다.    
- **중요한 점**: row 역할을 통해 데이터 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 데이터를 쉽게 탐색하고, 구조를 명확히 이해할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;tr&gt;)를 사용하여 테이블 행을 정의하는 것이 좋습니다. 이는 자동으로 row 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **그리드 및 트리그리드에서의 사용**: 그리드나 트리그리드 구조에서는 row 역할을 사용하여 행을 명확하게 정의하고, 각 셀 간의 관계를 명확히 해야 합니다.
- **적절한 구조 유지**: row 역할을 사용할 때는 반드시 그리드, 테이블, 트리그리드 등의 시멘틱 구조 내에서 사용해야 하며, 이 구조를 무너뜨리지 않도록 주의해야 합니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: 행의 제목을 지정하여, 보조 기술이 이 제목을 행과 연관지어 사용자에게 전달할 수 있게 합니다.       
- **aria-level**: 트리그리드 구조에서 행의 깊이를 나타냅니다. 이 속성은 행이 트리 구조 내에서 어느 수준에 위치하는지 정의하는 데 사용됩니다。       


**잘못된 예시 - row 역할을 사용하지 않아야 하는 경우**
이 예시는 데이터 구조와 무관한 단락에 row 역할을 사용했습니다. row 역할은 반드시 데이터 테이블, 그리드, 트리그리드 등의 구조 내에서 사용해야 하며, 단순한 텍스트 블록에는 사용하지 않아야 합니다.   
```sh
<div role="row">
  <p>This is not a data row</p>
</div>
```

**올바른 예시 - 그리드 구조 내에서 row 역할 사용**
이 예시는 그리드 구조 내에서 role="row"와 role="gridcell"을 사용하여, 보조 기술이 데이터를 올바르게 인식하고 사용자에게 전달할 수 있도록 했습니다.    
```sh
<div role="grid">
  <div role="row">
    <div role="gridcell">Apple</div>
    <div role="gridcell">$1.00</div>
    <div role="gridcell">50</div>
  </div>
  <div role="row">
    <div role="gridcell">Banana</div>
    <div role="gridcell">$0.50</div>
    <div role="gridcell">100</div>
  </div>
</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용 예시**
이 예시는 HTML의 &lt;tr&gt; 요소를 사용하여 테이블 행을 정의하고 있습니다. &lt;tr&gt; 요소는 자동으로 row 역할을 수행하여, 보조 기술이 이 구조를 올바르게 인식할 수 있도록 합니다.    
```sh
<table>
  <tr>
    <td>Apple</td>
    <td>$1.00</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Banana</td>
    <td>$0.50</td>
    <td>100</td>
  </tr>
</table>
```

**명시적으로 row 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="row"를 지정하여 비표준 마크업에서 그리드 행을 정의한 예시입니다. 각 셀은 role="gridcell"로 정의되어 있습니다.    
```sh
<div role="row">
  <div role="gridcell">Apple</div>
  <div role="gridcell">$1.00</div>
  <div role="gridcell">50</div>
</div>
```

### **20. rowgroup 역할**    
rowgroup 역할은 테이블, 그리드, 트리그리드 등의 데이터 구조에서 여러 행(row)을 묶어 하나의 그룹으로 나타내는 역할을 합니다. 이 역할은 행 그룹을 정의하여 보조 기술이 이 그룹을 올바르게 인식하고, 사용자에게 데이터를 더 구조적으로 전달할 수 있도록 돕습니다. HTML에서 &lt;thead&gt;, &lt;tbody&gt;, &lt;tfoot&gt; 요소가 기본적으로 rowgroup 역할을 수행합니다.   
[W3C ARIA rowgroup](https://www.w3.org/TR/wai-aria-1.2/#rowgroup){: target="_blank"}   
[MDN ARIA rowgroup](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/rowgroup_role){: target="_blank"}   
[UXKM : thead element](https://uxkm.io/publishing/html/08-table/05-thead_element#gsc.tab=0){: target="_blank"}   
[UXKM : tbody element](https://uxkm.io/publishing/html/08-table/06-tbody_element#gsc.tab=0){: target="_blank"}   
[UXKM : tfoot element](https://uxkm.io/publishing/html/08-table/07-tfoot_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- rowgroup 역할은 여러 개의 행을 논리적으로 묶어 하나의 그룹으로 표현하며, 보조 기술이 이 그룹을 문서의 다른 행과 구분하여 인식할 수 있도록 합니다.    
- 이 역할은 주로 테이블의 머리글, 본문, 꼬리글 등을 그룹화하는 데 사용됩니다. HTML에서 &lt;thead&gt;, &lt;tbody&gt;, &lt;tfoot&gt; 요소는 각각 행 그룹을 나타내며, 자동으로 rowgroup 역할을 수행합니다.    
- rowgroup 역할은 테이블이나 그리드와 같은 구조에서 데이터를 구조화하고, 사용자에게 데이터의 논리적인 구성을 명확히 전달하는 데 도움이 됩니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;thead&gt;, &lt;tbody&gt;, &lt;tfoot&gt;)를 사용하여 행 그룹을 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="rowgroup"을 명시적으로 지정해야 합니다. rowgroup 역할은 반드시 데이터 구조 내에서 사용되어야 합니다.    
- **중요한 점**: rowgroup 역할을 통해 데이터 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 데이터를 구조적으로 이해하고, 필요한 내용을 효율적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;thead&gt;, &lt;tbody&gt;, &lt;tfoot&gt;)를 사용하여 행 그룹을 정의하는 것이 좋습니다. 이는 자동으로 rowgroup 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **그리드 및 트리그리드에서의 사용**: 그리드나 트리그리드 구조에서는 rowgroup 역할을 사용하여 여러 행을 그룹화하고, 그룹 내에서 행 간의 관계를 명확히 해야 합니다.
- **적절한 구조 유지**: rowgroup 역할을 사용할 때는 데이터 구조 내에서 사용해야 하며, 구조를 무너뜨리지 않도록 주의해야 합니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: 행 그룹의 제목을 지정하여, 보조 기술이 이 제목을 그룹과 연관지어 사용자에게 전달할 수 있게 합니다.       


**잘못된 예시 - 의미 없는 그룹화**
이 예시는 데이터 구조와 무관한 텍스트를 role="rowgroup"으로 지정했으나, rowgroup 역할은 반드시 데이터 구조 내에서 사용되어야 합니다. 의미 없는 콘텐츠에 이 역할을 사용하면 보조 기술이 혼란스러울 수 있습니다.   
```sh
<div role="rowgroup">
  <p>This text does not belong to a row group</p>
</div>
```

**올바른 예시 - 그리드 구조 내에서 rowgroup 역할 사용 사용**
이 예시는 그리드 구조 내에서 role="rowgroup"과 role="row"를 사용하여, 보조 기술이 데이터를 그룹 단위로 인식하고, 사용자에게 구조화된 정보를 제공할 수 있도록 했습니다.    
```sh
<div role="table">
  <div role="rowgroup" aria-labelledby="header-row">
    <div role="row" id="header-row">
      <div role="columnheader">Product</div>
      <div role="columnheader">Price</div>
      <div role="columnheader">Quantity</div>
    </div>
  </div>
  <div role="rowgroup">
    <div role="row">
      <div role="gridcell">Apple</div>
      <div role="gridcell">$1.00</div>
      <div role="gridcell">50</div>
    </div>
    <div role="row">
      <div role="gridcell">Banana</div>
      <div role="gridcell">$0.50</div>
      <div role="gridcell">100</div>
    </div>
  </div>
</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용 예시**
이 예시는 HTML의 &lt;thead&gt;, &lt;tbody&gt;, &lt;tfoot&gt; 요소를 사용하여 테이블의 행을 그룹화하고 있습니다. 각 요소는 자동으로 rowgroup 역할을 수행하며, 보조 기술이 이 구조를 올바르게 인식할 수 있도록 합니다.    
```sh
<table>
  <thead>
    <tr>
      <th>Product</th>
      <th>Price</th>
      <th>Quantity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apple</td>
      <td>$1.00</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Banana</td>
      <td>$0.50</td>
      <td>100</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">Total</td>
    </tr>
  </tfoot>
</table>
```

**명시적으로 rowgroup 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="rowgroup"을 지정하여 비표준 마크업에서 행 그룹을 정의한 예시입니다. 각 그룹은 role="row"를 사용하여 행을 포함하며, 보조 기술이 그룹 간의 관계를 인식할 수 있도록 돕습니다.    
```sh
<div role="table">
  <div role="rowgroup">
    <div role="row">
      <div role="columnheader">Product</div>
      <div role="columnheader">Price</div>
      <div role="columnheader">Quantity</div>
    </div>
  </div>
  <div role="rowgroup">
    <div role="row">
      <div role="gridcell">Apple</div>
      <div role="gridcell">$1.00</div>
      <div role="gridcell">50</div>
    </div>
    <div role="row">
      <div role="gridcell">Banana</div>
      <div role="gridcell">$0.50</div>
      <div role="gridcell">100</div>
    </div>
  </div>
</div>
```

### **21. rowheader 역할**    
rowheader 역할은 테이블, 그리드, 또는 트리그리드에서 행의 제목을 나타내는 셀에 사용됩니다. 이 역할은 각 행의 주제를 설명하며, 보조 기술이 이를 올바르게 인식하고 사용자에게 전달할 수 있도록 돕습니다. 일반적으로 테이블의 첫 번째 열에 위치하며, 해당 행의 모든 데이터를 설명하는 역할을 합니다.   
[W3C ARIA rowheader](https://www.w3.org/TR/wai-aria-1.2/#rowheader){: target="_blank"}   
[MDN ARIA rowheader](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/rowheader_role){: target="_blank"}   
[UXKM : th element](https://uxkm.io/publishing/html/08-table/09-th_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- rowheader 역할은 테이블이나 그리드에서 행의 주제를 나타내는 셀에 사용됩니다. 이 셀은 행 내의 다른 데이터 셀들과 관련된 정보를 제공합니다.    
- HTML의 &lt;th scope="row"&gt; 요소는 자동으로 rowheader 역할을 수행합니다. 이 역할을 통해 보조 기술은 해당 셀을 행의 제목으로 인식하고, 사용자가 데이터의 맥락을 이해할 수 있도록 합니다.    
- rowheader 역할은 사용자가 테이블을 탐색할 때 행의 주제를 명확히 파악할 수 있도록 하여, 접근성과 사용자 경험을 향상시킵니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;th scope="row"&gt;)를 사용하여 행 머리글을 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="rowheader"를 명시적으로 지정해야 합니다. rowheader 역할은 반드시 데이터 구조 내에서 사용되어야 합니다.    
- **중요한 점**: rowheader 역할을 통해 데이터 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 데이터를 더 쉽게 탐색하고, 각 행의 내용을 명확히 이해할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;th scope="row"&gt;)를 사용하여 행 머리글을 정의하는 것이 좋습니다. 이는 자동으로 rowheader 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **그리드 및 트리그리드에서의 사용**: 그리드나 트리그리드 구조에서는 rowheader 역할을 사용하여 각 행의 주제를 명확하게 정의하고, 셀 간의 관계를 명확히 해야 합니다.
- **적절한 구조 유지**: rowheader 역할을 사용할 때는 반드시 데이터 구조 내에서 사용해야 하며, 구조를 무너뜨리지 않도록 주의해야 합니다.

**상속된 상태 및 속성**   
- **aria-sort**: 이 속성은 해당 행이 정렬된 상태인 경우 정렬 방향을 나타냅니다. ascending, descending, none 또는 other 값을 가질 수 있습니다.       
- **aria-labelledby**: 이 속성은 셀의 제목을 지정하여, 보조 기술이 이 제목을 셀과 연관지어 사용자에게 전달할 수 있게 합니다.       


**잘못된 예시 - 의미 없는 셀에 rowheader 역할 사용**
이 예시는 단순 텍스트 블록에 rowheader 역할을 사용했으나, rowheader 역할은 반드시 테이블, 그리드, 또는 트리그리드와 같은 데이터 구조 내에서 사용되어야 합니다. 의미 없는 콘텐츠에 이 역할을 사용하면 보조 기술이 혼란스러울 수 있습니다.   
```sh
<div role="rowheader">This is not a row header</div>
```

**올바른 예시 - 그리드 구조 내에서 rowheader 역할 사용**
이 예시는 그리드 구조 내에서 role="rowheader"과 role="gridcell"을 사용하여, 보조 기술이 데이터를 올바르게 인식하고, 사용자에게 행의 주제를 명확히 전달할 수 있도록 했습니다.    
```sh
<div role="grid">
  <div role="row">
    <div role="rowheader">Apple</div>
    <div role="gridcell">$1.00</div>
    <div role="gridcell">50</div>
  </div>
  <div role="row">
    <div role="rowheader">Banana</div>
    <div role="gridcell">$0.50</div>
    <div role="gridcell">100</div>
  </div>
</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용 예시**
이 예시는 HTML의 &lt;th scope="row"&gt; 요소를 사용하여 테이블 행의 머리글을 정의하고 있습니다. &lt;h&gt; 요소는 자동으로 rowheader 역할을 수행하며, 보조 기술이 이 구조를 올바르게 인식할 수 있도록 합니다.    
```sh
<table>
  <tr>
    <th scope="row">Apple</th>
    <td>$1.00</td>
    <td>50</td>
  </tr>
  <tr>
    <th scope="row">Banana</th>
    <td>$0.50</td>
    <td>100</td>
  </tr>
</table>
```

**명시적으로 rowheader 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="rowheader"를 지정하여 비표준 마크업에서 행 머리글을 정의한 예시입니다. 각 행의 데이터는 role="gridcell"을 사용하여 정의됩니다.    
```sh
<div role="row">
  <div role="rowheader">Apple</div>
  <div role="gridcell">$1.00</div>
  <div role="gridcell">50</div>
</div>
<div role="row">
  <div role="rowheader">Banana</div>
  <div role="gridcell">$0.50</div>
  <div role="gridcell">100</div>
</div>
```

### **22. table 역할**    
table 역할은 데이터를 행과 열로 구성된 표 형식으로 나타내는 구조를 정의하는 데 사용됩니다. 이 역할은 보조 기술이 데이터를 테이블 형식으로 인식하고, 각 셀 간의 관계를 사용자에게 명확히 전달할 수 있도록 돕습니다. HTML의 &lt;table&gt; 요소는 기본적으로 table 역할을 수행합니다.   
[W3C ARIA table](https://www.w3.org/TR/wai-aria-1.2/#table){: target="_blank"}   
[MDN ARIA table](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/table_role){: target="_blank"}   
[UXKM : table element](https://uxkm.io/publishing/html/08-table/01-table_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- table 역할은 데이터를 표 형식으로 나타내는 구조를 정의합니다. 이 역할을 통해 보조 기술은 데이터를 행과 열로 구성된 테이블로 인식하고, 사용자가 각 셀 간의 관계를 쉽게 이해할 수 있도록 합니다.    
- HTML의 &lt;table&gt; 요소는 자동으로 table 역할을 수행하며, 이 요소 내에서 &lt;tr&gt;, &lt;th&gt;, &lt;td&gt; 등의 요소가 사용됩니다.    
- table 역할은 주로 데이터를 시각적으로 정렬하고, 다양한 행과 열을 통해 데이터를 구조적으로 나타낼 때 사용됩니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;table&gt;, &lt;tr&gt;, &lt;th&gt;, &lt;td&gt;)를 사용하여 테이블 구조를 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="table"을 명시적으로 지정해야 합니다. 레이아웃 목적으로 사용되는 테이블에는 role="presentation"을 사용하는 것이 좋습니다.    
- **중요한 점**: table 역할을 통해 데이터 구조를 명확하게 정의함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 데이터를 더 쉽게 탐색하고, 각 셀 간의 관계를 명확히 이해할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;table&gt;, &lt;tr&gt;, &lt;th&gt;, &lt;td&gt;)를 사용하여 데이터를 정의하는 것이 좋습니다. 이는 자동으로 table 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **데이터 테이블과 레이아웃 테이블 구분**: 데이터 구조를 나타내는 테이블과 레이아웃 목적으로 사용되는 테이블을 구분해야 합니다. 데이터 테이블에는 table 역할이 필요하지만, 레이아웃을 위한 테이블에는 role="presentation"을 사용하여 보조 기술이 이를 무시하도록 하는 것이 좋습니다.
- **적절한 테이블 구조 유지**: table 역할을 사용할 때는 각 셀(td, th)이 적절한 행(tr)과 열로 구성되도록 구조를 유지해야 합니다. 이렇게 하면 보조 기술이 데이터를 정확하게 전달할 수 있습니다.

**상속된 상태 및 속성**   
- **aria-label**: 테이블의 이름이나 설명을 지정하여 보조 기술이 이를 사용자에게 전달할 수 있도록 합니다.       
- **aria-labelledby**: 테이블의 제목을 지정하여 보조 기술이 이 제목을 테이블과 연관지어 사용자에게 전달할 수 있게 합니다.       
- **aria-describedby**: 테이블에 대한 추가 설명을 제공하여, 보조 기술이 이 설명을 테이블과 연관지어 사용자에게 전달할 수 있게 합니다.       


**잘못된 예시 - 레이아웃 테이블에 table 역할 사용**
이 예시는 레이아웃을 위한 테이블에 table 역할을 사용하고 있으며, 이는 잘못된 사용입니다. 레이아웃 목적으로 사용되는 테이블에는 role="presentation"을 사용하여 보조 기술이 이를 무시하도록 하는 것이 좋습니다.   
```sh
<table role="table">
  <tr>
    <td><img src="image1.jpg" alt="Image 1"></td>
    <td><img src="image2.jpg" alt="Image 2"></td>
    <td><img src="image3.jpg" alt="Image 3"></td>
  </tr>
</table>
```

**(권장) 시멘틱 마크업 - 데이터 테이블에 table 역할 사용**
이 예시는 HTML의 &lt;table&gt; 요소를 사용하여 테이블 구조를 정의하고 있으며, &lt;caption&gt; 요소로 테이블의 제목을 제공하고 있습니다. table 역할은 자동으로 적용되며, 보조 기술이 이 테이블을 데이터 구조로 인식하고 사용자에게 전달할 수 있도록 합니다.    
```sh
<table>
  <caption>Product Pricing</caption>
  <thead>
    <tr>
      <th>Product</th>
      <th>Price</th>
      <th>Quantity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apple</td>
      <td>$1.00</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Banana</td>
      <td>$0.50</td>
      <td>100</td>
    </tr>
  </tbody>
</table>
```

**명시적으로 table 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="table"을 지정하여 비표준 마크업에서 테이블 구조를 정의한 예시입니다. 각 행과 셀은 role="row" 및 role="gridcell"로 정의되어 있습니다.    
```sh
<div role="table">
  <div role="rowgroup">
    <div role="row">
      <div role="columnheader">Product</div>
      <div role="columnheader">Price</div>
      <div role="columnheader">Quantity</div>
    </div>
  </div>
  <div role="rowgroup">
    <div role="row">
      <div role="gridcell">Apple</div>
      <div role="gridcell">$1.00</div>
      <div role="gridcell">50</div>
    </div>
    <div role="row">
      <div role="gridcell">Banana</div>
      <div role="gridcell">$0.50</div>
      <div role="gridcell">100</div>
    </div>
  </div>
</div>
```

### **23. separator(구분선) 역할 (포커스 불가능한 경우)**    
separator 역할은 콘텐츠를 논리적으로 구분하는 시각적인 구분선을 나타내는 데 사용됩니다. 이 역할은 주로 메뉴, 툴바, 대화 상자, 또는 기타 인터페이스 구성 요소 내에서 그룹을 나누거나 구획을 구분할 때 사용됩니다. 포커스 불가능한 separator는 보조 기술이 해당 요소를 콘텐츠 간의 구분자로 인식하지만, 이 요소에 포커스를 둘 수 없도록 설정된 경우입니다.   
[W3C ARIA separator](https://www.w3.org/TR/wai-aria-1.2/#separator){: target="_blank"}   
[MDN ARIA separator](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/separator_role){: target="_blank"}   

**기본 설명**  
- separator 역할은 시각적으로 구분선을 나타내며, 보조 기술이 이를 콘텐츠의 구분자로 인식할 수 있도록 돕습니다.    
- 이 역할은 주로 메뉴나 툴바에서 항목을 구분하는 수평선이나 수직선, 또는 다른 콘텐츠를 구분하는 데 사용됩니다.    
- **포커스 불가능한** separator는 사용자가 키보드 네비게이션을 통해 이 요소에 포커스를 둘 수 없으며, 시각적 또는 논리적인 구분만 제공합니다.    
- HTML에서 &lt;hr&gt; 요소는 기본적으로 시각적 구분선을 나타내며, separator 역할을 암시적으로 수행합니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;hr&gt;)를 사용하여 구분선을 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="separator"를 명시적으로 지정해야 합니다. 구분선이 단순히 시각적인 구분만 제공할 경우, 포커스 불가능하게 설정하는 것이 좋습니다.    
- **중요한 점**: separator 역할을 통해 사용자 인터페이스를 구조화하고, 접근성을 유지하면서 불필요한 포커스를 제거하여 사용자 경험을 향상시킬 수 있습니다. 이를 통해 사용자는 시각적인 구분을 쉽게 이해하고, 필요한 내용을 효율적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **포커스 가능 여부 결정**: 구분선이 사용자 인터페이스에서 중요한 역할을 하지 않으며, 단지 시각적 구분만 제공한다면 포커스 불가능한 상태로 유지해야 합니다. 그렇지 않으면 포커스 가능하게 설정하여 사용자에게 중요한 정보로 전달해야 합니다.   
- **시멘틱 마크업 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;hr&gt;)를 사용하여 구분선을 정의하는 것이 좋습니다. 이 요소는 자동으로 separator 역할을 수행하며, 포커스 불가능한 상태로 작동합니다.
- **구분선 방향 지정**: aria-orientation 속성을 사용하여 구분선의 방향을 명확히 지정해야 합니다. 수평 구분선이 기본값이므로, 수직 구분선이 필요할 경우 명시적으로 지정해야 합니다.

**상속된 상태 및 속성**   
- **aria-orientation**: 이 속성은 구분선의 방향을 지정합니다. horizontal(수평) 또는 vertical(수직) 값으로 설정할 수 있습니다. 기본값은 horizontal입니다.       
- **aria-labelledby**: 구분선이 설명 또는 제목과 연관될 경우, 보조 기술이 이를 설명할 수 있도록 이 속성을 사용할 수 있습니다.       


**잘못된 예시 - 불필요한 포커스 가능 설정 사용**
이 예시는 구분선에 tabindex="0"을 지정하여 포커스 가능하게 만들었지만, 구분선이 단순히 시각적인 구분만 제공하는 경우 포커스가 필요하지 않습니다. 이러한 설정은 사용자에게 혼란을 줄 수 있습니다.   
```sh
<div role="separator" tabindex="0"></div>
```

**올바른 예시 - 포커스 불가능한 상태 유지 사용**
이 예시는 마크업에서 role="separator"와 aria-orientation="vertical"을 사용하여, 포커스 불가능한 수직 구분선을 정의하고 있습니다. 포커스가 불가능하므로, 이 요소는 시각적 구분만 제공하며 사용자 인터페이스에서 중요한 역할을 하지 않습니다.    
```sh
<div role="separator" aria-orientation="vertical"></div>
```

**(권장) 시멘틱 마크업에서의 기본 사용**
이 예시는 HTML의 &lt;hr&gt; 요소를 사용하여 콘텐츠를 구분하는 구분선을 나타냅니다. &lt;hr&gt; 요소는 기본적으로 포커스 불가능하며, separator 역할을 자동으로 수행합니다.    
```sh
<hr>
```

**명시적으로 separator 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="separator"를 지정하여, 포커스 불가능한 수평 구분선을 비표준 마크업으로 정의한 예시입니다. aria-orientation="horizontal" 속성은 구분선의 방향을 명확히 지정합니다.    
```sh
<div role="separator" aria-orientation="horizontal"></div>
```

### **24. term 역할**    
term 역할은 정의 목록에서 정의될 용어 또는 단어를 나타내는 데 사용됩니다. 이 역할은 용어가 정의된 내용과 함께 그룹화되어 보조 기술이 이를 올바르게 해석하고 사용자에게 전달할 수 있도록 돕습니다. HTML에서 &lt;dt&gt; 요소가 기본적으로 term 역할을 수행합니다.   
[W3C ARIA term](https://www.w3.org/TR/wai-aria-1.2/#term){: target="_blank"}   
[MDN ARIA term](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/term_role){: target="_blank"}   
[UXKM : dl element](https://uxkm.io/publishing/html/04-grouping/06-dl_element#gsc.tab=0){: target="_blank"}   
[UXKM : dt element](https://uxkm.io/publishing/html/04-grouping/07-dt_element#gsc.tab=0){: target="_blank"}   
[UXKM : dd element](https://uxkm.io/publishing/html/04-grouping/08-dd_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- term 역할은 정의 목록(&lt;dl&gt;) 내에서 특정 용어를 나타냅니다. 이 용어는 뒤따르는 정의(definition 역할)를 설명하는 데 사용됩니다.    
- HTML의 &lt;dt&gt; 요소는 자동으로 term 역할을 수행합니다. &lt;dt&gt; 요소와 &lt;dd&gt; 요소가 함께 사용되어, 용어와 그 정의를 시멘틱하게 구조화합니다.    
- term 역할은 보조 기술이 용어를 정의된 내용과 연관지어 올바르게 사용자에게 전달할 수 있도록 돕습니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;dt&gt;, &lt;dl&gt;, &lt;dd&gt;)를 사용하여 용어와 그 정의를 정의하는 것이 가장 바람직하며, 비표준 마크업에서는 role="term"을 명시적으로 지정해야 합니다. term 역할은 항상 정의(definition 역할)와 함께 사용되어야 합니다.    
- **중요한 점**: term 역할을 통해 정의 목록을 명확하게 구조화함으로써, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 용어의 의미를 쉽게 이해하고, 정의된 내용을 효과적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;dt&gt;, &lt;dl&gt;, &lt;dd&gt;)를 사용하여 용어와 그 정의를 정의하는 것이 좋습니다. 이는 자동으로 term 역할을 수행하며, 문서의 구조를 명확히 합니다.   
- **정의와 함께 사용**: term 역할은 반드시 정의(definition 역할)와 함께 사용되어야 합니다. 정의 목록에서 용어는 해당 정의와 논리적으로 연결되어야 합니다.
- **비표준 마크업에서의 사용**: 시멘틱한 요소를 사용할 수 없는 경우, role="term"을 사용하여 용어를 명시적으로 정의할 수 있습니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. term 역할은 정의될 용어를 나타내는 역할을 하므로, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - 정의 없이 term 역할 사용**
이 예시는 용어를 정의하는 내용 없이 term 역할만 사용하고 있으며, 이는 부적절한 사용입니다. term 역할은 항상 정의(definition 역할)와 함께 사용되어야 합니다.   
```sh
<div role="term">Web API</div>
```

**올바른 예시 - 용어와 정의를 함께 사용**
이 예시는 role="term"과 role="definition"을 함께 사용하여 용어와 그 정의를 명확히 연결하고 있습니다. 보조 기술이 이 정보를 사용자에게 올바르게 전달할 수 있도록 합니다.    
```sh
<div role="term">Web API</div>
<div role="definition">An interface that allows software applications to interact with each other over the web.</div>
```

**(권장) 시멘틱 마크업에서의 기본 사용**
이 예시는 HTML의 &lt;dl&gt;, &lt;dt&gt;, &lt;dd&gt; 요소를 사용하여 정의 목록을 시멘틱하게 구조화하고 있습니다. &lt;dt&gt; 요소는 자동으로 term 역할을 수행합니다.    
```sh
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language, the standard language for documents designed to be displayed in a web browser.</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets, a language used to describe the presentation of a document written in HTML or XML.</dd>
</dl>
```

**명시적으로 term 역할 지정 예시**
이 예시는 &lt;div&gt; 요소에 role="term"과 role="definition"을 지정하여 비표준 마크업에서 정의 목록을 구성한 예시입니다. 보조 기술이 용어와 정의를 올바르게 연결할 수 있도록 돕습니다.    
```sh
<div role="term">JavaScript</div>
<div role="definition">A programming language that conforms to the ECMAScript specification and is used to create interactive effects within web browsers.</div>
```

### **25. toolbar 역할**    
toolbar 역할은 웹 애플리케이션에서 여러 상호작용 가능한 도구(버튼, 메뉴 등)가 모여 있는 도구 모음(툴바)을 나타내는 데 사용됩니다. 이 역할은 보조 기술이 도구 모음을 인식하고, 사용자에게 이 도구들이 한 그룹으로 묶여 있다는 정보를 제공할 수 있도록 돕습니다. 툴바는 일반적으로 관련된 작업을 수행하는 여러 컨트롤을 포함하고 있으며, 이는 사용자가 한 번에 접근할 수 있는 인터페이스 요소로 그룹화됩니다.   
[W3C ARIA toolbar](https://www.w3.org/TR/wai-aria-1.2/#toolbar){: target="_blank"}   
[MDN ARIA toolbar](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/toolbar_role){: target="_blank"}   

**기본 설명**  
- toolbar 역할은 여러 컨트롤(예: 버튼, 체크박스, 드롭다운 메뉴 등)이 함께 배치된 도구 모음을 나타냅니다. 이 역할을 사용하면 보조 기술이 이러한 컨트롤들을 한 그룹으로 처리하고, 사용자에게 이들이 같은 작업 범주에 속해 있음을 알릴 수 있습니다.    
- HTML에서 toolbar 역할을 특정 요소에 할당함으로써, 해당 요소와 그 자식 요소들을 보조 기술이 툴바로 인식하게 됩니다. 툴바 내의 개별 컨트롤은 자체적인 역할(예: button, menuitem, checkbox 등)을 가질 수 있습니다.    
- toolbar 역할은 툴바 안에 있는 도구들이 상호 관련이 있음을 나타내며, 사용자가 관련 작업을 수행하기 위해 쉽게 접근할 수 있는 인터페이스를 제공합니다.    
- **적절한 사용**: 툴바는 관련된 작업을 수행하기 위해 필요한 도구들을 그룹화하는 데 사용되며, 시멘틱한 HTML 요소를 사용하여 각 컨트롤을 정의해야 합니다. 툴바의 방향(aria-orientation)을 명확히 지정하는 것이 좋습니다.    
- **중요한 점**: toolbar 역할을 통해 사용자 인터페이스를 구조화하고, 사용자 경험과 접근성을 모두 향상시킬 수 있습니다. 이를 통해 사용자는 관련된 작업 도구를 한 번에 쉽게 접근하고 사용할 수 있습니다.    

**사용 시 주의사항**   
- **적절한 그룹화**: toolbar 역할은 관련된 도구나 컨트롤을 그룹화하는 데 사용됩니다. 사용자가 관련된 작업을 수행하기 위해 한 번에 접근할 수 있는 인터페이스 요소로 구성해야 합니다.   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소를 사용하여 툴바 내의 개별 컨트롤을 정의해야 합니다. 툴바의 역할은 전체 그룹에만 적용되며, 각 컨트롤에는 그에 맞는 역할(예: button, menuitem)을 적용해야 합니다.
- **툴바의 방향 지정**: 툴바의 컨트롤이 수직 또는 수평으로 배치되어 있는지 명확히 하기 위해, aria-orientation 속성을 사용해야 합니다.

**상속된 상태 및 속성**   
- **aria-orientation**: 툴바의 방향을 지정합니다. horizontal(수평) 또는 vertical(수직) 값으로 설정할 수 있으며, 기본값은 horizontal입니다.       
- **aria-labelledby**: 툴바의 제목을 지정하여, 보조 기술이 이 제목을 툴바와 연관지어 사용자에게 전달할 수 있게 합니다.       
- **aria-controls**: 툴바에서 제어하는 요소의 ID를 참조하여, 보조 기술이 툴바가 제어하는 콘텐츠와의 관계를 명확히 할 수 있도록 합니다.       


**잘못된 예시 - 툴바 내에 적절한 역할 미지정**
이 예시는 툴바 내의 컨트롤에 적절한 역할(button 등)을 지정하지 않았으며, 이는 보조 기술이 툴바의 개별 도구를 올바르게 인식하지 못하게 합니다. 각 컨트롤에는 그에 맞는 역할을 지정해야 합니다.   
```sh
<div role="toolbar">
  <div>Bold</div>
  <div>Italic</div>
  <div>Underline</div>
</div>
```

**(권장) 올바른 예시 - 툴바 내에 적절한 역할 지정**
이 예시는 툴바 내의 각 컨트롤에 button 역할을 지정하여, 보조 기술이 툴바의 개별 도구를 올바르게 인식하고 사용자에게 전달할 수 있도록 했습니다.    
```sh
<div role="toolbar" aria-label="Formatting options">
  <button>Bold</button>
  <button>Italic</button>
  <button>Underline</button>
</div>
```

**수평 툴바 사용 예시**
이 예시는 수평 툴바를 나타내며, 텍스트 서식 옵션을 제공하는 버튼들이 그룹화되어 있습니다. aria-label 속성은 툴바의 목적을 설명하며, aria-orientation="horizontal"은 툴바가 수평으로 배열되어 있음을 명시합니다.    
```sh
<div role="toolbar" aria-label="Text formatting options" aria-orientation="horizontal">
  <button>Bold</button>
  <button>Italic</button>
  <button>Underline</button>
  <div role="separator"></div>
  <button>Left Align</button>
  <button>Center Align</button>
  <button>Right Align</button>
</div>
```

**수직 툴바 사용 예시**
이 예시는 수직 툴바를 나타내며, 문서 관련 작업을 수행하는 버튼들이 수직으로 배열되어 있습니다. aria-orientation="vertical"은 툴바가 수직으로 배열되어 있음을 명시합니다.    
```sh
<div role="toolbar" aria-label="Document tools" aria-orientation="vertical">
  <button>New</button>
  <button>Open</button>
  <button>Save</button>
  <div role="separator"></div>
  <button>Print</button>
</div>
```

### **26. tooltip 역할**    
tooltip 역할은 요소와 연관된 추가 정보를 제공하는 작은 팝업 창을 나타냅니다. 툴팁은 일반적으로 마우스오버, 포커스, 또는 키보드 상호작용 시 나타나며, 해당 요소에 대한 설명이나 추가 정보를 간략하게 제공하는 데 사용됩니다. 툴팁은 시각적으로 나타나며, 보조 기술이 이를 사용자에게 올바르게 전달할 수 있도록 해야 합니다.   
[W3C ARIA tooltip](https://www.w3.org/TR/wai-aria-1.2/#tooltip){: target="_blank"}   
[MDN ARIA tooltip](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tooltip_role){: target="_blank"}   

**기본 설명**  
- tooltip 역할은 사용자가 요소와 상호작용할 때 표시되는 작은 팝업 설명을 나타냅니다. 이는 주로 버튼, 링크, 아이콘 등과 같은 인터페이스 요소에 대한 추가 설명을 제공하는 데 사용됩니다.    
- 툴팁은 사용자가 요소의 기능을 더 잘 이해할 수 있도록 도와주며, 시각적으로 요소 위에 나타나는 짧은 텍스트 설명입니다.    
- HTML에서 툴팁을 구현할 때는 일반적으로 title 속성을 사용하거나, aria-describedby 속성을 통해 툴팁과 연관된 요소를 지정합니다. tooltip 역할을 명시적으로 지정할 수도 있습니다.    
- **적절한 사용**: 툴팁은 관련된 요소와 직접적으로 연결되어야 하며, 명확하고 유용한 정보를 제공해야 합니다. aria-describedby 속성을 사용해 툴팁을 참조하거나, 동적으로 툴팁을 표시할 수 있습니다.    
- **중요한 점**: tooltip 역할을 통해 사용자 인터페이스의 접근성과 사용자 경험을 향상시킬 수 있습니다. 툴팁은 사용자가 인터페이스 요소를 더 잘 이해하고, 이를 효과적으로 사용할 수 있도록 돕습니다.    

**사용 시 주의사항**   
- **적절한 컨텍스트 제공**: 툴팁은 관련된 요소에 대한 추가 정보를 제공하는 것이므로, 툴팁이 제공하는 정보는 해당 요소와 직접적으로 관련되어 있어야 합니다.   
- **키보드 접근성**: 툴팁이 포커스를 받을 수 없는 경우, 사용자가 키보드로 상호작용할 때 툴팁이 접근 가능해야 합니다. 일반적으로 aria-describedby 속성을 사용하여 툴팁을 참조합니다.
- **자동적으로 표시되지 않도록 주의**: 툴팁은 사용자가 요소와 상호작용할 때만 나타나야 하며, 자동으로 나타나거나 사라지지 않도록 해야 합니다. 사용자가 툴팁을 읽을 충분한 시간을 가져야 합니다.

**상속된 상태 및 속성**   
- **aria-labelledby**: 툴팁에 대한 제목을 지정하여, 보조 기술이 이 제목을 툴팁과 연관지어 사용자에게 전달할 수 있게 합니다.       
- **aria-describedby**: 툴팁이 설명하는 요소를 지정하여, 보조 기술이 이를 사용자에게 연결된 설명으로 전달할 수 있습니다.       


**잘못된 예시 - 툴팁의 정보 부족**
이 예시는 툴팁에 제공되는 정보가 불충분하여, 사용자에게 도움이 되지 않습니다. 툴팁은 해당 요소에 대한 명확한 설명이나 추가 정보를 제공해야 합니다.   
```sh
<button aria-describedby="tooltip3">Submit</button>
<div role="tooltip" id="tooltip3">
  Click
</div>
```

**(권장) 올바른 예시 - 명확한 정보 제공**
이 예시는 툴팁에 명확한 정보를 제공하여, 사용자가 해당 버튼의 기능을 쉽게 이해할 수 있도록 합니다.    
```sh
<button aria-describedby="tooltip4">Submit</button>
<div role="tooltip" id="tooltip4">
  This button will submit the form data to the server.
</div>
```

**동적 툴팁 사용 예시**
이 예시는 버튼에 마우스를 올리면 툴팁이 나타나고, 마우스를 떼면 툴팁이 사라지도록 동적으로 처리한 예시입니다. aria-describedby 속성을 사용해 툴팁을 연결합니다.    
```sh
<button onmouseover="showTooltip()" onmouseout="hideTooltip()" aria-describedby="tooltip2">Info</button>
<div role="tooltip" id="tooltip2" style="display:none;">
  More information available on hover.
</div>

<script>
  function showTooltip() {
    document.getElementById('tooltip2').style.display = 'block';
  }

  function hideTooltip() {
    document.getElementById('tooltip2').style.display = 'none';
  }
</script>
```

### **27. time 역할**    
time 역할은 웹 페이지에서 날짜나 시간을 나타내는 요소에 사용됩니다. 이 역할은 특정한 시간, 날짜, 기간을 명확하게 표현하고, 보조 기술이 이를 사용자에게 올바르게 전달할 수 있도록 돕습니다. HTML의 &lt;time&gt; 요소는 기본적으로 time 역할을 수행합니다.   
[W3C ARIA time](https://www.w3.org/TR/wai-aria-1.2/#time){: target="_blank"}   
[MDN Web Docs : time element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time){: target="_blank"}   
[UXKM : time element](https://uxkm.io/publishing/html/05-textLevel/18-time_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- time 역할은 시간이나 날짜와 관련된 정보를 나타내는 데 사용되며, HTML에서 &lt;time&gt; 요소가 이 역할을 수행합니다.    
- &lt;time&gt; 요소는 날짜와 시간 정보에 의미를 부여하고, 이 정보를 구조화하여 보조 기술이 정확하게 해석할 수 있도록 합니다. 예를 들어, 보조 기술은 이러한 요소를 사용해 사용자에게 시간을 읽어주거나 날짜를 설명할 수 있습니다.    
- &lt;time&gt; 요소는 datetime 속성을 사용하여 기계가 읽을 수 있는 형태로 날짜와 시간을 명시할 수 있습니다. 이 속성을 통해 날짜와 시간을 구체적으로 지정할 수 있습니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;time&gt;)를 사용하여 날짜와 시간을 명확하게 표현하고, datetime 속성을 통해 기계가 읽을 수 있는 형식으로 시간을 명시하는 것이 중요합니다.    
- **중요한 점**: time 역할을 통해 웹 콘텐츠에서 날짜와 시간을 명확하게 전달할 수 있으며, 이는 사용자 경험과 접근성을 향상시킬 수 있습니다. 이를 통해 사용자는 중요한 시간을 정확히 이해하고, 필요한 정보를 효율적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **정확한 날짜와 시간 제공**: &lt;time&gt; 요소를 사용할 때는 정확한 날짜와 시간을 제공해야 하며, datetime 속성을 사용해 기계가 읽을 수 있는 형식으로 명시하는 것이 좋습니다.   
- **날짜 및 시간의 명확한 표시**: 날짜와 시간은 사람이 읽을 수 있는 형식과 기계가 읽을 수 있는 형식으로 모두 제공되어야 합니다. 이를 통해 보조 기술이 정확한 정보를 사용자에게 전달할 수 있습니다.
- **시멘틱 마크업을 우선 사용**: 가능한 경우, &lt;time&gt; 요소를 사용하여 시간을 시멘틱하게 표현하는 것이 좋습니다. 이는 문서의 구조를 명확히 하고, 보조 기술이 시간을 올바르게 해석할 수 있도록 돕습니다.

**상속된 상태 및 속성**   
- **datetime 속성**: 이 속성은 날짜와 시간을 ISO 8601 형식으로 명시하여, 보조 기술이 이를 정확하게 해석하고 사용자에게 전달할 수 있도록 돕습니다.       


**잘못된 예시 - datetime 속성 누락**
이 예시는 날짜를 나타내고 있지만, datetime 속성이 없어 보조 기술이 이를 정확히 해석하지 못할 수 있습니다. 날짜와 시간을 명확히 전달하기 위해 datetime 속성을 포함하는 것이 좋습니다.   
```sh
<p>The conference will be held on <time>August 25</time>.</p>
```

**(권장) 올바른 예시 - datetime 속성을 포함한 날짜 표시**
이 예시는 &lt;time&gt; 요소를 사용하여 이벤트 시작 시간을 나타내고 있으며, datetime 속성을 통해 ISO 8601 형식으로 시간을 명시하고 있습니다. 보조 기술은 이를 통해 정확한 시간을 사용자에게 전달할 수 있습니다.    
```sh
<p>The conference will be held on <time datetime="2024-08-25">August 25</time>.</p>
```

**날짜를 나타내는 예시**
이 예시는 프로젝트 마감일을 &lt;time&gt; 요소로 나타내고 있으며, datetime 속성을 통해 보조 기술이 날짜를 정확히 해석할 수 있도록 합니다.    
```sh
<p>Project deadline is <time datetime="2024-09-15">September 15, 2024</time>.</p>
```

### **28. meter 역할**    
meter 역할은 웹 콘텐츠에서 특정 범위 내에서의 측정된 값이나 분포를 나타내는 데 사용됩니다. 이 역할은 보조 기술이 해당 값을 적절히 해석하고 사용자에게 전달할 수 있도록 돕습니다. 일반적으로 진행률, 점수, 용량 등의 상대적인 값을 표현하는 데 사용됩니다.   
[W3C ARIA meter](https://www.w3.org/TR/wai-aria-1.2/#meter){: target="_blank"}   
[MDN Web Docs : meter element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter){: target="_blank"}   
[UXKM : meter element](https://uxkm.io/publishing/html/09-forms/12-meter_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- meter 역할은 숫자 범위 내에서 측정된 값을 나타내며, 사용자가 그 값이 어디에 위치하는지 쉽게 이해할 수 있도록 합니다.    
- 이 역할은 측정된 값이 특정 범위 내에 있음을 나타내기 때문에, 사용자가 값의 상태를 더 잘 이해할 수 있게 합니다.    
- HTML의 &lt;meter&gt; 요소가 기본적으로 meter 역할을 수행합니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;meter&gt;)를 우선 사용하고, 명시적으로 role="meter"를 지정하여 필요한 경우 값을 명확하게 표현합니다.    
- **중요한 점**: meter 역할을 통해 웹 콘텐츠에서 값을 효과적으로 전달할 수 있으며, 이는 사용자 경험과 접근성을 향상시키는 데 기여합니다. 잘못된 사용을 피하고, 명확한 속성 설정을 통해 값의 의미를 정확히 전달하는 것이 중요합니다.    

**사용 시 주의사항**   
- **적절한 범위 설정**: meter 역할을 사용할 때는 aria-valuemin, aria-valuemax, aria-valuenow 속성을 명확히 정의하여 사용자가 값을 쉽게 이해할 수 있도록 해야 합니다.   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소인 &lt;meter&gt;를 사용하는 것이 좋습니다. 이는 보조 기술이 값을 더 잘 해석할 수 있게 돕습니다.
- **값의 텍스트 표현 고려**: 특정 경우에 aria-valuetext 속성을 사용해 사용자에게 더 나은 텍스트 설명을 제공할 수 있습니다.

**상속된 상태 및 속성**   
- **aria-valuenow**: 현재 값으로, meter 요소가 나타내는 정확한 값을 지정합니다. 이 속성은 보조 기술이 사용자에게 현재 값을 전달하는 데 사용됩니다.       
- **aria-valuemin**: 허용되는 최솟값을 지정합니다. 이 속성을 통해 현재 값이 전체 범위 내에서 어디에 위치하는지 알 수 있습니다.       
- **aria-valuemax**: 허용되는 최댓값을 지정합니다. 이 속성은 값이 얼마나 높은지를 정의하는 데 사용됩니다.       
- **aria-valuetext**: aria-valuenow의 값 대신 사용자에게 표시될 텍스트를 제공합니다. 예를 들어, 숫자 대신 설명이 필요할 때 유용합니다.       


**잘못된 예시 - 불명확한 값과 범위 설정**
이 예시는 meter 역할을 사용했으나, aria-valuenow, aria-valuemin, aria-valuemax와 같은 중요한 속성들을 누락하여 보조 기술이 값을 올바르게 해석할 수 없습니다. 이러한 속성들은 값이 무엇을 의미하는지 명확히 설명할 수 있도록 추가되어야 합니다.   
```sh
<div role="meter">70%</div>
```

**올바른 예시 - 명시적으로 meter 역할 지정하여 명확한 범위와 값 설정**
이 예시는 role="meter"를 사용하여 div 요소를 통해 값을 표시합니다. aria-valuenow, aria-valuemin, aria-valuemax 속성을 통해 값의 범위를 명확히 지정합니다. 이로 인해 보조 기술이 값을 정확히 인식하고 사용자에게 전달할 수 있습니다.    
```sh
<div role="meter" aria-valuenow="70" aria-valuemin="0" aria-valuemax="100">
  70%
</div>
```

**(권장) 시멘틱 마크업으로 제공되는 meter 역할 예시**
이 예시는 value, min, max 속성을 사용하여 현재 값이 전체 범위 내에서 어디에 위치하는지를 표시합니다. &lt;meter&gt; 요소는 기본적으로 meter 역할을 수행합니다.    
```sh
<meter value="70" min="0" max="100">70%</meter>
```

### **29. blockquote 역할**    
blockquote 요소는 웹 페이지에서 인용된 텍스트를 나타내는 데 사용되는 시멘틱 HTML 요소입니다. 이 요소는 다른 출처에서 인용된 긴 텍스트 블록을 구분하여, 보조 기술이 이를 사용자에게 명확하게 전달할 수 있도록 돕습니다. 일반적으로 인용문은 들여쓰기를 통해 시각적으로 구분되며, 출처를 명시할 수도 있습니다.   
[W3C ARIA blockquote](https://www.w3.org/TR/wai-aria-1.2/#blockquote){: target="_blank"}   
[MDN Web Docs : blockquote element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote){: target="_blank"}   
[UXKM : blockquote element](https://uxkm.io/publishing/html/04-grouping/13-blockquote_element){: target="_blank"}   

**기본 설명**  
- blockquote 요소는 긴 인용문을 나타내며, 주로 다른 출처에서 가져온 내용을 강조하거나 인용할 때 사용됩니다.    
- HTML의 &lt;blockquote&gt; 요소는 인용된 콘텐츠가 원래 출처에서 온 것임을 나타내며, 인용문의 출처를 명시하기 위해 cite 속성을 사용할 수 있습니다.    
- &lt;blockquote&gt; 요소는 시멘틱 마크업을 통해 보조 기술이 인용문을 올바르게 인식하고 사용자에게 전달할 수 있도록 합니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;blockquote&gt;)를 사용하여 인용문을 명확하게 표현하고, cite 속성을 사용해 인용문의 출처를 명시하는 것이 좋습니다.    
- **중요한 점**: blockquote 요소를 통해 웹 콘텐츠에서 인용문을 명확하게 구분할 수 있으며, 이는 사용자 경험과 접근성을 향상시키는 데 도움이 됩니다. 이를 통해 사용자는 인용문의 의미와 출처를 정확히 이해할 수 있습니다.    

**사용 시 주의사항**   
- **긴 인용문에 사용**: &lt;blockquote&gt; 요소는 긴 인용문을 나타내는 데 사용되며, 짧은 인용문에는 &lt;q&gt; 요소를 사용하는 것이 더 적합합니다.   
- **출처 명시**: 인용문의 출처를 명확히 하기 위해 cite 속성을 사용하는 것이 바람직합니다. 이 속성은 인용문의 출처를 URL로 지정하여, 보조 기술이 이를 사용자에게 전달할 수 있도록 돕습니다.
- **시멘틱 마크업 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;blockquote&gt;)를 사용하여 인용문을 명확하게 표현하는 것이 좋습니다. 이는 문서의 구조를 명확히 하고, 보조 기술이 콘텐츠를 올바르게 해석할 수 있도록 돕습니다.

**상속된 상태 및 속성**   
- **cite 속성**: 인용문의 출처를 URL로 지정합니다. 이 속성을 사용하여 보조 기술이 출처를 사용자에게 전달할 수 있습니다.       


**잘못된 예시 - blockquote 요소 없이 인용문 표시**
이 예시는 blockquote 요소 없이 인용문을 단락(&lt;p&gt;) 내에 포함시켰습니다. 이 경우 인용문이 시각적으로 또는 시멘틱적으로 구분되지 않으며, 보조 기술이 이를 인용문으로 인식하지 못할 수 있습니다.   
```sh
<p>
  "The greatest glory in living lies not in never falling, but in rising every time we fall." - Nelson Mandela
</p>
```

**(권장) 올바른 예시 - blockquote 요소 사용**
이 예시는 blockquote 요소를 사용하여 인용문을 명확히 구분하고 있으며, cite 속성을 통해 인용문의 출처를 제공하여 보조 기술이 이를 올바르게 전달할 수 있도록 합니다.    
```sh
<blockquote cite="https://www.w3.org/WAI/fundamentals/accessibility-intro/ko#context">
  웹의 힘은 보편성에 있습니다. 장애에 상관없이 모두가 접근할 수 있다는 것이 가장 중요한 부분입니다.
</blockquote>
```

**출처를 명시하지 않은 인용문 예시**
이 예시는 blockquote 요소를 사용하여 인용문을 나타내고 있으며, cite 속성을 사용하지 않아 출처를 명시하지 않은 인용문입니다. 출처를 명시하지 않은 경우, 인용문이 어디에서 왔는지 보조 기술이 사용자에게 알리지 못할 수 있습니다.    
```sh
<blockquote>
  웹의 힘은 보편성에 있습니다. 장애에 상관없이 모두가 접근할 수 있다는 것이 가장 중요한 부분입니다.
</blockquote>
```

### **30. caption 역할**    
caption 역할은 웹 콘텐츠에서 표, 그림, 동영상 등의 요소에 대한 제목이나 설명을 제공하는 역할을 합니다. 이 역할을 통해 보조 기술이 표나 다른 미디어 콘텐츠에 대한 제목 또는 설명을 인식하고 사용자에게 전달할 수 있도록 돕습니다. HTML의 &lt;caption&gt; 요소는 기본적으로 표의 제목을 제공하는 데 사용되며, 시멘틱하게 콘텐츠의 목적을 명확히 합니다.   
[W3C ARIA caption](https://www.w3.org/TR/wai-aria-1.2/#caption){: target="_blank"}   
[MDN Web Docs : caption element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption){: target="_blank"}   
[UXKM : caption element](https://uxkm.io/publishing/html/08-table/02-caption_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- caption 역할은 주로 표와 같은 구조화된 데이터 또는 다른 미디어 콘텐츠의 제목이나 설명을 제공하는 데 사용됩니다.    
- HTML의 &lt;caption&gt; 요소는 &lt;table&gt; 요소와 함께 사용되어, 표의 내용을 요약하거나 설명하는 역할을 합니다. 이는 보조 기술이 표의 목적을 이해하고 사용자에게 전달하는 데 도움이 됩니다.    
- caption은 table, grid, treegrid의 첫 번째 자식 요소로 위치합니다.   
- caption은 figure의 첫 번째 또는 마지막 자식 요소로 위치합니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;caption&gt;)를 사용하여 콘텐츠의 제목이나 설명을 명확하게 제공하고, 사용자가 콘텐츠의 목적을 쉽게 이해할 수 있도록 해야 합니다.    
- **중요한 점**: caption 역할을 통해 웹 콘텐츠의 목적을 명확하게 전달할 수 있으며, 이는 사용자 경험과 접근성을 향상시키는 데 기여합니다. 이를 통해 사용자는 콘텐츠의 의미를 더 쉽게 이해하고, 관련 정보를 효과적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **적절한 위치에 사용**: caption 역할은 표의 제목이나 설명을 제공하는 것이므로, &lt;caption&gt; 요소는 반드시 &lt;table&gt; 요소의 첫 번째 자식 요소로 사용되어야 합니다.   
- **시멘틱 마크업 사용**: 가능한 경우, 시멘틱한 HTML 요소인 &lt;caption&gt;을 사용하여 표의 제목이나 설명을 제공하는 것이 좋습니다. 이는 문서의 구조를 명확히 하고, 보조 기술이 표의 내용을 올바르게 해석할 수 있도록 돕습니다.
- **다양한 미디어에 적용**: 표뿐만 아니라 다른 미디어 요소(예: 동영상, 이미지 갤러리)에도 caption 역할을 적용하여 콘텐츠에 대한 설명을 제공할 수 있습니다.

**상속된 상태 및 속성**   
-  **aria-labelledby**를 설정하여 간결한 이름을 포함하는 요소를 참조하고    
-  **aria-describedby**를 설정하여 설명 콘텐츠가 포함된 요소를 참조할 수 있습니다.       


**잘못된 예시 - caption 역할 없이 표 표시**
이 예시는 표에 제목이나 설명을 제공하지 않아서, 표의 목적을 이해하기 어려울 수 있습니다. caption 요소를 사용하여 표의 내용을 설명하는 것이 중요합니다.   
```sh
<table>
  <tr>
    <th>Product</th>
    <th>Sales</th>
    <th>Revenue</th>
  </tr>
  <tr>
    <td>Apples</td>
    <td>1000</td>
    <td>$500</td>
  </tr>
  <tr>
    <td>Oranges</td>
    <td>1500</td>
    <td>$750</td>
  </tr>
</table>
```

**(권장) 올바른 예시 - caption 요소를 사용하여 설명 제공**
이 예시는 caption 요소를 사용하여 표의 내용을 설명하는 "Quarterly Revenue by Product"라는 제목을 제공하고 있습니다. 이는 보조 기술이 표의 목적을 사용자에게 올바르게 전달하는 데 도움이 됩니다.    
```sh
<table>
  <caption>Quarterly Revenue by Product</caption>
  <tr>
    <th scope="col">Product</th>
    <th scope="col">Q1</th>
    <th scope="col">Q2</th>
  </tr>
  <tr>
    <td>Apples</td>
    <td>$1000</td>
    <td>$1200</td>
  </tr>
  <tr>
    <td>Oranges</td>
    <td>$1500</td>
    <td>$1600</td>
  </tr>
</table>
```

**동영상에 설명 제공 예시**   
이 예시는 동영상 콘텐츠에 대한 설명을 제공하기 위해 &lt;figcaption&gt; 요소를 사용했습니다. 이와 같이 다양한 미디어 콘텐츠에 caption 역할을 적용하여 사용자에게 추가 정보를 제공할 수 있습니다.    
```sh
<figure>
  <video src="video.mp4" controls></video>
  <figcaption>This video explains the process of data analysis.</figcaption>
</figure>
```

**명시적으로 사용한 예시**   
```sh
<div role="table" aria-labelledby="name" aria-describedby="desc">
   <div role="caption">
     <div id="name">Contest Entrants</div>
     <div id="desc">
       This table shows the total number of entrants (500) the
       contest accepted over the past four weeks.
     </div>
   </div>
</div>
```

### **31. deletion 역할**    
deletion 역할은 웹 콘텐츠에서 삭제된 텍스트를 나타내는 데 사용됩니다. 이 역할을 통해 보조 기술이 해당 텍스트가 문서에서 삭제되었음을 인식하고 사용자에게 이를 전달할 수 있습니다. 이 역할은 보통 HTML에서 &lt;del&gt; 요소로 구현되며, 삭제된 텍스트는 취소선으로 표시됩니다.   
[W3C ARIA deletion](https://www.w3.org/TR/wai-aria-1.2/#caption){: target="_blank"}   
[MDN Web Docs : del element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del){: target="_blank"}   
[UXKM : del element](https://uxkm.io/publishing/html/07-edits/01-del_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- deletion 역할은 문서에서 삭제된 텍스트를 나타내며, 이 텍스트는 더 이상 사용되지 않거나 변경된 내용임을 의미합니다.    
- HTML의 &lt;del&gt; 요소는 이 역할을 기본적으로 수행하며, 문서에서 삭제된 텍스트를 시각적으로 취소선으로 표시합니다.   
- 보조 기술은 deletion 역할을 사용하여 해당 텍스트가 삭제되었음을 사용자에게 알릴 수 있습니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;del&gt;)를 사용하여 삭제된 텍스트를 명확하게 표시하고, 필요에 따라 cite 및 datetime 속성을 사용하여 삭제된 텍스트의 출처와 날짜를 제공하는 것이 좋습니다.    
- **중요한 점**: deletion 역할을 통해 웹 콘텐츠에서 삭제된 텍스트를 명확하게 전달할 수 있으며, 이는 사용자 경험과 접근성을 향상시키는 데 도움이 됩니다. 이를 통해 사용자는 텍스트의 변화를 정확히 이해하고, 관련 정보를 효율적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **삭제된 텍스트의 명확한 표시**: deletion 역할은 문서에서 삭제된 텍스트를 명확히 표시하는 데 사용됩니다. 텍스트가 시멘틱하게 삭제되었음을 나타내기 위해 이 역할을 사용하는 것이 좋습니다.   
- **cite 및 datetime 속성 사용 고려**: 삭제된 텍스트의 출처나 삭제된 날짜를 명확히 하기 위해 cite 및 datetime 속성을 사용하는 것이 바람직합니다.
- **시멘틱 마크업 사용**: 가능한 경우, 시멘틱한 HTML 요소(&lt;del&gt;)를 사용하여 삭제된 텍스트를 명확하게 표시하는 것이 좋습니다. 이는 문서의 구조를 명확히 하고, 보조 기술이 텍스트의 변화를 올바르게 해석할 수 있도록 돕습니다.

**상속된 상태 및 속성**   
- **cite 속성**: 삭제된 텍스트의 출처를 URL로 지정합니다. 이를 통해 보조 기술이 삭제된 이유나 출처를 사용자에게 전달할 수 있습니다.   
- **datetime 속성**: 텍스트가 삭제된 날짜와 시간을 ISO 8601 형식으로 지정합니다. 이를 통해 보조 기술이 삭제된 시점을 사용자에게 전달할 수 있습니다.       


**잘못된 예시 - 단순 취소선**
이 예시는 span 요소에 취소선 스타일을 적용하여 텍스트를 시각적으로 삭제된 것처럼 보이게 하지만, 시멘틱 마크업을 사용하지 않았기 때문에 보조 기술이 이를 삭제된 텍스트로 인식하지 못합니다.   
```sh
<p>This is an <span style="text-decoration: line-through;">outdated</span> information.</p>
```

**(권장) 올바른 예시 - 시멘틱 마크업 사용**
이 예시는 HTML의 &lt;del&gt; 요소를 사용하여 "outdated"라는 단어가 삭제되었음을 표시하고 있습니다. 이 요소는 텍스트가 문서에서 삭제되었음을 명확히 표시하고 있으며, 보조 기술이 이를 올바르게 인식할 수 있습니다.    
```sh
<p>This is an <del>outdated</del> information.</p>
```

**(권장) cite 및 datetime 속성을 사용한 예시**
이 예시는 cite 속성을 사용하여 삭제된 텍스트의 출처를 명시하고, datetime 속성을 통해 텍스트가 삭제된 날짜를 지정하고 있습니다. 이는 보조 기술이 삭제된 텍스트에 대한 추가 정보를 사용자에게 전달할 수 있도록 돕습니다.    
```sh
<p>The policy was updated from <del cite="https://www.example.com/old-policy" datetime="2024-08-10">previous terms</del> to reflect new guidelines.</p>
```

### **32. emphasis 역할**    
emphasis 역할은 웹 콘텐츠에서 텍스트를 강조하는 데 사용됩니다. 이 역할은 텍스트의 중요성을 강조하거나 특정 부분에 의미를 부여할 때 사용되며, 보조 기술이 이 강조를 인식하고 사용자에게 전달할 수 있도록 돕습니다. HTML에서 &lt;em&gt; 요소는 이 역할을 기본적으로 수행하며, 일반적으로 이탤릭체로 표시됩니다.   
[W3C ARIA emphasis](https://www.w3.org/TR/wai-aria-1.2/#emphasis){: target="_blank"}   
[MDN Web Docs : em element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em){: target="_blank"}   
[UXKM : em element](https://uxkm.io/publishing/html/05-textLevel/02-em_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- emphasis 역할은 강조해야 할 텍스트를 나타내며, 이 텍스트는 문맥상 중요한 의미를 가집니다. 강조된 텍스트는 브라우저에서 일반적으로 이탤릭체로 표시되지만, 시멘틱하게 강조된 텍스트로 해석됩니다.    
- HTML의 &lt;em&gt; 요소는 시멘틱 마크업으로, 문서 내에서 특정 텍스트에 강조를 부여하는 역할을 합니다. 이는 보조 기술이 강조된 부분을 인식하고 사용자에게 전달할 수 있게 합니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;em&gt;)를 우선 사용하여 강조의 의미를 부여하고, 텍스트를 명확하게 표현하는 것이 중요합니다.    
- **중요한 점**: emphasis 역할을 통해 웹 콘텐츠에서 텍스트를 시멘틱하게 강조함으로써, 사용자 경험과 접근성을 향상시킬 수 있습니다. 강조의 의미를 정확히 전달하여, 사용자가 중요한 정보를 더 쉽게 인식하고 이해할 수 있도록 합니다.    

**사용 시 주의사항**   
- **의미 있는 강조에 사용**: emphasis 역할은 단순히 텍스트의 스타일을 변경하기 위해 사용해서는 안 됩니다. 강조의 의미를 실제로 부여해야 하는 경우에만 사용해야 합니다.   
- **중첩 사용 고려**: 다른 강조 요소(&lt;strong&gt;, &lt;b&gt; 등)와 함께 사용될 수 있습니다. 그러나 지나친 중첩은 피해야 하며, 중첩 사용 시에는 각 요소의 시멘틱 의미를 고려해야 합니다.
- **시멘틱 마크업 사용**: 가능한 경우, 시멘틱한 HTML 요소인 &lt;em&gt;을 사용하여 텍스트를 강조하는 것이 좋습니다. 이는 문서의 구조를 명확히 하고, 보조 기술이 콘텐츠를 올바르게 해석할 수 있도록 돕습니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. emphasis 역할은 텍스트에 시멘틱 강조를 부여하는 데 사용되며, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - 스타일링을 위한 잘못된 사용**
이 예시는 &lt;span&gt; 요소에 이탤릭 스타일을 적용하여 텍스트를 강조하고 있지만, 시멘틱 마크업을 사용하지 않았기 때문에 보조 기술이 이를 강조된 텍스트로 인식하지 못합니다. em 요소를 사용하는 것이 더 적절합니다.   
```sh
<p>This is <span style="font-style: italic;">important</span> information.</p>
```

**(권장) 올바른 예시 - 기본적으로 제공되는 emphasis 역할 사용**
이 예시는 HTML의 &lt;em&gt; 요소를 사용하여 "always"라는 단어를 강조하고 있습니다. 이 텍스트는 브라우저에서 이탤릭체로 표시되며, 보조 기술이 이를 강조된 텍스트로 인식하여 사용자에게 전달할 수 있습니다.    
```sh
<p>You should <em>always</em> check your work before submitting it.</p>
```

### **33. insertion 역할**    
insertion 역할은 웹 콘텐츠에서 새로 추가된 텍스트를 나타내는 역할을 합니다. 이 역할은 보조 기술이 문서에 추가된 내용을 인식하고 사용자에게 전달할 수 있도록 돕습니다. HTML에서 이 역할은 &lt;ins&gt; 요소를 통해 구현되며, 일반적으로 밑줄로 표시됩니다.   
[W3C ARIA insertion](https://www.w3.org/TR/wai-aria-1.2/#insertion){: target="_blank"}   
[MDN Web Docs : ins element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ins){: target="_blank"}   
[UXKM : ins element](https://uxkm.io/publishing/html/07-edits/02-ins_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- insertion 역할은 문서에서 새로 추가된 텍스트를 나타냅니다. 이 역할을 통해 보조 기술은 해당 텍스트가 문서에 추가되었음을 사용자에게 알릴 수 있습니다.    
- HTML의 &lt;ins&gt; 요소는 기본적으로 이 역할을 수행하며, 문서에서 추가된 텍스트를 시각적으로 표시합니다.    
- 이 역할은 문서의 수정 기록이나 텍스트 변경 사항을 명확히 하여 사용자에게 중요한 정보를 전달하는 데 사용됩니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;ins&gt;)를 사용하여 추가된 텍스트를 명확하게 표시하고, 필요에 따라 cite 및 datetime 속성을 사용하여 추가된 텍스트의 출처와 날짜를 제공하는 것이 좋습니다.    
- **중요한 점**: insertion 역할을 통해 웹 콘텐츠에서 새로 추가된 텍스트를 명확하게 전달할 수 있으며, 이는 사용자 경험과 접근성을 향상시키는 데 도움이 됩니다. 이를 통해 사용자는 텍스트의 변화를 정확히 이해하고, 관련 정보를 효율적으로 탐색할 수 있습니다.    

**사용 시 주의사항**   
- **새로 추가된 텍스트의 명확한 표시**: insertion 역할은 문서에서 새로 추가된 텍스트를 명확히 표시하는 데 사용됩니다. 시멘틱 마크업을 통해 이 역할을 명확히 해야 합니다.   
- **cite 및 datetime 속성 사용 고려**: 새로 추가된 텍스트의 출처와 날짜를 명확히 하기 위해 cite 및 datetime 속성을 사용하는 것이 바람직합니다.
- **시멘틱 마크업 사용**: 가능한 경우, 시멘틱한 HTML 요소인 &lt;ins&gt;를 사용하여 텍스트를 추가된 내용으로 명확하게 표시하는 것이 좋습니다. 이는 보조 기술이 콘텐츠의 변경 사항을 올바르게 해석할 수 있도록 돕습니다.

**상속된 상태 및 속성**   
- **cite 속성**: 새로 추가된 텍스트의 출처를 URL로 지정합니다. 이를 통해 보조 기술이 추가된 텍스트의 출처를 사용자에게 전달할 수 있습니다.       
- **datetime 속성**: 텍스트가 추가된 날짜와 시간을 ISO 8601 형식으로 지정합니다. 이를 통해 보조 기술이 해당 시점을 사용자에게 전달할 수 있습니다.       


**잘못된 예시 - 단순 밑줄 스타일링**
이 예시는 &lt;span&gt; 요소에 밑줄 스타일을 적용하여 텍스트를 시각적으로 추가된 것처럼 보이게 했지만, 시멘틱 마크업을 사용하지 않았기 때문에 보조 기술이 이를 추가된 텍스트로 인식하지 못합니다.   
```sh
<p>This is an <span style="text-decoration: underline;">updated</span> information.</p>
```

**(권장) 올바른 예시 - 시멘틱 마크업 사용**
이 예시는 &lt;ins&gt; 요소를 사용하여 텍스트가 시멘틱하게 추가되었음을 명확히 표시하고 있으며, 보조 기술이 이를 올바르게 인식할 수 있습니다.    
```sh
<p>This is an <ins>updated</ins> information.</p>
```

**(권장) cite 및 datetime 속성을 사용한 예시**
이 예시는 cite 속성을 사용하여 새로 추가된 텍스트의 출처를 명시하고, datetime 속성을 통해 텍스트가 추가된 날짜를 지정하고 있습니다. 이는 보조 기술이 추가된 텍스트에 대한 추가 정보를 사용자에게 전달할 수 있도록 돕습니다.    
```sh
<p>The policy was revised to include <ins cite="https://www.example.com/new-policy" datetime="2024-08-10">new terms</ins> for better clarity.</p>
```

### **34. strong 역할**    
strong 역할은 웹 콘텐츠에서 텍스트의 중요성을 강조하는 역할을 합니다. 이 역할은 해당 텍스트가 문맥적으로 매우 중요한 의미를 가지며, 보조 기술이 이를 인식하여 사용자에게 전달할 수 있도록 돕습니다. HTML에서는 &lt;strong&gt; 요소가 이 역할을 기본적으로 수행하며, 브라우저에서 일반적으로 굵은 글씨체로 표시됩니다.   
[W3C ARIA strong](https://www.w3.org/TR/wai-aria-1.2/#strong){: target="_blank"}   
[MDN Web Docs : strong element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong){: target="_blank"}   
[UXKM : strong element](https://uxkm.io/publishing/html/05-textLevel/04-strong_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- strong 역할은 문서 내에서 특정 텍스트가 매우 중요하거나 강조되어야 할 경우 사용됩니다. 이 요소를 사용하면 브라우저는 해당 텍스트를 굵게 표시하여 시각적으로 강조하며, 보조 기술은 이 텍스트가 중요함을 사용자에게 전달합니다.    
- HTML의 &lt;strong&gt; 요소는 시멘틱 마크업으로, 문서 내에서 중요한 텍스트를 강조하는 역할을 합니다. 이는 단순한 시각적 강조를 넘어서, 텍스트의 의미를 명확하게 전달하기 위한 시멘틱한 의미를 부여합니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;strong&gt;)를 우선 사용하여 강조의 의미를 부여하고, 텍스트를 명확하게 표현하는 것이 중요합니다.    
- **중요한 점**: strong 역할을 통해 웹 콘텐츠에서 텍스트를 시멘틱하게 강조함으로써, 사용자 경험과 접근성을 향상시킬 수 있습니다. 강조의 의미를 정확히 전달하여, 사용자가 중요한 정보를 더 쉽게 인식하고 이해할 수 있도록 합니다.    

**사용 시 주의사항**   
- **의미 있는 강조에 사용**: strong 역할은 단순히 텍스트의 스타일을 변경하기 위해 사용해서는 안 되며, 문맥적으로 중요한 의미를 가진 텍스트에만 사용해야 합니다.   
- **중첩 사용 고려**: 다른 강조 요소(&lt;em&gt;, &lt;b&gt; 등)와 함께 사용될 수 있지만, 지나친 중첩은 피하는 것이 좋습니다. 각 요소의 시멘틱 의미를 고려하여 사용해야 합니다.
- **시멘틱 마크업 사용**: 가능한 경우, 시멘틱한 HTML 요소인 &lt;strong&gt;을 사용하여 텍스트를 강조하는 것이 좋습니다. 이는 문서의 구조를 명확히 하고, 보조 기술이 콘텐츠를 올바르게 해석할 수 있도록 돕습니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. strong 역할은 텍스트에 시멘틱한 중요성을 부여하는 데 사용되며, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - 단순 굵은 글씨를 위한 잘못된 사용**
이 예시는 &lt;span&gt; 요소에 굵은 글씨 스타일을 적용하여 텍스트를 강조하고 있지만, 시멘틱 마크업을 사용하지 않았기 때문에 보조 기술이 이를 강조된 텍스트로 인식하지 못합니다. strong 요소를 사용하는 것이 더 적절합니다.   
```sh
<p>This is <span style="font-weight: bold;">important</span> information.</p>
```

**(권장) 올바른 예시 - 시멘틱 마크업 사용**
이 예시는 HTML의 &lt;strong&gt; 요소를 사용하여 "very important"라는 단어를 강조하고 있습니다. 이 텍스트는 브라우저에서 굵은 글씨로 표시되며, 보조 기술이 이를 강조된 텍스트로 인식하여 사용자에게 전달할 수 있습니다.    
```sh
<p>This is <strong>very important</strong> information.</p>
```

### **35. subscript 역할**    
subscript 역할은 웹 콘텐츠에서 텍스트를 아래 첨자로 표시하는 역할을 합니다. 이 역할은 주로 수학적 표현, 화학식, 또는 특정 약어에서 사용되며, 텍스트가 일반 텍스트 라인 아래로 이동하여 표시됩니다. HTML에서 &lt;sub&gt; 요소가 이 역할을 기본적으로 수행합니다.   
[W3C ARIA subscript](https://www.w3.org/TR/wai-aria-1.2/#subscript){: target="_blank"}   
[MDN Web Docs : sub element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub){: target="_blank"}   
[UXKM : sub element](https://uxkm.io/publishing/html/05-textLevel/10-sub_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- subscript 역할은 텍스트를 아래 첨자로 표시하며, 이는 주로 과학적, 수학적, 또는 기술적 문서에서 사용됩니다. 예를 들어, 화학식에서 물(H₂O)의 숫자 2는 아래 첨자로 표시됩니다.    
- HTML의 &lt;sub&gt; 요소는 기본적으로 subscript 역할을 수행하며, 보조 기술이 이 텍스트를 아래 첨자로 인식하고 사용자에게 올바르게 전달할 수 있도록 돕습니다.    
- **적절한 사용**: 시멘틱한 HTML 요소(&lt;sub&gt;)를 우선 사용하고, 필요한 경우 role="subscript"를 명시적으로 지정하여 텍스트를 아래 첨자로 표시합니다.   
- **중요한 점**: subscript 역할을 통해 텍스트를 시멘틱하게 표시함으로써, 웹 콘텐츠의 접근성과 사용성을 향상시킬 수 있습니다. 잘못된 사용을 피하고, 시멘틱한 요소를 통해 텍스트를 정확히 표시하는 것이 중요합니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소인 &lt;sub&gt;를 사용하여 텍스트를 아래 첨자로 표시하는 것이 좋습니다. 이는 보조 기술이 텍스트를 올바르게 해석할 수 있도록 돕습니다.
- **올바른 용도**: subscript 역할은 텍스트를 아래 첨자로 표시해야 하는 경우에만 사용해야 하며, 단순한 시각적 스타일링을 위해 사용하지 않도록 주의해야 합니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. subscript 역할은 텍스트를 시각적으로 아래 첨자로 표시하는 데 사용되며, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - 스타일링을 위한 잘못된 사용**
이 예시는 단순히 텍스트 크기를 줄이는 방식으로 아래 첨자 효과를 내고 있지만, 시멘틱 마크업을 사용하지 않았기 때문에 보조 기술이 이를 아래 첨자로 인식하지 못합니다. sub 요소 또는 subscript 역할을 사용하는 것이 더 적절합니다.   
```sh
<span style="font-size: smaller;">2</span>
```

**(권장) 올바른 예시 - 시멘틱 마크업 사용**
이 예시는 시멘틱한 HTML 요소인 &lt;sub&gt;를 사용하여 "mc²"에서 숫자 2를 아래 첨자로 표시하고 있습니다. &lt;sub&gt; 요소는 기본적으로 subscript 역할을 수행합니다.    
```sh
<p>The equation is E = mc<sub>2</sub>.</p>
```

**명시적으로 subscript 역할 지정**
이 예시는 div 요소에 role="subscript"를 사용하여 숫자 2를 아래 첨자로 명시적으로 지정한 예시입니다.    
```sh
<div role="subscript">2</div>
```

### **36. superscript 역할**    
superscript 역할은 웹 콘텐츠에서 텍스트를 위 첨자로 표시하는 역할을 합니다. 이 역할은 주로 수학적 지수, 상표 기호, 또는 특정 약어에서 사용되며, 텍스트가 일반 텍스트 라인 위로 이동하여 표시됩니다. HTML에서 &lt;sup&gt; 요소가 이 역할을 기본적으로 수행합니다.   
[W3C ARIA superscript](https://www.w3.org/TR/wai-aria-1.2/#superscript){: target="_blank"}   
[MDN Web Docs : sup element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup){: target="_blank"}   
[UXKM : sup element](https://uxkm.io/publishing/html/05-textLevel/11-sup_element#gsc.tab=0){: target="_blank"}   

**기본 설명**  
- superscript 역할은 텍스트를 위 첨자로 표시하며, 이는 주로 과학적, 수학적, 또는 기술적 문서에서 사용됩니다. 예를 들어, 수학적 표현에서 E=mc²에서 숫자 2는 위 첨자로 표시됩니다.    
- HTML의 &lt;sup&gt; 요소는 기본적으로 superscript 역할을 수행하며, 보조 기술이 이 텍스트를 위 첨자로 인식하고 사용자에게 올바르게 전달할 수 있도록 돕습니다.    
- 적절한 사용: 시멘틱한 HTML 요소(&lt;sup&gt;)를 우선 사용하고, 필요한 경우 role="superscript"를 명시적으로 지정하여 텍스트를 위 첨자로 표시합니다.   
- 중요한 점: superscript 역할을 통해 텍스트를 시멘틱하게 표시함으로써, 웹 콘텐츠의 접근성과 사용성을 향상시킬 수 있습니다. 잘못된 사용을 피하고, 시멘틱한 요소를 통해 텍스트를 정확히 표시하는 것이 중요합니다.    

**사용 시 주의사항**   
- **시멘틱 마크업을 우선 사용**: 가능한 경우, 시멘틱한 HTML 요소인 &lt;sup&gt;를 사용하여 텍스트를 위 첨자로 표시하는 것이 좋습니다. 이는 보조 기술이 텍스트를 올바르게 해석할 수 있도록 돕습니다.   
- **올바른 용도**: superscript 역할은 텍스트를 위 첨자로 표시해야 하는 경우에만 사용해야 하며, 단순한 시각적 스타일링을 위해 사용하지 않도록 주의해야 합니다.

**상속된 상태 및 속성**   
- 기본적으로 상속된 상태나 속성은 없습니다. superscript 역할은 텍스트를 시각적으로 위 첨자로 표시하는 데 사용되며, 추가적인 ARIA 상태나 속성이 필요하지 않습니다.       


**잘못된 예시 - 스타일링을 위한 잘못된 사용**
이 예시는 단순히 텍스트 크기를 줄이고 위치를 올리는 방식으로 위 첨자 효과를 내고 있지만, 시멘틱 마크업을 사용하지 않았기 때문에 보조 기술이 이를 위 첨자로 인식하지 못합니다. sup 요소 또는 superscript 역할을 사용하는 것이 더 적절합니다.   
```sh
<span style="vertical-align: super; font-size: smaller;">2</span>
```

**(권장) 올바른 예시 - 시멘틱 마크업 사용**
이 예시는 HTML의 &lt;sup&gt; 요소를 사용하여 "mc²"에서 숫자 2를 위 첨자로 표시하고 있습니다. &lt;sup&gt; 요소는 기본적으로 superscript 역할을 수행합니다.    
```sh
<p>The equation for energy is E = mc<sup>2</sup>.</p>
```

**명시적으로 superscript 역할 지정**
이 예시는 div 요소에 role="superscript"를 사용하여 숫자 2를 위 첨자로 명시적으로 지정한 예시입니다.    
```sh
<div role="superscript">2</div>
```



## 참조
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.1](https://www.w3.org/TR/wai-aria-1.1/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.2](https://www.w3.org/TR/wai-aria-1.2/){: target="_blank"}   
- [W3C Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://www.w3.org/TR/wai-aria-1.3/){: target="_blank"}   
- [W3C Editor's Draft - Accessible Rich Internet Applications (WAI-ARIA) 1.3](https://w3c.github.io/aria/){: target="_blank"}   
- [Accessibility Object Model](https://wicg.github.io/aom/explainer.html){: target="_blank"}   
- [W3C Class diagram of the relationships described in the role data model.](https://www.w3.org/TR/wai-aria-1.1/img/rdf_model.svg){: target="_blank"}   
- [MDN ARIA guides](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Guides){: target="_blank"}   
  