# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    

**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #인지장애 사용자, #모든 사용자

   
### 표의 구성   
**관련 지침 : 표는 이해하기 쉽게 구성해야 한다.**   
표를 제공할 경우, 표의 이해를 돕기 위한 내용 및 구조에 대한 정보를 제공해야 한다.     

🔗 관련 WCAG 2.2 성공 기준    
[1.3.1 정보 및 관계 (Level A)](https://www.w3.org/TR/WCAG22/#info-and-relationships){: target="_blank"}    
[WAI - Understanding Info and Relationships](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships.html){: target="_blank"}      
[MDN - <table> 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/table){: target="_blank"}    

- 표 정보 제공: 데이터를 표로 구성할 경우, 표의 내용, 구조 등을 이해할 수 있는 정보를 제공하여 표의 이용 방법을 예측할 수 있도록 해야 한다.     
- 표의 구성: 표의 내비게이션을 위하여, 표의 셀은 제목 셀과 데이터 셀이 구분되도록 구성해야 한다.    

**기대효과**   

- 제목 셀과 데이터 셀이 구분되도록 구현한 데이터 테이블은 시각장애인에게 데이터 셀에 대한 제목 셀의 내용 또는 제목 셀과의 관계를 알려주므로 내용을 파악하기 쉽다.    


#### 1. 필요성        
표는 데이터를 구조적으로 제공하는 도구로, **적절한 헤더(th)**, **범위 지정(scope)**, **캡션(caption)** 등을 통해 스크린 리더 사용자와 모든 사용자에게 정보를 명확히 전달해야 합니다. 특히 복잡한 표일수록 시각뿐 아니라 논리적으로 구조화되어 있어야 합니다.   

- 시각적으로만 구조화된 표는 스크린 리더 사용자가 이해할 수 없음    
- 캡션, 헤더 정보, 셀 간 관계를 명확하게 제공해야 정보 전달이 가능    
- 복잡한 표일수록 헤더와 데이터의 관계를 기술적으로 설명할 필요 있음    

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 스크린 리더가 헤더-셀 관계를 정확히 안내해야 이해 가능  
| 인지장애 사용자     | 데이터가 잘 정리되어야 의미를 파악하기 쉬움  
| 모든 사용자         | 구조적 정보는 사용성과 가독성을 높임  

#### 3. 체크리스트       

- `<caption>` 요소로 표 제목이 명확히 설명되었는가?    
- `<th>`를 사용해 머리글 셀이 정의되어 있는가?    
- `scope="col"` 또는 `scope="row"`를 통해 헤더의 범위가 명시되었는가?    
- 복잡한 표의 경우 `headers`, `id` 속성을 활용하여 관계를 정의했는가?    

#### 4. 테스트 방법      

- 스크린 리더로 표 탐색 시 헤더-셀 관계 안내 여부 확인    
- `<caption>`, `<th>`, `scope` 사용 여부 확인   
- 복잡한 경우 `headers`, `id` 속성 관계 매핑 확인   

#### 5. QA 지표       

- 헤더 정의 비율 (표 내 `<th>` 포함률)   
- 범위 지정 비율 (`scope` 속성 사용률)   
- 스크린 리더에서 헤더-셀 관계 해석 정확도    

#### 6. 개발방법     

#### HTML 예시 – 단순 표
```html
<table>
  <caption>월별 판매량</caption>
  <thead>
    <tr>
      <th scope="col">월</th>
      <th scope="col">판매량</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1월</th>
      <td>1,000</td>
    </tr>
    <tr>
      <th scope="row">2월</th>
      <td>1,200</td>
    </tr>
  </tbody>
</table>
```

#### Vue 예시
```vue
<template>
  <table>
    <caption>사용자 목록</caption>
    <thead>
      <tr>
        <th scope="col">이름</th>
        <th scope="col">이메일</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="user in users" :key="user.id">
        <th scope="row">{{ user.name }}</th>
        <td>{{ user.email }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
const users = [
  { id: 1, name: '홍길동', email: 'hong@example.com' },
  { id: 2, name: '김영희', email: 'kim@example.com' }
];
</script>
```

#### React 예시
```jsx
function UserTable({ users }) {
  return (
    <table>
      <caption>사용자 목록</caption>
      <thead>
        <tr>
          <th scope="col">이름</th>
          <th scope="col">이메일</th>
        </tr>
      </thead>
      <tbody>
        {users.map(user => (
          <tr key={user.id}>
            <th scope="row">{user.name}</th>
            <td>{user.email}</td>
          </tr>
        ))}
      </tbody>
    </table>
  );
}
```

#### 7. 점검 기준     

- 모든 표에 `<th>` 및 `scope` 속성이 포함되어 있는가?   
- 표 제목이 `<caption>` 또는 시각적으로 설명되어 있는가?   
- 데이터 셀과 헤더의 관계가 기술적으로 연결되었는가?   

#### 8. 점검 방법     

- 코드 내 `<table>` 구성 요소 확인    
- 스크린 리더로 표 읽기 시 헤더-셀 연결 확인   
- 시멘틱 마크업 존재 여부 및 scope 속성 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-table01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<th scope="col">제품명</th>
<th scope="row">3월</th>
```

#### 10. 미준수 사례       

```html
<td><b>제품명</b></td>
<!-- 헤더에 <th> 대신 <td> 사용 -->
```


#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/2rx3gWdMSHA?si=9bNzsqWijd6PuIqu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (표의 구성)](https://www.youtube.com/embed/2rx3gWdMSHA?si=9bNzsqWijd6PuIqu){: target="_blank"}    
   
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
