# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    

**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #키보드 사용자, #인지장애 사용자

   
### 콘텐츠의 선형구조   
**관련 지침 : 콘텐츠는 논리적인 순서로 제공해야 한다.**   
콘텐츠는 보조기술 사용자가 맥락을 이해할 수 있도록 논리적인 순서로 제공해야 한다.     


🔗 관련 WCAG 2.2 성공 기준     
[1.3.2 의미 있는 순서 (Meaningful Sequence) (Level A)](https://www.w3.org/TR/WCAG22/#meaningful-sequence){: target="_blank"}      
[WAI - Understanding Meaningful Sequence](https://www.w3.org/WAI/WCAG22/Understanding/meaningful-sequence.html){: target="_blank"}        
[MDN - CSS Positioning 참고](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Positioning){: target="_blank"}      

**기대효과**   


#### 1. 필요성        
콘텐츠는 시각적 배치와 무관하게, **스크린 리더나 키보드 사용자가 순차적으로 접근할 때도 의미가 유지되도록** 논리적인 순서로 구성되어야 합니다. CSS나 JavaScript를 통해 시각적으로 재배열된 콘텐츠도 **HTML 코드 상의 순서**는 논리적이어야 합니다.    


- 시각적으로는 이해할 수 있어도, **스크린 리더**는 문서 순서대로 콘텐츠를 읽음    
- CSS Flex/Grid 등으로 배치가 변경되어도 **DOM 순서가 의미를 유지**해야 함    
- 논리적인 콘텐츠 흐름은 사용자의 **이해도 향상 및 오독 방지**에 기여    

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 스크린 리더 사용 시 순서대로 콘텐츠 탐색  
| 키보드 사용자       | Tab 순서대로 기능과 정보에 접근  
| 인지장애 사용자     | 콘텐츠 흐름에 따라 정보를 처리  

#### 3. 체크리스트       

- 콘텐츠의 순서가 시맨틱하게 논리적인 흐름을 따르는가?    
- CSS 또는 JavaScript로 배치 순서만 변경되었고, HTML 순서는 잘못되지 않았는가?    
- 시각적으로 보이지 않는 요소가 먼저 포커스되지 않는가?    
- 반응형 구조에서 순서가 흐트러지지 않는가?    

#### 4. 테스트 방법      

- CSS를 제거한 상태로 페이지를 확인    
- 스크린 리더를 통해 순서대로 읽히는지 확인    
- 키보드(Tab)로 순서대로 접근되는지 확인    

#### 5. QA 지표       

- 시각적 순서와 코드 순서의 불일치 비율   
- Tab 포커스 순서의 오류 발생 건수   
- 스크린 리더 출력 흐름과 UI 의미 일치율    

#### 6. 개발방법     

#### HTML 예시 – 논리적 순서 유지
```html
<h2>상품 소개</h2>
<p>이 상품은...</p>
<button>구매하기</button>
```

#### 잘못된 예시 – 시각적 배치를 위해 순서를 변경
```html
<button>구매하기</button>
<h2>상품 소개</h2>
<p>이 상품은...</p>
<!-- CSS로 버튼을 아래로 이동 → 스크린 리더는 먼저 읽음 -->
```

#### Vue 예시
```vue
<template>
  <section>
    <h2>프로필</h2>
    <p>소개 내용</p>
    <button>연락하기</button>
  </section>
</template>
```

#### React 예시
```jsx
function ProfileSection() {
  return (
    <section>
      <h2>프로필</h2>
      <p>소개 내용</p>
      <button>연락하기</button>
    </section>
  );
}
```

#### 7. 점검 기준     

- HTML DOM 순서가 콘텐츠 의미 전달에 적합한가?    
- CSS로 시각적 위치를 바꾸더라도 시맨틱 흐름을 해치지 않는가?    

#### 8. 점검 방법     

- 개발자 도구로 DOM 순서를 확인    
- CSS 제거 후 텍스트 흐름 비교    
- 보조기술(스크린 리더) 또는 키보드 탐색 시 논리적 흐름 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-linearized01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<h2>서비스 요금</h2>
<p>요금은 매월 자동 결제됩니다.</p>
<button>결제하기</button>
```

#### 10. 미준수 사례       

```html
<button>결제하기</button>
<h2>서비스 요금</h2>
<p>요금은 매월 자동 결제됩니다.</p>
<!-- 시각적 배치용 위치 조정 -->
```



#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/7T3J8BQ0NwQ?si=ME_KcrKQcgrJbVYl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (콘텐츠의 선형 구조)](https://www.youtube.com/embed/7T3J8BQ0NwQ?si=ME_KcrKQcgrJbVYl){: target="_blank"}    
   
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
