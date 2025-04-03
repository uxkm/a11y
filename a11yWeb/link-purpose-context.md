# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #인지장애 사용자, #비장애 사용자


### 적절한 링크 텍스트 
**관련 지침 : 링크 텍스트는 용도나 목적을 이해할 수 있도록 제공해야 한다.**   
링크는 주변 맥락을 통하여 용도나 목적지를 명확하게 이해할 수 있는 링크 텍스트를 제공해야 한다.     
즉, 링크 텍스트는 해당 링크가 어떤 페이지나 기능으로 연결되는지를 명확히 알려야 하며, “여기”, “자세히 보기”와 같은 모호한 표현은 피해야 합니다. 스크린 리더 사용자는 페이지 내 모든 링크 텍스트만 추출해 듣는 경우가 많으므로, **링크 자체만으로 목적을 이해할 수 있어야 합니다.**    

[2.4.4 링크 목적(문맥 내) (Level A)](https://www.w3.org/TR/WCAG22/#link-purpose-in-context){: target="_blank"}     
[2.4.9 링크 목적(링크만) (Level AAA)](https://www.w3.org/TR/WCAG22/#link-purpose-link-only){: target="_blank"}   
[WCAG 2.2 - 2.4.9 Link Purpose (Link Only)](https://www.w3.org/TR/WCAG22/#link-purpose-link-only){: target="_blank"}     
[WAI - Understanding Link Purpose](https://www.w3.org/WAI/WCAG22/Understanding/link-purpose-in-context.html){: target="_blank"}   


1. 맥락을 통해 이해할 수 있도록 링크 텍스트 제공: 링크의 용도나 목적지를 링크 텍스트만으로 또는 주변의 맥락으로부터 충분히 이해할 수 있도록 링크 텍스트를 제공해야 한다.     
(가) 문장의 일부분에 링크를 연결하는 경우: URL(Uniform Resource Locator) 목적지, 용도 등을 표현한 텍스트에 링크를 연결해야 한다.    
(나) ‘바로가기’, ‘GO’ 등의 링크 텍스트를 제공하는 경우: URL에 관한 정보를 제공하는 텍스트에 이어서 링크 텍스트를 삽입해야 한다.    
(다) 이미지 링크를 제공하는 경우: URL에 관한 정보를 제공하는 텍스트와 URL로 이동하는 이미지 링크는 하나의 링크로 구성하는 것이 바람직하다. 이 경우, 이미지 링크의 대체 텍스트는 공백 문자로 제공해야 한다.    
(라) 동일한 제품을 서로 다른 관점에서 각각 설명한 페이지로 이동하는 링크들은 각 링크 텍스트를 서로 다르게 구성하는 것이 바람직하다.    
(마) 탭(tab) 콘트롤을 이용하여 공지사항 목록을 나열하고, 주변에 ‘더보기’ 링크를 제공하는 콘텐츠에서 ‘더보기’ 링크는 그 맥락으로부터 ‘공지사항 더보기’임을 알 수 있어야 한다.     
2. 이미지 링크 구성: 아이콘(icon)으로 링크 텍스트를 대신하여 표현한 경우(예: 홈 페이지로 이동하기 위한 링크를 집 모양의 아이콘 이미지로 대신하고 해당 아이콘에 홈 페이지로 이동하는 링크를 걸어놓은 경우), 해당 아이콘 이미지만으로도 링크의 용도나 목적지, 내용 등을 충분히 이해할 수 있도록 직관적이고 명료하게 제공해야 한다. 아이콘에 대체 텍스트를 제공하는 방법은 검사항목 5.1.1의 ‘적절한 대체 텍스트 제공’을 참고해야 한다.    

**기대효과**   

- 텍스트에 링크를 연결할 때, **‘여기를 클릭하세요.’** 와 같이 애매모호한 표현을 사용하여 링크를 연결한 경우, 시각장애인이나 지적장애인뿐만 아니라 비장애인도 클릭했을 때 어떤 일이 일어날 것이며 무슨 내용이 제시될 것인지를 알 수 없다. 그러나 링크 텍스트를 직관적으로 구성하면, 장애인은 해당 링크를 클릭했을 때 무슨 일이 벌어질 것인지를 분명하게 알 수 있으므로, 시각장애인이나 지적장애인은 맥락을 이해하기 위한 쓸데없는 콘텐츠 간의 이동 과정을 피할 수 있다.   

#### 1. 필요성        

- 스크린 리더 사용자는 문서 내 모든 링크만 목록으로 듣기 때문에 텍스트가 명확하지 않으면 용도를 파악하기 어려움    
- “자세히 보기”, “클릭”, “여기” 등의 표현은 단독으로는 의미 전달 불가    
- 명확한 링크 텍스트는 접근성 향상 및 검색엔진 최적화(SEO)에 도움이 됨     

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 링크 텍스트만으로도 페이지 용도 파악 필요  
| 인지장애 사용자     | 반복적인 비유적 표현은 혼동을 유발함  
| 비장애 사용자         | 링크 목적 명확성은 사용성과 직접 연결됨  

#### 3. 체크리스트       

- 링크 텍스트만으로도 해당 목적이나 내용을 유추할 수 있는가?    
- 같은 텍스트에 여러 개의 링크가 연결되어 있지는 않은가?    
- “여기”, “자세히 보기” 등 모호한 표현을 제거했는가?    
- 문맥 의존이 아닌 링크 자체로 의미를 전달하는가?    

#### 4. 테스트 방법      

- 페이지에서 링크 텍스트만 스크린 리더로 들어본다    
- 링크 텍스트가 의미 있는 정보를 제공하는지 확인   
- 동일한 텍스트의 링크가 문서 내 반복되지 않는지 확인   

#### 5. QA 지표       

- 명확한 링크 텍스트 제공률   
- 모호한 링크 텍스트("여기", "자세히 보기") 사용률   
- 링크 목록 테스트 시 목적 이해 가능성   

#### 6. 개발방법     

#### HTML 예시 – 명확한 링크 텍스트
```html
<a href="/products/shoes">운동화 상품 보기</a>
```

#### 잘못된 예시 – 모호한 링크 텍스트
```html
<a href="/products/shoes">여기</a>
```

#### Vue 예시
```vue
<template>
  <a :href="productLink">운동화 상품 보기</a>
</template>

<script setup>
const productLink = "/products/shoes";
</script>
```

#### React 예시
```jsx
function ProductLink() {
  return <a href="/products/shoes">운동화 상품 보기</a>;
}
```

#### 7. 점검 기준     

- 링크 텍스트가 목적을 명확하게 설명하는가?    
- 스크린 리더 사용자도 링크만 듣고 이해할 수 있는가?    
- 동일한 링크 텍스트가 중복되어 사용되고 있지 않은가?    

#### 8. 점검 방법     

- DOM을 통해 링크 텍스트 수집 → 중복/모호 여부 확인   
- 스크린 리더로 링크만 목록화하여 테스트   
- 클릭 시 연결되는 목적지와 링크 텍스트의 일치성 확인    

#### 9. 준수 사례       

```html
<a href="/service/loan-info">신용대출 서비스 안내 보기</a>
```
<!-- <figure>
<img src="./../images/a11y-web/img-link-purpose-context01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->

#### 10. 미준수 사례       

```html
<a href="/service/loan-info">자세히 보기</a>
<a href="/service/loan-info">여기</a>
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/C4AvmYc7E8E?si=u3bKTkaGA56KYd1X" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (적절한 링크 텍스트)](https://www.youtube.com/embed/C4AvmYc7E8E?si=u3bKTkaGA56KYd1X){: target="_blank"}    
   
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
