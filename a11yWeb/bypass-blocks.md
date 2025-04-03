# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #지체 장애 사용자, #비장애 사용자


### 반복 영역 건너뛰기 
**관련 지침 : 콘텐츠의 반복되는 영역은 건너뛸 수 있어야 한다.**   
웹사이트 상단의 메뉴, 검색창, 광고 영역 등 **반복적으로 나타나는 콘텐츠 블록은 키보드 사용자와 스크린 리더 사용자들이 본문으로 빠르게 이동할 수 있도록 "본문 바로가기(Skip to content)" 링크를 제공**해야 합니다.     

[2.4.1 블록 건너뛰기 (Bypass Blocks) (Level A)](https://www.w3.org/TR/WCAG22/#bypass-blocks){: target="_blank"}    
[WAI - Understanding Bypass Blocks](https://www.w3.org/WAI/WCAG22/Understanding/bypass-blocks.html){: target="_blank"}      
[MDN - HTML 링크 앵커](https://developer.mozilla.org/ko/docs/Web/HTML/Element/a){: target="_blank"}    

- 반복 영역을 건너뛸 수 있는 수단 제공: 웹 페이지가 제공하는 핵심 영역이 위치한 곳으로 직접 이동하는 건너뛰기 링크를 제공한다. 건너뛰기 링크는 웹 페이지의 가장 앞에 제공한다.    
- 여러 개의 건너뛰기 링크 제공: 여러 개의 건너뛰기 링크를 제공하는 경우, 핵심 영역으로 이동하기 위한 건너뛰기 링크를 가장 먼저 나타내도록 한다.    
- 시각적인 구현: 건너뛰기 링크는 시각장애인뿐만 아니라 지체장애인도 키보드 조작 횟수를 줄일 수 있게 하는 효과적인 수단이므로, 메뉴 건너뛰기 링크는 화면에 보이도록 구현해야 한다.    

**기대효과**   

- 웹 페이지의 상단이나 좌측 프레임에 동일한 링크 목록이 반복되는 영역이 포함되어 있으면, 화면낭독프로그램은 이 링크 목록을 순서대로 읽어준 후에야 필요한 부분을 읽어주므로 매우 불편하다. 마찬가지로, 키보드 사용자는 모든 링크 목록을 순차적으로 이동해야 핵심 영역으로 이동할 수 있어 매우 불편하다. 그러나 웹 페이지의 첫 부분에 핵심 영역으로 이동할 수 있는 건너뛰기 링크를 제공하면, 키보드 사용자는 몇 번의 키보드 조작을 통해서 핵심 영역으로 빠르게 이동할 수 있다.    
- 색인이 없는 긴 문장으로 구성된 콘텐츠의 경우, 콘텐츠의 특정 위치로 이동하는 것이 매우 불편하다. 그러나 웹 페이지의 시작 부분에 색인을 제공하면, 필요한 부분으로 직접 이동할 수 있어 보다 쉽고 빠르게 내비게이션할 수 있다. 콘텐츠를 장, 절, 소절 등으로 구분하면, 웹브라우저 또는 보조기술이 제공하는 장, 절, 소절 간의 빠른 이동 수단을 이용할 수 있게 된다.   
- 여러 페이지로 구성된 웹사이트에서 사이트 맵을 제공하면, 사용자는 이를 이용하여 필요한 정보가 위치한 페이지로 보다 쉽고 빠르게 이동할 수 있다.    


#### 1. 필요성        
키보드 사용자는 페이지가 로딩된 이후 모든 웹 페이지에 공통적으로 들어있는 메뉴 및 링크 목록 등을 탭 키를 이용하여 순차적으로 내비게이션한 후에 핵심 영역에 도달하게 된다. 화면낭독프로그램을 이용하는 사람은 메뉴 등을 페이지가 로딩되거나 갱신될 때마다 모든 웹 페이지에 공통적으로 들어있는 메뉴 등을 다시 듣게 된다. 키보드 사용자와 화면낭독프로그램 사용자가 겪게 되는 이러한 불편을 방지하기 위해, 사용자가 메뉴 등과 같은 반복 영역을 바로 건너뛰어 핵심 영역으로 직접 이동할 수 있는 수단을 제공해야 한다.     

- 매번 상단 메뉴/검색 영역을 탐색하지 않고 본문으로 이동 가능   
- 스크린 리더 사용자와 키보드 사용자에게 반복 탐색의 피로도 감소   
- 접근성 향상 및 UX 향상 효과   

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 반복된 탐색 없이 빠르게 본문으로 이동  
| 지체 장애 사용자     | 키보드 조작 최소화 필요  
| 비장애 사용자         | 효율적인 정보 접근  


#### 3. 체크리스트       

- “본문 바로가기” 링크가 페이지 최상단에 존재하는가?   
- 포커스 시 시각적으로 명확히 드러나는가?   
- 링크가 본문 영역의 앵커(target)로 연결되는가?   
- 스크린 리더에서도 인식 가능한가?    

#### 4. 테스트 방법      

- 페이지 처음 로드 후 Tab 키로 “본문 바로가기” 링크 확인   
- 포커스 시 시각적 스타일 제공 여부 확인   
- 링크 클릭 시 실제 본문으로 초점 이동 여부 확인   

#### 5. QA 지표       

- 본문 바로가기 링크 제공률   
- 포커스 스타일 명확성   
- 스크린 리더 탐색 가능성   

#### 6. 개발방법     

#### HTML 예시
```html
<a href="#main" class="skip-link">본문 바로가기</a>

<style>
.skip-link {
  position: absolute;
  left: -9999px;
}
.skip-link:focus {
  left: 0;
  top: 0;
  background: #000;
  color: #fff;
  padding: 10px;
  z-index: 1000;
}
</style>

<main id="main">
  <h1>본문 영역입니다.</h1>
</main>
```

#### Vue 예시
```vue
<template>
  <a href="#mainContent" class="skip-link">본문 바로가기</a>
  <main id="mainContent">
    <h1>메인 콘텐츠</h1>
  </main>
</template>

<style scoped>
.skip-link {
  position: absolute;
  left: -9999px;
}
.skip-link:focus {
  left: 0;
  top: 0;
  background: #007bff;
  color: white;
  padding: 8px;
}
</style>
```

#### React 예시
```jsx
function SkipLink() {
  return (
    <>
      <a href="#main" className="skip-link">본문 바로가기</a>
      <main id="main">
        <h1>본문 콘텐츠</h1>
      </main>
      <style>
        {`
          .skip-link {
            position: absolute;
            left: -9999px;
          }
          .skip-link:focus {
            left: 0;
            top: 0;
            background: black;
            color: white;
            padding: 8px;
            z-index: 1000;
          }
        `}
      </style>
    </>
  );
}
```

#### 7. 점검 기준     

- Skip 링크가 시맨틱하게 `<a>` 태그로 구현되었는가?   
- 포커스 시 사용자에게 인지 가능한가?   
- ID와 앵커 대상이 정확히 연결되어 있는가?   

#### 8. 점검 방법     

- 페이지 로딩 후 Tab 키 → 첫 번째 포커스 요소가 skip 링크인지 확인   
- 클릭 또는 Enter → 해당 영역으로 이동되는지 확인   
- 스크린 리더 탐색에서 “본문 바로가기”가 읽히는지 확인   

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-bypass-blocks01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<a href="#main">본문 바로가기</a>
<main id="main">...</main>
```


#### 10. 미준수 사례       

```html
<!-- skip link 없음 또는 display:none 처리 -->
<a href="#main" style="display:none;">본문</a>
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/O3z10F7Dnig?si=h8tuSN9T0xwamW5-" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (반복 영역 건너뛰기)](https://www.youtube.com/embed/O3z10F7Dnig?si=h8tuSN9T0xwamW5-){: target="_blank"}    
   
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
