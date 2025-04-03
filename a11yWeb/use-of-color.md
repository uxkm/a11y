# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    

**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #색각이상 사용자, #저시력 사용자, #인지장애 사용자

   
### 색에 무관한 콘텐츠 인식   
**관련 지침 : 콘텐츠는 색에 관계없이 인식될 수 있어야 한다.**   
콘텐츠에서 제공하는 모든 정보는 특정한 색을 구별할 수 없는 사용자, 흑백 디스플레이 사용자, 흑백 인쇄물을 보는 사용자 및 고대비 모드 사용자가 인식할 수 있도록 제공해야 한다.    

🔗 관련 WCAG 2.2 성공 기준  
[1.4.1 색에 의존하지 않음 (Use of Color) (Level A)](https://www.w3.org/TR/WCAG22/#use-of-color){: target="_blank"}    
[WAI - Understanding Use of Color](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html){: target="_blank"}      
[MDN - 색상 접근성](https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_Colors_and_Luminance){: target="_blank"}    


- 색에 의한 정보 표현 방지: 차트나 그래프 등을 고대비 모드로 화면에 표시하면 모든 색이 단색(회색조)으로 표시되어 사용자가 색을 구분하지 못하는 경우가 발생한다. 따라서 사용자가 경조 모드에서도 콘텐츠를 인식할 수 있도록 색만을 이용하여 정보를 제공하지 않아야 한다. 즉, 색은 시각적인 강조를 위해서만 사용해야 한다.    
- 무늬를 이용한 정보 제공: 서로 다른 정보를 무늬로 구분하여 표시하면 경조 모드 사용자, 단색 디스플레이 사용자, 흑백 인쇄물의 사용자도 정보를 충분히 구분할 수 있다. 무늬와 색을 동시에 이용한 콘텐츠는 색각장애가 있는 사용자도 접근이 가능하다.     

**기대효과**   

- 색의 차이가 정보의 다름을 나타내지 않으므로, 색을 인지하는 데 장애가 있는 사용자도 혼동을 일으킬 염려가 없게 된다.    
- 흑백 스크린(구형 PDA 등) 또는 고대비 모드 사용자도 콘텐츠의 내용이나 구조를 손쉽게 이해할 수 있다.   


#### 1. 필요성        
정보 전달이나 조작을 색상에만 의존해서는 안 되며, 색을 구분하지 못하는 사용자도 **텍스트, 패턴, 라벨 등 다른 방법으로 정보를 인식할 수 있도록** 제공해야 합니다.   

- 색각이상 또는 흑백 디스플레이 사용자는 색상만으로는 정보를 구분할 수 없음    
- 중요 정보나 동작 안내가 색상에만 의존하면 **접근성 불가**    
- 보조 지표(텍스트, 기호 등) 제공은 인지와 접근성을 향상시킴    

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 색각이상 사용자     | 빨강/초록, 파랑/보라 등 색 구분 어려움  
| 저시력 사용자       | 대비가 낮을 경우 색 인식 어려움  
| 인지장애 사용자     | 색으로만 지시 시 이해 어려움  

#### 3. 체크리스트       

- 색상 외에도 텍스트, 아이콘, 테두리, 패턴 등 보조 수단이 있는가?   
- 색으로만 구분되는 요소(예: 버튼 상태, 오류 메시지 등)가 있는가?   
- 색상이 구분되지 않아도 동일한 정보가 제공되는가?   

#### 4. 테스트 방법      

- 화면을 흑백 모드로 전환하여 테스트    
- 색맹 시뮬레이션 도구(Color Oracle 등) 사용    
- 텍스트 또는 아이콘이 함께 제공되는지 확인    

#### 5. QA 지표       

- 색상 단독 정보 전달 비율   
- 색각 시뮬레이션에서 정보 구분 가능률   
- 비색상 사용자 대상 정보 이해 가능성    

#### 6. 개발방법     

#### HTML 예시 – 색상 + 텍스트 보조 제공
```html
<p><strong style="color:red;">오류:</strong> 비밀번호가 일치하지 않습니다.</p>
```

#### 잘못된 예시 – 색상만 강조
```html
<p style="color:red;">비밀번호가 일치하지 않습니다.</p>
```

#### Vue 예시
```vue
<template>
  <div :class="{ error: isError }">
    <span class="error-icon" aria-hidden="true">⚠</span>
    <span>{{ errorMessage }}</span>
  </div>
</template>

<script setup>
const isError = true;
const errorMessage = '입력 오류: 비밀번호가 일치하지 않습니다.';
</script>
```

#### React 예시
```jsx
function ErrorNotice({ message }) {
  return (
    <div className="error">
      <span aria-hidden="true">⚠</span>
      <span>{message}</span>
    </div>
  );
}
```


#### 7. 점검 기준     

- 색상 외에도 다른 수단으로 정보 전달이 이루어지는가?    
- 시각적 정보가 색상 외에도 인식 가능한가?    
- UI 상태 변화(활성/비활성 등)가 색상 외 수단으로도 구분 가능한가?    

#### 8. 점검 방법     

- 색맹 시뮬레이션 도구 사용    
- 텍스트, 아이콘, 테두리 등 시각 외 정보 전달 확인    
- 흑백 프린트에서도 정보 전달 가능한지 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-use-of-color01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<p><span class="status success">성공</span></p>
<p><span class="status error">실패</span></p>
<!-- 텍스트와 클래스 분리로 색상 외 인식 가능 -->
```

#### 10. 미준수 사례       

```html
<p style="color:green;">성공</p>
<p style="color:red;">실패</p>
<!-- 색상 외 텍스트 구분 없음 -->
```


#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/VkKda38UDJ0?si=r2QdOMeQxhJb1kae" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (색에 무관한 콘텐츠 인식)](https://www.youtube.com/embed/VkKda38UDJ0?si=r2QdOMeQxhJb1kae){: target="_blank"}    
   
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
