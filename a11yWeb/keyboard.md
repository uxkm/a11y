# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #지체장애인, #파워 유저 및 개발자


### 키보드 사용 보장 
**관련 지침 : 모든 기능은 키보드만으로도 사용할 수 있어야 한다.**   
웹 페이지에서 제공하는 모든 기능은 키보드만으로도 사용할 수 있도록 제공해야 한다.     

🔗 관련 WCAG 2.2 성공 기준    
[2.1.1 키보드 (Keyboard) (Level A)](https://www.w3.org/TR/WCAG22/#keyboard){: target="_blank"}    
[2.4.7 포커스 표시 (Focus Visible) (Level AA)](https://www.w3.org/TR/WCAG22/#focus-visible){: target="_blank"}    
[WAI - Understanding Keyboard](https://www.w3.org/WAI/WCAG22/Understanding/keyboard.html){: target="_blank"}      
[MDN - Keyboard accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Keyboard-navigable_JavaScript_widgets){: target="_blank"}    

**본 검사항목의 예외**   

- 키보드 인터페이스와 기능: 콘텐츠의 모든 기능은 키보드로 사용이 가능해야 한다. 이 경우, 해당 기능을 사용하는 데 필요한 키보드의 조작 횟수의 많고 적음은 고려대상이 아니다.     
- 예외 콘텐츠: 위치 지정 도구의 커서 궤적이 중요한 역할을 하는 콘텐츠(붓질 기능이 필요한 콘텐츠, 시뮬레이션 콘텐츠, 지리정보 응용 콘텐츠, 가상현실 콘텐츠 등), 움직임 측정 센서를 이용하는 콘텐츠는 본 검사항목의 예외 콘텐츠로 간주한다. 그러나 예외 콘텐츠의 경우에도 위치 지정 도구나 움직임 측정 센서를 이용하는 기능을 제외한 나머지 사용자 인터페이스는 키보드만으로도 사용할 수 있어야 한다.    


**기대효과**   

- 위치 지정 도구를 사용할 수 없는 시각장애인의 경우, 키보드만으로도 웹 콘텐츠나 웹사이트가 제공하는 모든 기능을 사용할 수 있다.    
- 전통적인 키보드를 사용할 수 없는 지체장애인의 경우, 키보드 대신 음성 입력장치를 이용하더라도 웹 콘텐츠가 제공하는 모든 기능을 사용할 수 있다.   

#### 1. 필요성        
마우스를 사용할 수 없는 사용자도 모든 기능을 **Tab, 화살표 키, Enter, Space, ESC 등 키보드만으로 조작 가능**하도록 구현되어야 합니다. 포커스 이동, 콘텐츠 탐색, 메뉴/탭 조작 등이 키보드 기반으로 가능해야 하며, **시각적 포커스 표시도 반드시 제공**되어야 합니다.    


- 시각장애인, 지체 장애인, 고령 사용자 등 마우스 사용이 어려운 사용자 고려   
- 포커스 이동만으로 웹 페이지 전체 기능 접근 가능해야 함   
- 키보드 기반 보조기술과 호환성을 확보   

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 스크린 리더와 키보드 병행 사용  
| 지체장애인         | 손떨림/장애로 마우스 조작 불가  
| 파워 유저 및 개발자 | 키보드 단축키 활용  

#### 3. 체크리스트       

- 모든 인터랙션이 Tab, Enter, Space 등으로 작동 가능한가?    
- 포커스가 논리적이고 순차적으로 이동하는가?    
- 포커스된 요소가 시각적으로 구분 가능한가?    
- 화살표 키로 이동하는 메뉴/탭/콤보박스가 키보드 동작 가능한가?    

#### 4. 테스트 방법      

- 마우스를 사용하지 않고 Tab 키만으로 모든 요소 탐색    
- Enter, Space, ESC, 화살표 키로 조작 가능한지 확인    
- 포커스가 논리적이고 빠짐없이 이동하는지 체크    

#### 5. QA 지표       

- 키보드 접근 가능 영역 비율   
- Tab 포커스 누락 요소 수   
- 포커스 스타일 명확도   

#### 6. 개발방법     

#### HTML 예시 – 네비게이션 2Depth + 탭메뉴 구성
```html
<nav>
  <ul>
    <li><a href="#home">홈</a></li>
    <li>
      <button aria-expanded="false" aria-controls="menu1">서비스</button>
      <ul id="menu1" hidden>
        <li><a href="#service1">서비스 소개</a></li>
        <li><a href="#service2">요금 안내</a></li>
      </ul>
    </li>
  </ul>
</nav>

<div role="tablist" aria-label="서비스 탭">
  <button role="tab" aria-selected="true" aria-controls="tab1" id="t1">서비스 안내</button>
  <button role="tab" aria-selected="false" aria-controls="tab2" id="t2">이용 후기</button>

  <div role="tabpanel" id="tab1" aria-labelledby="t1">내용 1</div>
  <div role="tabpanel" id="tab2" aria-labelledby="t2" hidden>내용 2</div>
</div>
```

#### Vue 예시 – 키보드 전용 탭 메뉴
```vue
<template>
  <div role="tablist" aria-label="FAQ">
    <button
      v-for="(tab, index) in tabs"
      :key="tab.id"
      role="tab"
      :aria-selected="index === current"
      :tabindex="index === current ? 0 : -1"
      @click="select(index)"
      @keydown.arrow-right="select((current + 1) % tabs.length)"
      @keydown.arrow-left="select((current - 1 + tabs.length) % tabs.length)"
    >
      {{ tab.label }}
    </button>
    <div
      v-for="(tab, index) in tabs"
      v-show="index === current"
      :key="tab.id"
      role="tabpanel"
    >
      {{ tab.content }}
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const current = ref(0);
const tabs = ref([
  { id: 'faq1', label: '문의 방법', content: '이메일 문의 가능' },
  { id: 'faq2', label: '환불 정책', content: '결제일로부터 7일 이내' }
]);

function select(index) {
  current.value = index;
}
</script>
```

#### React 예시 – 키보드 내비게이션 포함
```jsx
import { useState } from 'react';

function TabMenu() {
  const [current, setCurrent] = useState(0);
  const tabs = [
    { label: '공지', content: '공지사항 내용' },
    { label: '이벤트', content: '이벤트 안내' }
  ];

  return (
    <div role="tablist" aria-label="정보 탭">
      {tabs.map((tab, index) => (
        <button
          key={index}
          role="tab"
          aria-selected={index === current}
          onClick={() => setCurrent(index)}
          onKeyDown={(e) => {
            if (e.key === 'ArrowRight') setCurrent((index + 1) % tabs.length);
            if (e.key === 'ArrowLeft') setCurrent((index - 1 + tabs.length) % tabs.length);
          }}
        >
          {tab.label}
        </button>
      ))}
      <div role="tabpanel">{tabs[current].content}</div>
    </div>
  );
}
```

#### 7. 점검 기준     

- 모든 기능이 마우스 없이 사용 가능한가?   
- 포커스가 빠지거나 막히는 구간은 없는가?   
- 인터페이스 컨트롤이 키보드로도 활성화되는가?   

#### 8. 점검 방법     

- 키보드만으로 전체 UI 탐색/조작   
- Tab 순서와 논리 구조 확인   
- 버튼/링크/입력/탭/메뉴 등 키보드 작동 여부 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-keyboard01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<button onclick="alert('확인')">확인</button>
```

#### 10. 미준수 사례       

```html
<div onclick="alert('클릭')">확인</div>
<!-- 키보드 포커스 불가, 클릭만 가능 -->
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/UI9dWJJnC5k?si=ZQF1tXC1feYlu0gR" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (키보드 사용 보장)](https://www.youtube.com/embed/UI9dWJJnC5k?si=ZQF1tXC1feYlu0gR){: target="_blank"}    
   
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
