# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #인지장애 사용자, #비장애 사용자


### 콘텐츠 간의 구분   
**관련 지침 : 이웃한 콘텐츠는 구별될 수 있어야 한다.**   
웹 페이지를 구성하는 이웃한 콘텐츠는 시각적으로 구분되도록 제공해야 한다.     
모든 이웃한 콘텐츠는 시각적으로 구분될 수 있도록 구현해야 한다.        


🔗 관련 WCAG 2.2 성공 기준  
[1.3.1 정보 및 관계 (Level A)](https://www.w3.org/TR/WCAG22/#info-and-relationships){: target="_blank"}    
[WAI - Understanding Info and Relationships](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships.html){: target="_blank"}      
[MDN - HTML Sectioning Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section){: target="_blank"}    

**이웃한 콘텐츠를 시각적으로 구분하기 위한 예**     

- 테두리를 이용하여 구분    
- 콘텐츠 사이에 시각적인 구분선을 삽입하여 구분   
- 서로 다른 무늬를 이용하여 구분    
- 콘텐츠 배경색 간의 명도대비(채도)를 달리하여 구분    
- 줄 간격 및 글자 간격을 조절하여 구분   
- 기타 콘텐츠를 시각적으로 구분할 수 있는 방법 등   

**기대효과**   

- 이웃한 콘텐츠 간에 간격을 두면 손가락으로 이용할 수 있는 터치스크린을 채용한 기기에서도 콘텐츠의 식별과 조작이 가능하게 된다.    

#### 1. 필요성        

- 시각적/인지적 경계를 통해 정보 그룹을 명확히 인식 가능   
- 스크린 리더 사용자에게도 각 콘텐츠의 목적을 구분 가능하게 함   
- 섹션 구분이 명확하면 정보 이해도 향상 및 피로도 감소   


#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 콘텐츠 그룹 간 구조적 구분 필요  
| 인지장애 사용자     | 명확한 시각적 구분이 정보 이해에 도움  
| 비장애 사용자         | 레이아웃 정돈을 통한 정보 흐름 이해 용이  

#### 3. 체크리스트       

- 인접한 콘텐츠 블록 간 시각적 구분(여백, 테두리, 배경색 등)이 있는가?    
- 구조적 마크업(`<section>`, `<article>`, `<nav>`, `<aside>` 등)을 활용했는가?    
- 제목, 구분선, 구획 요소 등을 통해 의미가 구분되는가?    

#### 4. 테스트 방법      

- 시각적으로 인접한 콘텐츠 그룹 확인    
- 보조기술로 각 콘텐츠의 시작/종료 경계 인식 가능 여부 확인    
- CSS 제거 시 구조적 마크업만으로도 콘텐츠를 구분할 수 있는지 확인    

#### 5. QA 지표       

- 시각적 구분 요소(테두리, 배경, 간격 등) 제공률   
- 스크린 리더 사용 시 콘텐츠 단위별 인식률   
- 구조화된 시맨틱 태그 사용률   

#### 6. 개발방법     

#### HTML 예시
```html
<section>
  <h2>공지사항</h2>
  <ul>
    <li>정기 점검 안내</li>
  </ul>
</section>

<section>
  <h2>이벤트</h2>
  <ul>
    <li>봄맞이 경품 이벤트</li>
  </ul>
</section>
```

#### Vue 예시
```vue
<template>
  <div class="content-group">
    <section>
      <h2>자주 묻는 질문</h2>
      <ul><li>Q1. 로그인 방법</li></ul>
    </section>
    <section>
      <h2>고객센터</h2>
      <p>운영시간: 9시~18시</p>
    </section>
  </div>
</template>
```

#### React 예시
```jsx
function InfoSections() {
  return (
    <div>
      <section>
        <h2>공지사항</h2>
        <ul>
          <li>서비스 점검 예정</li>
        </ul>
      </section>
      <section>
        <h2>FAQ</h2>
        <ul>
          <li>비밀번호 변경 방법</li>
        </ul>
      </section>
    </div>
  );
}
```

#### 7. 점검 기준     

- 콘텐츠 블록마다 시각적 또는 구조적 구분 요소가 있는가?   
- 구조적으로 마크업이 적절하게 분리되어 있는가?   

#### 8. 점검 방법     

- 개발자 도구로 시맨틱 태그, 클래스, 구분자 사용 여부 확인    
- 스크린 리더를 사용하여 섹션 구분 여부 청취    
- CSS 없이 HTML만으로 구분 가능한지 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-grouping-content01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<section>
  <h2>최근 게시글</h2>
  <ul><li>접근성에 대한 이야기</li></ul>
</section>
<hr />
<section>
  <h2>인기 게시글</h2>
  <ul><li>Vue vs React 비교</li></ul>
</section>
```

#### 10. 미준수 사례       

```html
<div>
  <h2>최근 게시글</h2>
  <ul><li>접근성에 대한 이야기</li></ul>
  <h2>인기 게시글</h2>
  <ul><li>Vue vs React 비교</li></ul>
</div>
<!-- 구분 없음, 구조적 구획 미사용 -->
```


#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/Zk0HSiIWSEU?si=v7lMoj3BvVZc4NMv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (콘텐츠 간의 구분)](https://www.youtube.com/embed/Zk0HSiIWSEU?si=v7lMoj3BvVZc4NMv){: target="_blank"}    

   
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
