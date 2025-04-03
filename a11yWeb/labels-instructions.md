# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #인지장애인, #고령자


### 레이블 제공 
**관련 지침 : 사용자 입력에는 대응하는 레이블을 제공해야 한다.**   
사용자 입력 근처에 사용법을 알려주는 레이블을 보조기술이 알 수 있도록 해당 콘트롤과 대응하여 제공해야 한다. 레이블과 사용자 입력 간의 관계를 보조기술이 인식할 수 있도록 대응시키지 않고 단순히 텍스트로만 제공할 경우, 보조기술은 해당 사용자 입력에 대한 레이블을 인식할 수 없다.     

[WCAG 2.2 - 3.3.2 레이블 또는 지시사항 (Level A)](https://www.w3.org/TR/WCAG22/#labels-or-instructions){: target="_blank"}    

- 성공 기준 3.3.2 (레벨 A)​ : 요구 사항 : 각 입력 필드에 대해 레이블이나 지시사항을 제공해야 합니다. 이를 통해 사용자는 해당 필드에 어떤 정보를 입력해야 하는지 명확하게 알 수 있습니다.      

**기대효과**   

- 레이블과 사용자 입력 간의 관계를 보조기술이 인식할 수 있도록 대응시키면 화면낭독프로그램을 사용하는 시각장애인에게 해당 콘트롤이 어떤 용도로 사용되는지를 알려줄 수 있으므로 잘못된 데이터의 입력을 방지할 수 있다.     


#### 1. 필요성        
입력 필드나 양식 구성 요소는 시각적으로 식별 가능한 레이블뿐 아니라, 보조 기술 사용자에게도 인식될 수 있는 시멘틱한 레이블을 제공해야 합니다. 레이블 제공은 정보 전달과 오류 방지를 위한 중요한 접근성 항목입니다.    

- **입력 목적의 명확화**: 사용자에게 어떤 정보를 입력해야 하는지 정확히 알려줌   
- **보조기술 호환성 보장**: 스크린 리더 사용자도 필드의 의미를 알 수 있음   
- **오류 감소**: 입력 오류나 혼동을 줄이고 효율적인 데이터 수집 가능   

#### 2. 대상       

| 사용자 유형   | 이유 |
|---------------|------|
| 시각장애인 | 스크린 리더를 통해 필드의 이름을 듣고 이해함 |
| 인지장애인 | 텍스트 안내로 어떤 정보를 입력해야 하는지 명확히 인지 가능 |
| 고령자 | 시각적 안내 부족 시 혼란을 줄 수 있음 |


#### 3. 체크리스트       

- `label` 요소가 입력 필드와 연결되어 있는가? (`for="id"` 와 `id=""` 매칭)    
- 시각적으로 레이블이 없을 경우, `aria-label` 또는 `aria-labelledby` 제공 여부     
- `placeholder`만으로 레이블을 대체하지 않았는가?     
- 레이블은 구체적이며 명확한가?     


#### 4. 테스트 방법      

- **스크린 리더(NVDA, JAWS 등)**로 입력 필드에 접근하여 필드명이 올바르게 출력되는지 확인     
- **개발자 도구**의 접근성 트리 또는 name role value 확인     
- 키보드만으로 입력 필드 탐색 시 레이블이 읽히는지 확인    


#### 5. QA 지표       

- 명시적 레이블 제공 비율    
- `aria-label`, `aria-labelledby` 활용률    
- 스크린 리더 레이블 출력 성공률    


#### 6. 개발방법     


#### ✅ HTML 예시 – 올바른 레이블 제공
```html
<label for="email">이메일 주소</label>
<input type="email" id="email" name="email" />
```

#### ❌ 잘못된 예시 – 레이블 없이 placeholder만 사용
```html
<input type="text" placeholder="이메일을 입력하세요" />
```

#### ✅ ARIA 사용 예시
```html
<input type="text" aria-label="이름" />
```

#### ✅ Vue 예시
```vue
<template>
  <label for="username">사용자 이름</label>
  <input id="username" v-model="username" type="text" />
</template>

<script setup>
import { ref } from 'vue';
const username = ref('');
</script>
```

#### ✅ React 예시
```jsx
function NameInput() {
  const [name, setName] = React.useState('');
  return (
    <>
      <label htmlFor="name">이름</label>
      <input
        id="name"
        type="text"
        value={name}
        onChange={e => setName(e.target.value)}
      />
    </>
  );
}
```


#### 7. 점검 기준     

- 모든 입력 요소에 레이블이 존재하는가?     
- 스크린 리더가 해당 레이블을 정확히 읽어주는가?    
- `for` 속성과 `id` 속성의 연결이 일치하는가?   


#### 8. 점검 방법     

- 크롬 요소검사 및 접근성 탭에서 필드의 name 확인   
- 스크린 리더 테스트: 각 입력 필드에 포커스를 줄 때 적절한 이름이 들리는지 확인    
- 자동화 도구(Lighthouse, Axe 등)에서 레이블 누락 경고 유무 확인    


#### 9. 준수 사례       

```html
<label for="password">비밀번호</label>
<input type="password" id="password" />
```


#### 10. 미준수 사례       

```html
<input type="password" placeholder="비밀번호" />
<!-- 시각적으로는 안내되나 보조기술로는 인식 불가 -->
```


#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/MnvmNx0q1Qw?si=MDUnFh_j-diTF9F9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (레이블 제공)](https://www.youtube.com/embed/MnvmNx0q1Qw?si=MDUnFh_j-diTF9F9){: target="_blank"}    
   
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
