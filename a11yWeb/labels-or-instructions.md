# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    

**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #색각이상 사용자, #청각장애 사용자, #인지장애 사용자, #시각장애 사용자

   
### 명확한 지시사항 제공   
**관련 지침 : 지시사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.**   
특정 요소를 가리키거나 지시사항을 전달하는 콘텐츠에 한정해 적용하는 것으로, 콘텐츠의 사용에 필요한 지시사항을 시각이나 청각 등과 같은 특정한 단일 감각에만 의존하는 방법으로 제공해서는 안 된다는 것이다. 즉, 여러 가지 다른 감각을 통해서도 지시사항을 인식하는 데 문제가 없도록 콘텐츠를 제공해야 한다. 텍스트 콘텐츠(대체 텍스트 포함)는 보조기술을 통해 다른 감각으로의 변환이 가능하기 때문에 텍스트 지시사항에는 추가적인 음성 콘텐츠를 제공할 필요가 없다.    


🔗 관련 WCAG 2.2 성공 기준    
[1.3.3 감각적 특성 (Level A)](https://www.w3.org/TR/WCAG22/#sensory-characteristics){: target="_blank"}    
[WAI - Understanding Sensory Characteristics](https://www.w3.org/WAI/WCAG22/Understanding/sensory-characteristics.html){: target="_blank"}      
[MDN - Accessible Rich Internet Applications (ARIA)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA){: target="_blank"}    

- 색, 크기, 모양 또는 위치와 같은 정보에 대한 인식: 웹 콘텐츠는 콘텐츠에 접근하는 사용자들이 색, 크기, 모양 또는 위치에 관한 정보를 인식하지 못하더라도 원하는 콘텐츠에 접근할 수 있도록 제작해야 한다.    
  예를 들어, 특정 요소를 ‘동그란 버튼을 누르시오’ 또는 ‘오른쪽 버튼을 누르시오’라고 가리킬 때, 그 대상이 되는 버튼이 ‘동그란 버튼’ 또는 ‘오른쪽 버튼’이라는 대체 텍스트를 포함하고 있지 않을 경우, 시각장애를 지닌 사용자는 어떤 요소를 지칭하는지 알 수 없다. 따라서 이러한 경우, 가리키고자 하는 요소의 실제 명칭이나 그 요소가 포함하고 있는 대체 텍스트를 사용해 지칭하거나, 불가피하게 색, 크기, 모양, 위치와 같은 정보를 사용해 특정 요소를 가리킬 때는 이를 보완할 수 있는 다른 감각을 이용하는 정보를 제공해야 한다.      
- 음성이나 음향 정보의 인식: 사용자에게 음성이나 음향을 사용해 지시사항을 전달하는 경우, 사용자가 소리를 들을 수 없더라도 전달하고자 하는 지시사항을 인식할 수 있어야 한다.     
  예를 들어, 온라인 시험 진행 중 사용자에게 비프음으로 정답인지 오답인지를 사용자에게 알려주면, 청각장애 사용자나 스피커가 설치되어 있지 않은 환경에 있는 사용자는 정답과 오답 여부를 확인할 수 없다. 이 경우, 비프음과 함께 정답과 오답 여부를 시각적으로 확인할 수 있는 수단을 제공하면 더 많은 사용자가 지시사항을 인지할 수 있다. 


**기대효과**   

- 시각장애인은 콘텐츠의 모양이나 위치에 의한 정보를 이해할 수 없기 때문에, 추가적인 정보를 제공하는 경우 콘텐츠를 이용할 수 있다.     


#### 1. 필요성        
사용자에게 제공되는 지시사항은 특정 감각(색, 소리, 위치 등)에만 의존해서는 안 됩니다. 시각·청각·인지에 의존하지 않고도 정보나 조작 방법을 이해할 수 있도록 **텍스트로 명확히 전달**해야 합니다.    


- 색상, 모양 등은 모든 사용자가 동일하게 인지할 수 없음    
- 색각 이상, 청각장애, 인지장애 사용자 등은 특정 감각에 의존한 지시를 이해하기 어려움    
- 텍스트 기반의 설명 제공은 모든 사용자에게 공통된 인식 수단 제공    


#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 색각이상 사용자     | 색으로만 구분 시 인식 불가  
| 청각장애 사용자     | 소리로만 지시 시 정보 손실 발생  
| 인지장애 사용자     | 위치 기반, 모양 기반 지시 이해 어려움  
| 시각장애 사용자     | 시각적 단서만으로 정보 전달 시 접근 불가  


#### 3. 체크리스트       

- “빨간 버튼을 누르세요” → “제출 버튼(빨간색)을 누르세요”처럼 텍스트로도 설명되는가?   
- “오른쪽 버튼을 클릭하세요” 같은 방향 지시만 있는가?   
- 색, 위치, 소리 외에도 **텍스트·아이콘·라벨 등으로 설명**이 제공되는가?   
- 여러 요소가 함께 있을 경우, 고유한 이름 또는 라벨로 식별 가능한가?   

#### 4. 테스트 방법      

- 색상·소리·위치 지시만으로 조작 가능한지 테스트    
- 텍스트나 라벨 없이도 조작 요소 식별 가능한지 확인    
- 스크린 리더 등 보조기술에서 명확한 설명 제공 여부 확인    

#### 5. QA 지표       

- 색상만을 사용한 지시 문구 비율    
- 방향 또는 모양만으로 지시하는 경우의 수    
- 텍스트 기반 설명 포함률    

#### 6. 개발방법     

#### HTML 예시 – 색상 외 텍스트 지시
```html
<p>제출하려면 '제출' 버튼(빨간색)을 누르세요.</p>
<button type="submit" style="background:red;">제출</button>
```

#### 잘못된 예시 – 색상만으로 지시
```html
<p>빨간 버튼을 누르세요.</p>
<!-- 텍스트나 라벨이 없어 스크린 리더 사용자가 알 수 없음 -->
```

#### Vue 예시
```vue
<template>
  <p>오른쪽에 있는 ‘삭제’ 버튼을 누르세요.</p>
  <button @click="removeItem" aria-label="삭제">삭제</button>
</template>

<script setup>
function removeItem() {
  alert('삭제 완료');
}
</script>
```

#### React 예시
```jsx
function ActionHint() {
  return (
    <>
      <p>'제출' 버튼을 클릭하세요 (녹색 배경).</p>
      <button style={{ backgroundColor: 'green' }} aria-label="제출">제출</button>
    </>
  );
}
```

#### 7. 점검 기준     

- 색, 모양, 위치, 소리에만 의존한 지시가 있는가?    
- 텍스트와 라벨을 통한 추가 설명이 있는가?    
- 보조기술로도 의미를 파악할 수 있는가?    

#### 8. 점검 방법     

- 코드 내 지시사항이 색, 위치, 소리만으로 전달되는지 확인    
- 사용자 설명 문구에 식별 가능한 텍스트가 포함되어 있는지 확인    
- 스크린 리더 테스트를 통해 지시사항 이해 가능성 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-labels-or-instructions01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<p>‘다음’ 버튼(파란색)을 누르세요.</p>
<button style="background:blue;">다음</button>
```

#### 10. 미준수 사례       

```html
<p>파란색 버튼을 누르세요.</p>
<!-- 색으로만 지시됨 → 색각이상 사용자 등에게 인식 불가 -->
```



#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/T70ZKfY78Lo?si=Si0tEn0MV36oyaLy" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (명확한 지시사항 제공)](https://www.youtube.com/embed/T70ZKfY78Lo?si=Si0tEn0MV36oyaLy){: target="_blank"}    
   
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
