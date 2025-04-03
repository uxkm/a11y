# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #저시력 사용자, #인지장애 사용자, #고령자


### 사용자 요구에 따른 실행 
**관련 지침 : 사용자가 의도하지 않은 기능(새 창, 초점에 의한 맥락 변화 등)은 실행되지 않아야 한다.**   
콘트롤이나 사용자 입력은 초점을 받았을 때 의도하지 않는 기능이 자동적으로 실행되지 않도록 콘텐츠를 개발해야 한다. 즉, 콘트롤이나 사용자 입력 기능은 사용자의 마우스 클릭이나 키보드 조작에 의하여 실행되어야 한다. 특히 새 창, 팝업창 등은 사용자가 인지하지 못한 상황에서 열리지 않아야 한다.      

[3.2.5 사용자 요청에 따른 변경 (Level AAA)](https://www.w3.org/TR/WCAG22/#change-on-request){: target="_blank"}   

1) 초점에 의한 맥락 변화: 웹 콘텐츠를 구성하는 콘트롤이 초점을 받았을 경우, 사용자가 의도하지 않은 기능이 실행되지 않아야 한다. 단, 기능의 실행이 아니라 초점을 받은 요소의 색깔이 반전되거나 테두리가 생기는 것과 같은 시각적인 변화, 또는 사용자 제어가 이동하지 않은 상태에서 나타나는 추가 정보 등은 초점에 의한 맥락 변화를 일으키는 기능의 실행으로 간주하지 않는다. 다음은 종종 발생하는 대표적인 오류들이다.    
    (가) 온라인 서식이 자동적으로 제출됨    
    (나) 새 창이 열림   
    (다) 드롭다운 메뉴가 열림만으로 특정 메뉴 항목이 실행됨    
    (라) 풀다운 메뉴를 사용하는 콘텐츠에서 초점을 받는 것만으로 특정 메뉴의 기능이 실행됨   
    (마) 사용자 제어(초점)가 다른 콘트롤로 이동하거나 사라지거나 또는 그 위치를 예측할 수 없음    
2) 입력에 따른 변화: 사용자가 선택할 수 있는 콘트롤(예: 콤보 박스, 라디오 버튼, 체크 박스 등)에서 어떤 항목을 선택하는 경우, 해당 항목이 의미하는 기능이 실행되거나 서식 제출이 일어나지 않아야 한다. 실제로 해당 기능이 실행되거나 서식 제출이 일어나는 것은 사용자가 선택할 수 있는 콘트롤과 함께 제공되는 실행 버튼을 활성화(클릭)하였을 때 비로소 실행되어야 한다. 단, 기능의 실행이 아니라 초점을 받은 사용자 입력 또는 콘트롤의 색깔이 반전되거나 테두리가 생기는 것과 같은 시각적인 변화, 또는 사용자 제어(초점)가 이동하지 않은 상태에서 나타나는 추가 정보 등은 입력 변화에 따른 기능의 실행으로 간주하지 않는다.    
3) 새 창/팝업창: 사용자가 예측할 수 없는 상황에서 새 창을 열어 정보를 전달해서는 안 된다.  
4) 레이어 팝업: 레이어 팝업은 콘텐츠의 논리적 초점 이동 및 콘텐츠의 선형구조를 위반할 가능성이 많으므로 사용하지 않는 것이 바람직하다.    
5) 새 창/팝업창/레이어 팝업의 닫음: 새 창/팝업창/레이어 팝업에 초점이 있을 경우, 새 창/팝업창/레이어 팝업을 닫거나 종료 버튼을 클릭하였을 때, 해당 창 또는 팝업 등이 종료되어야 한다. 사용자가 화면에 나타난 새 창/팝업창/레이어 팝업을 닫거나 종료하도록 요구하였음에도 불구하고 해당 창 또는 팝업 등이 종료되지 않으면 사용자는 매우 당황하게 된다. 특히 레이어 팝업의 경우 이러한 혼란이 가중될 수 있다.     

**기대효과**   

- 시각장애, 지적장애 또는 지체장애가 있는 사람도 초점 및 문맥의 변화를 이해할 수 있게 된다.    
- 사용자에게 미리 새 창 열림을 경고하면 뒤로 가기 버튼이 더 이상 예상처럼 동작하지 않는다는 사실을 알 수 있으므로 이용하는 데 따른 혼란이 줄어든다.    

#### 1. 필요성        
웹사이트 또는 웹 애플리케이션에서 링크 클릭, 버튼 누름, 초점 이동 등의 인터랙션이 있을 때, **사용자가 명시적으로 요청하지 않은 행동(예: 새 창 열림, 페이지 자동 전환, 맥락 변경 등)** 은 자동으로 실행되어서는 안 됩니다.   

- 예기치 않은 동작은 **혼란**과 **오류 발생 가능성**을 높임    
- 스크린 리더 사용자, 저시력 사용자 등은 **자동 초점 이동**이나 **자동 페이지 전환** 시 맥락을 잃을 수 있음     
- 사용자 경험 향상뿐 아니라 접근성을 위한 핵심 요소   

#### 2. 대상       

| 사용자 유형   | 이유 |
|----------------|------|
| 스크린 리더 사용자 | 자동 초점 전환 시 탐색 순서가 왜곡될 수 있음 |
| 저시력 사용자     | 새 창이 열리면 현재 위치 인식이 어려움 |
| 인지장애 사용자   | 자동 실행된 맥락 변화가 혼란 유발 가능 |
| 고령자           | 변화된 콘텐츠에 대한 인지 지연 발생 가능성 있음 |

#### 3. 체크리스트       

- 새 창을 여는 경우, 사용자에게 사전 안내 또는 선택지를 제공하는가?    
- 폼 전송, 셀렉트 박스 변경 등에서 자동 페이지 전환이 발생하지 않는가?    
- 포커스가 의도하지 않은 위치로 자동 이동되지 않는가?    
- `target="_blank"` 사용 시 텍스트 또는 `aria-label`로 새 창 열림을 명시하는가?    

#### 4. 테스트 방법      

- 버튼/링크 클릭 시 **새 창 또는 맥락 전환 발생 여부** 확인   
- **select 요소 선택 변경만으로 페이지가 이동**되는지 확인   
- 스크린 리더 사용 시 자동 초점 이동 발생 여부 확인    
- 사용자의 입력 없이 DOM 조작으로 자동 변경되는 동작 여부 확인   

#### 5. QA 지표       

- 자동 맥락 변경 발생 비율   
- 새 창 열림 시 사전 안내 제공률   
- 스크린 리더 사용자 혼란 사례 수   

#### 6. 개발방법     

#### HTML 예시 – 새 창 열림 알림 추가
```html
<a href="https://example.com" target="_blank" aria-label="예제 사이트 (새 창 열림)">
  예제 사이트 방문
</a>
```

#### 잘못된 예시 – 선택만으로 페이지 이동
```html
<select onchange="location.href=this.value;">
  <option value="/home">홈</option>
  <option value="/about">회사 소개</option>
</select>
```

#### 개선된 예시 – 버튼으로 명시적 전환
```html
<select id="gotoPage">
  <option value="/home">홈</option>
  <option value="/about">회사 소개</option>
</select>
<button onclick="goToPage()">이동</button>

<script>
function goToPage() {
  const url = document.getElementById('gotoPage').value;
  window.location.href = url;
}
</script>
```

#### Vue 예시
```vue
<template>
  <select v-model="selected">
    <option value="/home">홈</option>
    <option value="/about">회사 소개</option>
  </select>
  <button @click="navigate">이동</button>
</template>

<script setup>
import { ref } from 'vue';
const selected = ref('');
function navigate() {
  if (selected.value) window.location.href = selected.value;
}
</script>
```

#### React 예시
```jsx
function PageNavigator() {
  const [url, setUrl] = React.useState('');

  const handleNavigate = () => {
    if (url) window.location.href = url;
  };

  return (
    <>
      <select onChange={e => setUrl(e.target.value)}>
        <option value="">선택</option>
        <option value="/home">홈</option>
        <option value="/about">회사 소개</option>
      </select>
      <button onClick={handleNavigate}>이동</button>
    </>
  );
}
```

#### 7. 점검 기준     

- 사용자의 조작 없이 자동으로 맥락이 변경되는가?    
- 새 창 열기 또는 초점 이동이 명확히 안내되는가?   
- 스크린 리더 또는 키보드 사용자가 인지 가능한가?   

#### 8. 점검 방법     

- 모든 링크, 버튼 클릭 시 자동 창 열림 또는 전환 발생 여부 확인    
- `onchange`, `onload` 등의 이벤트로 자동 동작 실행 여부 확인   
- 스크린 리더로 해당 기능 사용 후 포커스 위치 확인   

#### 9. 준수 사례       

```html
<a href="help.html" target="_blank" aria-label="도움말 (새 창 열림)">도움말</a>
```

#### 10. 미준수 사례       

```html
<select onchange="window.location.href=this.value;">
  <option value="home.html">홈</option>
  <option value="about.html">소개</option>
</select>
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/tuFn0SCLOP8?si=QqNHBo_o5brJCUzo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (사용자 요구에 따른 실행)](https://www.youtube.com/embed/tuFn0SCLOP8?si=QqNHBo_o5brJCUzo){: target="_blank"}    
   
--- 
<strong style="font-size:20px;cursor:pointer;">접근성 테스트 도구 활용 점검방법</strong>
모바일 앱 접근성 과 내용 동일

 
#### 결론     
모바일 앱 접근성 과 내용 동일




### 참조    
- [Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/){: target="_blank"}    
- [WCAG 2.2 Understanding Docs](https://www.w3.org/WAI/WCAG22/Understanding/){: target="_blank"}    
- [WCAG (Quick Reference)](https://www.w3.org/WAI/WCAG22/quickref/?versions=2.2&showtechniques=111){: target="_blank"}    
- [웹 콘텐츠 접근성 지침(WCAG) 2.2 - 번역판](https://a11ykr.github.io/wcag22/){: target="_blank"}    
- [smashingmagazine - WCAG 2.2 Checklist with Filter and Links](https://codepen.io/smashingmag/pen/MWLgQzm){: target="_blank"}    
- [MDN 웹 컨텐츠 접근성 지침 이해하기](https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG){: target="_blank"}    
- [보건복지부 블로그](https://blog.naver.com/prologue/PrologueList.naver?blogId=mohw2016){: target="_blank"}     
- [행정안전부 - 전자정부 웹사이트 UI UX 가이드라인](https://www.mois.go.kr/frt/bbs/type001/commonSelectBoardArticle.do?bbsId=BBSMSTR_000000000045&nttId=69451){: target="_blank"}     
- [널리 알리는 기술 소식 커뮤니티](https://nuli.navercorp.com/community/article){: target="_blank"}     
