# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #인지장애 사용자, #비장애 사용자


### 제목 제공 
**관련 지침 : 페이지, 프레임, 콘텐츠 블록에는 적절한 제목을 제공해야 한다.**   
페이지, 프레임, 콘텐츠 블록의 제목은 사용자가 웹 콘텐츠를 운용하기 쉽게 도와준다. 제목은 간단 명료해야 하며, 해당 페이지, 프레임, 콘텐츠 블록을 유추할 수 있도록 제공해야 한다.     

[2.4.2 페이지 제목 (Page Titled) (Level A)](https://www.w3.org/TR/WCAG22/#page-titled){: target="_blank"}      
[2.4.6 제목 및 레이블 (Headings and Labels) (Level AA)](https://www.w3.org/TR/WCAG22/#headings-and-labels){: target="_blank"}    
[WAI - Understanding Page Titles](https://www.w3.org/WAI/WCAG22/Understanding/page-titled.html){: target="_blank"}      
[MDN - HTML 제목 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/title){: target="_blank"}    


- 웹 페이지 제목(title) 제공: 모든 웹 페이지가 해당 내용을 간단명료하게 기술한 제목을 포함하고 있을 경우, 사용자(예: 시각장애인, 지적장애인, 중증지체장애인 등)는 여러 개의 웹 페이지가 열려 있더라도 제목을 통해 웹 페이지를 선택하므로, 모든 웹 페이지에는 해당 페이지를 간단명료하게 설명한 제목을 제공해야 한다. 또한, 웹 페이지는 유일하고 서로 다른(unique and exclusive) 제목을 제공해야 한다.    
- 팝업창 제목(title) 제공: 팝업창에도 제목을 제공해야 한다.    
- 프레임 제목(title) 제공: 웹 페이지의 모든 프레임에는 각 프레임을 설명하는 간단명료한 제목을 제공해야 한다. 모든 프레임에 간단명료한 제목이 부여되면, 사용자(예: 시각장애인, 지적장애인, 중증지체장애인 등)는 프레임 제목을 통해 프레임의 선택, 이동 등이 가능하다. 아무런 내용이 없는 프레임에도 '빈 프레임' 등과 같이 제목을 제공해야 한다.    
- 콘텐츠 블록 제목 구성: 콘텐츠 블록에는 적절한 제목(heading)을 제공하면 제목과 본문을 구분할 수 있으며, 제목을 이용하여 콘텐츠 블록 간의 이동이 가능하다. 그러나 본문이 없는 콘텐츠 블록에는 제목을 붙이지 않아야 한다.    
- 특수 기호 사용 제한: 웹 페이지, 프레임 또는 콘텐츠 블록의 제목은 문장의 하나로 간주하여 불필요한 특수 기호를 반복하여 사용하지 않아야 한다.    


**기대효과**   

- 웹사이트가 제공하는 모든 웹 페이지에 서로 다른 제목을 제공하면, 사용자(예: 시각장애인, 지적장애인, 지체장애인 등)는 동시에 여러 개의 웹 페이지가 열려 있더라도 웹 페이지의 제목을 확인하여 열려있는 웹 페이지 간을 편리하게 이동할 수 있다. 이를 위해, 각 페이지는 해당 페이지만의 유일하고 서로 다른 페이지 제목을 가져야 한다.    
- 웹 페이지를 구성하는 모든 프레임에 제목을 제공하면, 사용자(예: 시각장애인, 지적장애인, 중증지체장애인 등)는 프레임 제목을 통해 프레임 간을 매우 편리하게 이동할 수 있다. 이를 위해, 페이지의 경우와 마찬가지로, 동일한 페이지에 포함된 모든 프레임은 해당 프레임만의 유일하고 서로 다른 프레임 제목을 가져야 한다.    

#### 1. 필요성        

- 콘텐츠 구조를 파악하고 빠르게 원하는 정보를 찾을 수 있도록 도움    
- 스크린 리더 사용자에게 명확한 내비게이션 경로 제공   
- 콘텐츠 의미를 설명하여 인지장애 사용자도 이해하기 쉬움   

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 제목을 통해 구조를 탐색  
| 인지장애 사용자     | 제목을 보고 내용 예측 가능  
| 비장애 사용자         | 섹션 간 빠른 이동 가능  

#### 3. 체크리스트       

- 모든 페이지에 `<title>` 요소가 있는가?   
- 콘텐츠 블록에 적절한 제목 태그(`<h1>~<h6>`)가 포함되어 있는가?   
- 제목은 콘텐츠의 주제를 잘 반영하고 있는가?   
- 제목 계층이 논리적으로 구성되어 있는가?   

#### 4. 테스트 방법      

- 브라우저 탭에서 `<title>` 확인   
- 스크린 리더를 사용하여 제목 목록 탐색   
- 콘텐츠 내의 heading 구조와 의미 일치 여부 확인   

#### 5. QA 지표       

- 제목 누락률   
- 제목 계층 오류율   
- 제목과 콘텐츠 일치도   

#### 6. 개발방법     

#### HTML 예시
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <title>고객센터 - 예시사이트</title>
</head>
<body>
  <main>
    <h1>고객센터</h1>
    <section>
      <h2>자주 묻는 질문</h2>
    </section>
    <section>
      <h2>1:1 문의하기</h2>
    </section>
  </main>
</body>
</html>
```

#### Vue 예시
```vue
<template>
  <main>
    <h1>고객센터</h1>
    <section>
      <h2>문의 게시판</h2>
    </section>
  </main>
</template>

<script setup>
document.title = '고객센터 - Vue 예제';
</script>
```

#### React 예시
```jsx
import { useEffect } from 'react';

function HelpCenter() {
  useEffect(() => {
    document.title = '고객센터 - React 예제';
  }, []);

  return (
    <main>
      <h1>고객센터</h1>
      <section>
        <h2>문의 게시판</h2>
      </section>
    </main>
  );
}
```

#### 7. 점검 기준     

- `<title>`이 페이지 내용을 대표하는가?   
- 콘텐츠 블록마다 `h1~h6` 구조가 논리적인가?   
- 중복되지 않는 의미 있는 제목이 사용되었는가?   


#### 8. 점검 방법     

- 브라우저 탭 제목과 콘텐츠의 일치 여부 확인   
- 개발자 도구에서 heading 계층 구조 확인   
- 스크린 리더의 heading 탐색 기능 사용   


#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-page-titled01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<title>이용약관 - SampleSite</title>
<h1>이용약관</h1>
```

#### 10. 미준수 사례       

```html
<!-- 제목 없음 또는 모호한 제목 -->
<title>문서</title>
<!-- <h1> 생략됨 -->
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/xuGoPImMXgU?si=iHy_LIFUMVsdnhv6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (제목 제공)](https://www.youtube.com/embed/xuGoPImMXgU?si=iHy_LIFUMVsdnhv6){: target="_blank"}    
   
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
