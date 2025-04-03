# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #문법 준수, #마크업, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각 장애인, #인지 장애인, #고령화, #키보드 사용자


### 마크업 오류 방지 
**관련 지침 : 마크업 언어의 요소는 열고 닫음, 중첩 관계 및 속성 선언에 오류가 없어야 한다.**   
마크업 언어로 작성된 콘텐츠는 해당 마크업 언어의 문법을 최대한 준수하여 제공하는 것이 바람직 하다. 특히 요소의 열고 닫음, 중첩 관계의 오류가 없도록 제공해야 한다. 또한 요소의 속성도 마크 업 문법을 최대한 준수하여 제공하는 것이 바람직하다.     

[4.1.1 구문 분석 (Parsing, Level A)](https://www.w3.org/TR/WCAG22/#parsing){: target="_blank"}    

**기대효과**   

- 시작 요소와 끝나는 요소가 잘 대응되고 요소 간의 포함 관계가 어긋나지 않도록 웹 페이지의 마크업 문서를 구성하면, 웹 브라우저나 보조기술이 작동을 멈추지 않고 콘텐츠를 명확히 전달할 수 있다.    
- 콘텐츠에 필요한 속성의 누락이나 중복된 경우를 없애 콘텐츠의 일부 기능이 누락되는 것을 방지할 수 있다.     


#### 1. 필요성        

- 잘못된 마크업은 스크린 리더 등 보조기술에 오작동을 유발함    
- 구조화되지 않은 문서는 포커스 순서 오류, 의미 왜곡 등 발생    
- 표준을 지킨 마크업은 다양한 브라우저에서 호환성을 보장함   

#### 2. 대상       

| 사용자 유형   | 필요 이유                                         |
|---------------|--------------------------------------------------|
| 시각장애인     | 스크린 리더가 오류 없이 문서를 정확히 해석해야 함 |
| 인지장애인     | 구조화된 콘텐츠로 정보 이해 향상                  |
| 고령자         | 예측 가능한 레이아웃 제공                         |
| 키보드 사용자 | 논리적인 포커스 순서 확보                         |

#### 3. 체크리스트       

- 태그는 열고 닫힘이 정확한가? (`<div></div>`)   
- 중첩 순서가 올바른가? (`<ul><li>항목</li></ul>`)   
- 중복된 `id`는 없는가?    
- `role`, `aria-*` 속성은 문법적으로 유효한가?   

#### 4. 테스트 방법      

- [W3C Validator](https://validator.w3.org/){: target="_blank"}를 통한 문법 유효성 검사   
- 접근성 검사 도구 (WAVE, Axe DevTools, Lighthouse 등) 사용    
- 브라우저 콘솔 및 개발자 도구로 DOM 오류 확인    

#### 5. QA 지표       

- 마크업 오류 건수   
- W3C Validator 통과율   
- 자동화 검사 도구 경고/오류 수량   

#### 6. 개발방법     

**HTML 예시 - 올바른 코드**
```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <title>정상 마크업 예시</title>
  </head>
  <body>
    <header><h1>접근성 타이틀</h1></header>
    <main>
      <section>
        <h2>콘텐츠 구역</h2>
        <p>내용이 여기에 들어갑니다.</p>
      </section>
    </main>
    <footer><p>푸터입니다.</p></footer>
  </body>
</html>
```

**HTML 예시 - 잘못된 코드**
```html
<html>
  <head><title>오류 예시</title></head>
  <body>
    <header><h1>제목
    <main>
      <section><p>닫힘 태그 누락
    </main>
</html>
```

#### 7. 점검 기준     

- 모든 요소는 정확한 위치에 올바르게 중첩되어야 함    
- 문법적으로 유효하지 않은 속성, 중복된 ID가 없어야 함    
- 모든 HTML 태그는 W3C 명세에 맞게 구성되어야 함   

#### 8. 점검 방법     

- 개발자 도구 또는 W3C Validator를 통한 정적 분석    
- HTML 및 ARIA 속성 유효성 확인    
- 접근성 자동 검사 도구를 통한 오류 노출   

#### 9. 준수 사례       

```html
<nav>
  <ul>
    <li><a href="#home">홈</a></li>
    <li><a href="#about">소개</a></li>
  </ul>
</nav>
```

#### 10. 미준수 사례       

```html
<nav>
  <ul>
    <li><a href="#home">홈
    <li><a href="#about">소개
</nav>
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/Xz3qma1in28?si=6er5DLAhZYj-wP-c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (마크업 오류 방지)](https://www.youtube.com/embed/Xz3qma1in28?si=6er5DLAhZYj-wP-c){: target="_blank"}    
   
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
