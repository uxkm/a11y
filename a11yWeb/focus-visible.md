# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #지체 장애 사용자, #인지장애 사용자


### 초점 이동과 표시 
**관련 지침 : 키보드에 의한 초점은 논리적으로 이동해야 하며, 시각적으로 구별할 수 있어야 한다.**   
웹 페이지에서 제공하는 모든 기능을 키보드만으로 사용하는 경우에도 사용자 입력 간의 초점 이동은 적절한 순서를 따라야 하며, 이 과정에서 콘텐츠는 조작이 불가능한 상태가 되거나 갑작스러운 페이지의 전환 등이 일어나지 않아야 한다.    
또한 초점을 받은 콘텐츠는 저시력장애인과 지체장애인이 인지할 수 있도록 시각적으로 구별되어야 한다.     


🔗 관련 WCAG 2.2 성공 기준    
[2.4.3 포커스 순서 (Focus Order) (Level A)](https://www.w3.org/TR/WCAG22/#focus-order){: target="_blank"}        
[2.4.7 포커스 표시 (Focus Visible) (Level AA)](https://www.w3.org/TR/WCAG22/#focus-visible){: target="_blank"}      
[WAI - Understanding Focus](https://www.w3.org/WAI/WCAG22/Understanding/focus-order.html){: target="_blank"}        
[MDN - CSS outline 속성](https://developer.mozilla.org/ko/docs/Web/CSS/outline){: target="_blank"}      

- 초점 이동 순서 유지: 사용자가 키보드를 이용하여 초점을 이동하는 경우 이동 순서가 관례를 벗어나면 사용자에게 혼란을 주기 때문에, 초점 이동 순서는 사용자가 예측하는 이동 순서와 일치해야 한다. 바람직한 방법은 기존의 관례를 따르도록 콘텐츠를 제공하는 것이다. 관례와 달리 초점 이동 순서를 결정해야 하는 경우, 사용자 입력 간의 이동 순서를 논리적으로 구현해야 한다.     
  예를 들어, 사용자 아이디, 비밀번호를 입력하는 입력 창과 로그인 버튼 간의 초점 이동 순서는 사용자 아이디, 비밀번호, 로그인 버튼의 순서이어야 한다.     
- 함정 또는 오류 방지: 웹 콘텐츠는 더 이상 키보드 조작이 불가능한 상태가 되어 다음 사용자 입력 또는 콘트롤 등으로 초점을 이동할 수 없거나 이전 페이지로 초점을 이동할 수 없는 상태가 되지 않도록 구현해야 한다.    
- 초점의 시각화: 사용자 입력 등이 위치 지정 도구(마우스)나 키보드 조작을 통해 초점을 받았을 때, 해당 콘트롤이 초점을 받았음을 시각적으로 구별할 수 있음을 의미한다.     
  대표적인 예로 키보드 조작을 통해 버튼이 초점을 받았을 때, 이 버튼의 주위에 점선의 테두리가 표시되는 것을 들 수 있다. 위치 지정 도구에 의한 초점과 키보드에 의한 초점의 표시 방법이 다른 것도 허용한다. 시각적으로 인식가능한 초점 표시는 시간제한이 없어야 한다.    

**기대효과**   

- 화면낭독프로그램을 이용하는 사용자의 경우, 사용자 입력 주변의 상하좌우에 위치한 콘텐츠에 대한 정보를 알 수 없다. 따라서 웹 콘텐츠를 사용하는 과정에서 키보드 조작에 의한 사용자 입력 간의 이동 순서는 관례를 따라야 한다. 그렇지 않으면 사용자 입력의 조작 과정에서 혼란을 주게 된다.     
- 마우스나 키보드 조작을 통해 특정 영역으로 콘트롤을 이동하였을 경우 해당 영역이 초점을 받았음을 시각적으로 알려주면 저시력장애인, 고령자, 지체장애인뿐만 아니라 비장애인들도 현재 초점이 어느 콘트롤에 위치하고 있는지 확인가능하고 콘트롤의 기능을 활성화시킬 수 있는지 쉽게 인지할 수 있다.    


#### 1. 필요성        
키보드로 웹 페이지를 탐색할 때, 포커스가 **논리적인 순서로 이동**하고, 사용자가 현재 위치를 **시각적으로 인지할 수 있도록 표시(Outline 등)** 되어야 합니다. 포커스가 보이지 않거나, 순서가 뒤섞이면 혼란을 초래할 수 있습니다.     

- 시각장애 사용자 및 키보드 전용 사용자는 포커스만으로 위치 파악    
- 포커스 순서가 엉킬 경우 기능 사용 불가    
- 포커스 시각화는 정보 인지와 조작 상태 인식을 도와줌    

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 스크린 리더와 포커스 탐색 병행  
| 지체 장애 사용자     | 키보드 전용 조작  
| 인지장애 사용자     | 시각적 피드백이 필요  

#### 3. 체크리스트       

- Tab 키로 요소를 탐색할 때 논리적 순서로 이동하는가?   
- 현재 포커스된 요소가 시각적으로 구분 가능한가?   
- 포커스 outline 제거 없이 사용자 정의 스타일을 제공하는가?   
- JavaScript로 강제 초점 이동 시에도 자연스럽게 이동하는가?   

#### 4. 테스트 방법      

- Tab 키만으로 전체 페이지 탐색    
- 포커스 시각적 표시(outline, border 등) 확인    
- 스크린 리더 사용자 테스트로 초점 이동 및 탐색 확인    


#### 5. QA 지표       

- 포커스 outline 누락 비율   
- 포커스 시각화 누락 영역 수   
- Tab 순서 오류 발생률   

#### 6. 개발방법     

#### HTML 예시 – 포커스 스타일 제공
```html
<a href="#main" class="skip-link">본문 바로가기</a>

<style>
.skip-link:focus {
  outline: 3px solid #333;
  background: yellow;
  position: absolute;
  top: 0;
  left: 0;
}
</style>
```

#### 잘못된 예시 – 포커스 스타일 제거
```css
*:focus {
  outline: none;
}
```

#### Vue 예시 – 사용자 정의 포커스 스타일
```vue
<template>
  <button class="focus-btn">확인</button>
</template>

<style scoped>
.focus-btn:focus {
  outline: 3px solid #2a8;
  box-shadow: 0 0 0 3px #ccf;
}
</style>
```

#### React 예시 – 논리적 포커스 순서
```jsx
function LoginForm() {
  return (
    <>
      <label htmlFor="email">이메일</label>
      <input id="email" type="email" />

      <label htmlFor="pw">비밀번호</label>
      <input id="pw" type="password" />

      <button type="submit">로그인</button>
    </>
  );
}
```

#### 7. 점검 기준     

- 포커스가 논리적인 순서로 이동하는가?    
- 포커스가 시각적으로 명확히 표시되는가?    
- outline 제거 시 대체 스타일이 제공되는가?    

#### 8. 점검 방법     

- 키보드(Tab)만으로 UI 탐색    
- 포커스가 눈에 보이는지 육안으로 확인    
- 요소간 포커스 이동 순서 논리성 점검    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-focus-visible01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```css
button:focus {
  outline: 2px solid #0066cc;
  background-color: #eef;
}
```

#### 10. 미준수 사례       

```css
button:focus {
  outline: none;
}
/* 포커스가 보이지 않아 위치 인식 불가 */
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/b1hALv6l9ck?si=Z95EnyuZ0-JWyHlr" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (초점 이동과 표시)](https://www.youtube.com/embed/b1hALv6l9ck?si=Z95EnyuZ0-JWyHlr){: target="_blank"}    
   
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
