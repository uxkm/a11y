# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #키보드 사용자, #스크린 리더 사용자, #인지장애 사용자


### 조작 가능 
**관련 지침 : 사용자 입력 및 콘트롤은 조작 가능하도록 제공되어야 한다.**   
웹 페이지에서 제공하는 모든 이웃한 콘트롤은 개별적으로 선택하고 사용할 수 있도록 충분한 크기로 제공해야 한다.     

[2.1.1 키보드 (Keyboard)](https://www.w3.org/TR/WCAG22/#keyboard){: target="_blank"}    
[3.3.2 레이블 또는 지시사항 (Labels or Instructions)](https://www.w3.org/TR/WCAG22/#labels-or-instructions){: target="_blank"}      
[4.1.2 이름, 역할, 값 (Name, Role, Value)](https://www.w3.org/TR/WCAG22/#name-role-value){: target="_blank"}    
[MDN - Input 요소 접근성](https://developer.mozilla.org/ko/docs/Web/Accessibility/ARIA/Roles/Input_role){: target="_blank"}    

- 콘트롤의 크기: 콘텐츠에 포함된 모든 콘트롤은 대각선 방향의 길이를 6.0mm 이상으로 제공하는 것이 바람직하다.    
- 링크, 사용자 입력, 기타 콘트롤 등의 안쪽 여백: 링크, 사용자 입력 및 기타 콘트롤은 테두리 안쪽으로 1픽셀 이상의 여백을 두고, 그곳에서는 위치 지정 도구의 조작에 반응하지 않도록 구현하는 것이 바람직하다.     

**기대효과**   

-  콘트롤을 크게 구현하면 터치스크린을 채용한 기기를 이용하는 손 떨림이 있는 사용자와 시각장애인도 콘트롤을 용이하게 찾아서 조작할 수 있다.    

#### 1. 필요성        
사용자가 양식 입력, 버튼 클릭, 탭 전환 등 기능을 조작할 수 있도록 모든 UI 요소는 **키보드, 스크린 리더 등 보조기술로도 작동할 수 있어야 하며**, 잘못된 입력에 대한 안내와 피드백도 포함해야 합니다.   

- 사용자 입력 필드 및 UI 컴포넌트가 비조작 상태이면 사용자 경험 단절   
- 장애 사용자도 키보드/음성 명령 등으로 모든 기능 접근 가능해야 함   
- 올바른 구조 제공 시 보조기술의 호환성이 보장됨   

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 키보드 사용자       | 포커스 이동 및 입력 필수  
| 스크린 리더 사용자  | 요소의 역할과 상태 인지 필요  
| 인지장애 사용자     | 지시사항과 피드백 제공 필수  

#### 3. 체크리스트       

- 버튼, 입력 필드 등 모든 컨트롤이 조작 가능한가?   
- 입력 필드에 적절한 label 또는 aria-label이 있는가?   
- 동적 UI 요소에 name/role/value가 명확히 제공되는가?   
- 포커스 가능하고 동작 확인 가능한가?   

#### 4. 테스트 방법      

- 키보드로 Tab 이동하여 컨트롤 요소 접근   
- 스크린 리더로 컨트롤의 이름/역할/값이 읽히는지 확인   
- 입력/전송 후 피드백 메시지 확인   

#### 5. QA 지표       

- 조작 불가능한 UI 요소 수   
- 레이블 누락 항목 비율   
- 조작 시 오류 피드백 유무   

#### 6. 개발방법     

#### HTML 예시 – label, button, input
```html
<label for="email">이메일</label>
<input id="email" type="email" aria-required="true" />

<button type="submit">제출</button>
```

#### ❌ 잘못된 예시 – 레이블 없음, div로 버튼 구현
```html
<div onclick="submit()">제출</div>
<input type="email" placeholder="이메일 입력">
<!-- label 없음 -->
```

#### Vue 예시
```vue
<template>
  <label for="name">이름</label>
  <input id="name" v-model="username" />

  <button @click="submit">제출</button>
</template>

<script setup>
import { ref } from 'vue';
const username = ref('');
function submit() {
  alert(`${username.value}님, 제출되었습니다.`);
}
</script>
```

#### React 예시
```jsx
function Form() {
  const [email, setEmail] = React.useState('');

  return (
    <form>
      <label htmlFor="email">이메일</label>
      <input
        id="email"
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        aria-required="true"
      />
      <button type="submit">제출</button>
    </form>
  );
}
```

#### 7. 점검 기준     

- 입력 및 조작 가능한 UI 요소가 키보드, 보조기술에서도 작동하는가?     
- 명확한 label, 역할(name), 상태(value)가 정의되어 있는가?    

#### 8. 점검 방법     

- 키보드 및 스크린 리더로 컨트롤 요소 조작   
- form 요소 유효성 검사   
- aria 속성 점검 및 작동 상태 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-operable01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<label for="search">검색어</label>
<input id="search" type="text">
<button>검색</button>
```

#### 10. 미준수 사례       

```html
<div onclick="search()">검색</div>
<input type="text" placeholder="검색">
<!-- 역할 명확하지 않음, label 없음 -->
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/y7aF3WgGPl0?si=FXgs6kkwIcLSi1Ia" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (조작 가능)](https://www.youtube.com/embed/y7aF3WgGPl0?si=FXgs6kkwIcLSi1Ia){: target="_blank"}    
   
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
