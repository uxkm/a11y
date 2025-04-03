# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #웹 애플리케이션, #보조기술 지원, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #지체 장애인, #시각장애인, #고령자, #인지 장애인     

### 웹 애플리케이션 접근성 준수
**관련 지침 : 콘텐츠에 포함된 웹 애플리케이션은 접근성이 있어야 한다.**   
웹 애플리케이션이 포함된 콘텐츠는 모든 사용자가 기능을 동등하게 사용할 수 있도록 접근성이 보장되어야 하며, 이는 보조기술 사용자에게도 동일한 기능 제공이 가능하도록 구성해야 함.     

[WCAG 2.2 - 2.1.1 키보드](https://www.w3.org/TR/WCAG22/#keyboard){: target="_blank"}     
[WCAG 2.2 - 4.1.2 이름, 역할, 값](https://www.w3.org/TR/WCAG22/#name-role-value){: target="_blank"}      
[MDN 웹 접근성 개요](https://developer.mozilla.org/ko/docs/Web/Accessibility){: target="_blank"}    

[WCAG 2.2 - 관련 성공 기준]    

- [2.1.1 키보드 (레벨 A)](https://www.w3.org/TR/WCAG22/#keyboard)    
- [2.4.3 포커스 순서 (레벨 A)](https://www.w3.org/TR/WCAG22/#focus-order)    
- [2.5.1 포인터 제스처 (레벨 A)](https://www.w3.org/TR/WCAG22/#pointer-gestures)    
- [2.5.2 포인터 취소 (레벨 A)](https://www.w3.org/TR/WCAG22/#pointer-cancellation)    
- [2.5.3 레이블과 이름 (레벨 A)](https://www.w3.org/TR/WCAG22/#label-in-name)    
- [2.5.4 동작 기반 작동 (레벨 A)](https://www.w3.org/TR/WCAG22/#motion-actuation)    
- [4.1.2 이름, 역할, 값 (레벨 A)](https://www.w3.org/TR/WCAG22/#name-role-value)          


웹 애플리케이션은 다음에 설명한 모든 요구사항을 적용하여 제작해야 한다.    

- 접근성 프로그래밍 인터페이스 사용 지원: 웹 애플리케이션은 운영체제 또는 플랫폼이 제공하는 접근성 프로그래밍 인터페이스를 사용하여 제작해야 한다. 그렇지 않으면 보조기술이 웹 애플리케이션의 접근성 기능을 지원하지 못하는 경우가 발생할 수 있다.     
- 접근성 프로그래밍 인터페이스 대체수단 제공: 웹 애플리케이션을 구현하는 과정에서 운영체제(플랫폼 포함)가 제공하는 접근성 프로그래밍 인터페이스가 정의되지 않은 새로운 기능을 구현할 경우, 그 기능의 명칭, 역할, 상태 및 값에 관한 정보를 운영체제(또는 플랫폼)의 접근성 프로그래밍 인터페이스로 전달하도록 구현함으로써 보조기술이 그 정보를 이용할 수 있게 해야 한다.    
- 보조기술 지원: 국내의 보조기술로 접근이 불가능한 웹 애플리케이션은 가능한 한 사용하지 않는 것이 좋으며, 반드시 사용해야 하는 경우, 해당 웹 애플리케이션에 대한 대체수단을 제공해야 한다.      

**기대효과**   

- 웹 애플리케이션이 접근성을 제공할 경우 보조기술이 웹 애플리케이션과 상호작용 가능하므로, 보조기술 사용자가 웹 애플리케이션을 활용할 수 있다.     
- 웹 애플리케이션에 적용하려는 기능이 플랫폼 접근성 프로그래밍 인터페이스를 지원하지 못하더라도 필수적인 접근성 정보를 플랫폼 접근성 프로그래밍 인터페이스를 통하여 보조기술로 제공할 수 있게 되므로 새롭고 접근성이 있는 기술 개발이 가능하다.     

#### 1. 필요성        

- 비장애인뿐만 아니라 보조기술 사용자(스크린 리더, 키보드 사용자 등)도 웹 애플리케이션을 완전하게 사용할 수 있도록 함.     
- SPA(Single Page Application) 등 동적 콘텐츠는 접근성 요소(ARIA, 포커스 이동 등)를 통해 구조화 필요.   


#### 2. 대상       

| 사용자 유형        | 접근성 필요 이유 |
|-------------------|------------------|
| 시각장애인         | 보이지 않는 UI에 대한 명확한 안내 필요 |
| 지체장애인         | 키보드만으로 조작 가능한 환경 필요 |
| 인지장애인         | 논리적 흐름, 오류 피드백 필요 |
| 고령자             | 명확하고 간단한 UI, 고대비 필요 |


#### 3. 체크리스트       

- 동적 콘텐츠가 갱신될 때 `aria-live`로 알림을 제공하는가?    
- 모든 컨트롤이 키보드로 조작 가능한가?    
- 버튼, 입력 등의 인터랙션 요소에 `aria-label`이 적절히 부여되어 있는가?    
- `role`, `name`, `state`, `value`가 명확히 전달되는가?     
- 포커스 순서가 논리적이며 시각적으로 확인 가능한가?    


#### 4. 테스트 방법      

- 키보드만 사용해 기능을 조작해 보기 (`Tab`, `Enter`, `Space`, `Esc`, `Arrow` 등)    
- 스크린 리더로 콘텐츠를 탐색하며 각 요소의 이름/역할/상태 전달 여부 확인    
- 자동화 도구 사용: WAVE, Axe, Lighthouse    
- ARIA 속성이 올바르게 동작하는지 개발자 도구로 확인   


#### 5. QA 지표       

- 키보드 탐색 가능 비율   
- ARIA 속성 적용 정확도    
- 스크린 리더 정보 전달 정확도    
- 동적 콘텐츠 변경 시 알림 제공 여부   


#### 6. 개발방법     

**HTML 예시**  
```html
<button aria-label="알림 열기" aria-expanded="false">🔔</button>
<div role="dialog" aria-label="알림 목록" hidden>
  <p>새로운 알림이 있습니다.</p>
</div>
```

**Vue 예시**  
```vue
<template>
  <button
    @click="toggle"
    aria-label="알림 열기"
    :aria-expanded="isOpen.toString()"
  >
    🔔
  </button>
  <section v-if="isOpen" role="dialog" aria-label="알림 목록">
    <p>새로운 알림이 있습니다.</p>
  </section>
</template>

<script setup>
import { ref } from 'vue';
const isOpen = ref(false);
const toggle = () => (isOpen.value = !isOpen.value);
</script>
```

**React 예시**  
```jsx
function Notification() {
  const [isOpen, setIsOpen] = React.useState(false);
  return (
    <>
      <button
        aria-label="알림 열기"
        aria-expanded={isOpen}
        onClick={() => setIsOpen(!isOpen)}
      >
        🔔
      </button>
      {isOpen && (
        <div role="dialog" aria-label="알림 목록">
          <p>새로운 알림이 있습니다.</p>
        </div>
      )}
    </>
  );
}
```

#### 7. 점검 기준     

- 사용자는 보조기술을 통해 애플리케이션의 모든 기능을 사용할 수 있어야 한다.    
- 인터랙션 가능한 요소는 `role`, `name`, `state`, `value`가 적절히 제공되어야 한다.   

#### 8. 점검 방법     

- 키보드 탐색이 가능한가?    
- 포커스가 논리적으로 이동하는가?    
- 자동화 도구에서 접근성 오류가 발생하지 않는가?   

#### 9. 준수 사례       

```html
<button aria-label="검색 열기">🔍</button>
```

#### 10. 미준수 사례       

```html
<button>🔍</button> <!-- aria-label 누락 -->
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/bg1Uvnoi4-w?si=aTcktWtDPt7ZIRAy" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (웹 애플리케이션 접근성 준수)](https://www.youtube.com/embed/bg1Uvnoi4-w?si=aTcktWtDPt7ZIRAy){: target="_blank"}    
   
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
