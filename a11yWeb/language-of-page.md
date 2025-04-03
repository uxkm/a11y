# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #다국어 사용자, #외국인 사용자


### 기본 언어 표시 
**관련 지침 : 주로 사용하는 언어를 명시해야 한다.**   
웹 브라우저는 웹 페이지를 구성하는 텍스트 콘텐츠의 언어 정보를 바탕으로 텍스트 콘텐츠를 화면에 표시하거나 보조기술로 전달한다. 다국어를 지원하는 화면낭독프로그램을 사용하는 경우, 텍스트 콘텐츠의 언어 정보를 화면낭독프로그램으로 전달하여 정확한 발음으로 읽어주도록 제어하기도 한다.    
웹 페이지의 언어 명시: 웹 페이지에서 제공하는 콘텐츠에 적용되는 기본 언어를 반드시 정의해야 한다.      

[3.1.1 문서 언어 (Level A)](https://www.w3.org/TR/WCAG22/#language-of-page){: target="_blank"}

**기대효과**   

- 화면낭독프로그램과 점역 프로그램과 같은 보조기술은 웹 페이지의 기본 언어를 인식하여 자동적으로 음성 모듈을 선택하거나 해당 언어에 적합한 점역 방법을 선택할 수 있는 편리함이 있다.    

#### 1. 필요성        
웹 문서 또는 웹 애플리케이션은 콘텐츠의 기본 언어를 HTML 마크업 내에서 명시해야 합니다. 이는 보조기술(스크린 리더 등)이 정확한 발음과 언어 처리를 수행할 수 있도록 돕기 위한 핵심 요소입니다.   

- 스크린 리더는 문서의 언어 정보를 기반으로 **올바른 발음 및 문장 구조 해석**을 수행    
- 콘텐츠가 영어, 한국어, 일본어 등 다양한 언어로 구성될 경우, 언어가 명확히 지정되지 않으면 음성 출력이 부정확해짐     
- 검색 엔진 최적화(SEO) 및 콘텐츠의 의미적 해석에도 도움     

#### 2. 대상    

| 사용자 유형       | 필요 이유 |
|--------------------|-----------|
| 시각장애인         | 스크린 리더로 언어 인식 → 올바른 발음 제공  
| 다국어 사용자       | 언어 혼용 시 발음 구분 불가능 시 이해도 저하  
| 외국인 사용자       | 올바른 콘텐츠 번역과 해석을 위한 기반 제공 

#### 3. 체크리스트       

- `<html lang="ko">` 또는 해당 언어 코드가 명시되어 있는가?  
- 콘텐츠 내 다른 언어를 사용하는 요소에 `lang` 속성이 명시되어 있는가?  
- 스크린 리더가 페이지 언어를 정확하게 감지하고 있는가?

#### 4. 테스트 방법      

- 페이지 소스 확인 → `<html lang="ko">` 또는 다른 언어 코드 존재 여부 확인    
- 콘텐츠 내에 다국어 콘텐츠가 포함되어 있다면 `lang="en"`, `lang="ja"` 등으로 개별 설정되었는지 확인   
- 스크린 리더로 텍스트를 읽어볼 때 발음이 언어에 맞는지 확인   

#### 5. QA 지표       

- 문서 루트 요소에 언어 속성 존재율   
- 다국어 콘텐츠의 `lang` 속성 부여율   
- 스크린 리더 언어 인식 정확률   

#### 6. 개발방법     

#### HTML 전체 문서 언어 설정
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>웹 접근성 테스트</title>
</head>
<body>
  <p>안녕하세요. 웹 접근성 테스트입니다.</p>
</body>
</html>
```

#### 콘텐츠 일부 다국어 사용 시
```html
<p>웹 접근성은 <span lang="en">Accessibility</span> 을 의미합니다.</p>
```

#### Vue 예시 (lang은 index.html에서 지정)
```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <title>Vue 접근성 예제</title>
  </head>
  <body>
    <div id="app"></div>
  </body>
</html>
```

#### React 예시 (index.html 설정)
```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <title>React 접근성 예제</title>
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>
```


#### 7. 점검 기준     

- `<html>` 태그에 `lang` 속성이 선언되어 있는가?   
- 다국어 콘텐츠의 경우 개별 `lang` 속성으로 지정되어 있는가?   

#### 8. 점검 방법     

- HTML 코드 검사 → lang 속성 확인   
- 다국어 텍스트 영역에 lang 속성 적용 여부 확인   
- 스크린 리더(NVDA, JAWS 등)로 언어 발음 확인   

#### 9. 준수 사례       

```html
<html lang="ko">
<!-- 한국어 페이지에 한국어 지정 -->
```

#### 10. 미준수 사례       

```html
<html>
<!-- lang 속성 없음 → 스크린 리더가 기본 언어를 판단하지 못함 -->
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/Pujf4gdBu5M?si=tihdpdlVKFcbGsd2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (기본 언어 표시)](https://www.youtube.com/embed/Pujf4gdBu5M?si=tihdpdlVKFcbGsd2){: target="_blank"}    
   
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
