# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애 사용자, #저시력장애인, #지적장애인, #인지장애 사용자, #발작 장애 사용자, #모든 사용자


### 정지 기능 제공 
**관련 지침 : 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.**   
웹 콘텐츠는 스크롤 및 자동 갱신되는 콘텐츠를 장애인 사용자가 이용할 수 있도록 일시 정지할 수 있는 수단을 제공해야 한다.     
슬라이드 배너, 자동 뉴스 티커, 애니메이션 등 자동으로 움직이는 콘텐츠는 **사용자가 정지(Pause), 재생(Play), 숨김(Hide) 등의 제어 기능을 사용할 수 있어야 하며**, 5초 이상 지속되는 자동 움직임은 필수적으로 제어 기능을 제공해야 합니다.    

[2.2.2 일시정지, 정지, 숨기기 (Pause, Stop, Hide) (Level A)](https://www.w3.org/TR/WCAG22/#pause-stop-hide){: target="_blank"}    
[WAI - Understanding Pause, Stop, Hide](https://www.w3.org/WAI/WCAG22/Understanding/pause-stop-hide.html){: target="_blank"}      
[MDN - aria-pressed](https://developer.mozilla.org/ko/docs/Web/Accessibility/ARIA/Attributes/aria-pressed){: target="_blank"}    

- 이동하거나 스크롤되는 콘텐츠 사용 배제: 스크롤 및 자동 갱신되는 콘텐츠를 사용하지 않는다.    
- 이동하거나 스크롤되는 콘텐츠: 저시력장애인이나 지적장애인 등은 이동하거나 스크롤되는 콘텐츠를 사용하기 어려우므로, 웹 콘텐츠는 사용자가 이동이나 스크롤을 일시 정지시키고, 지나간 콘텐츠 또는 앞으로 나타날 콘텐츠를 선택할 수 있는 콘트롤(예: ‘앞으로 이동', ‘뒤로 이동’, ‘정지’ 등)을 제공해야 한다.    

**기대효과**   


#### 1. 필요성        

- 시각장애 및 인지장애 사용자는 자동 콘텐츠의 반복이 주의를 방해하거나 혼란을 유발   
- 스크린 리더 사용 시 자동으로 움직이는 콘텐츠가 콘텐츠 탐색을 방해    
- 사용자에게 콘텐츠 제어권을 부여하여 자율성을 보장    

#### 2. 대상       

| 사용자 유형       | 이유 |
|--------------------|------|
| 시각장애 사용자     | 자동 슬라이드가 정보 탐색 방해  
| 인지장애 사용자     | 자동 콘텐츠로 인한 집중력 저하  
| 발작 장애 사용자     | 깜빡이는 콘텐츠로 인한 위험 발생 가능  
| 모든 사용자         | 사용자의 자율적인 콘텐츠 제어 필요  

#### 3. 체크리스트       

- 자동 슬라이드, 애니메이션, 배너에 정지 또는 일시정지 기능이 있는가?   
- 움직임이 5초 이상 지속되는가? 해당되는 경우 제어 기능이 있는가?    
- 키보드 또는 마우스로 정지 기능을 조작할 수 있는가?    
- 스크린 리더로 제어 버튼을 인식할 수 있는가?    

#### 4. 테스트 방법      

- 자동 슬라이드 배너 등 콘텐츠에 정지 버튼이 있는지 확인    
- 정지 버튼이 작동하며 상태가 반영되는지 테스트    
- 스크린 리더로 제어 요소 인식 가능 여부 확인    

#### 5. QA 지표       

- 자동 콘텐츠 제어 기능 제공률    
- 제어 UI 접근 가능성    
- 키보드 및 보조기술 조작률    

#### 6. 개발방법     

#### HTML 예시 – 슬라이드 정지 버튼 제공
```html
<div class="slider" aria-label="광고 슬라이드">
  <div class="slide">슬라이드 1</div>
  <div class="slide">슬라이드 2</div>
  <button onclick="pauseSlider()" aria-pressed="false">정지</button>
</div>

<script>
  let sliderPaused = false;
  let current = 0;
  const slides = document.querySelectorAll('.slide');

  const interval = setInterval(() => {
    if (!sliderPaused) {
      slides[current].style.display = 'none';
      current = (current + 1) % slides.length;
      slides[current].style.display = 'block';
    }
  }, 4000);

  function pauseSlider() {
    sliderPaused = !sliderPaused;
    const btn = document.querySelector('button');
    btn.textContent = sliderPaused ? '재생' : '정지';
    btn.setAttribute('aria-pressed', sliderPaused.toString());
  }
</script>
```

#### Vue 예시
```vue
<template>
  <div>
    <div>{{ slides[current] }}</div>
    <button @click="togglePause" :aria-pressed="paused">{{ paused ? '재생' : '정지' }}</button>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const slides = ['슬라이드 A', '슬라이드 B'];
const current = ref(0);
const paused = ref(false);

onMounted(() => {
  setInterval(() => {
    if (!paused.value) current.value = (current.value + 1) % slides.length;
  }, 4000);
});

function togglePause() {
  paused.value = !paused.value;
}
</script>
```

#### React 예시
```jsx
import { useState, useEffect } from 'react';

function Slider() {
  const [paused, setPaused] = useState(false);
  const [current, setCurrent] = useState(0);
  const slides = ['Slide 1', 'Slide 2'];

  useEffect(() => {
    const interval = setInterval(() => {
      if (!paused) {
        setCurrent(c => (c + 1) % slides.length);
      }
    }, 4000);
    return () => clearInterval(interval);
  }, [paused]);

  return (
    <div>
      <div>{slides[current]}</div>
      <button onClick={() => setPaused(!paused)} aria-pressed={paused}>
        {paused ? 'Play' : 'Pause'}
      </button>
    </div>
  );
}
```

#### 7. 점검 기준     

- 자동 콘텐츠가 사용자의 제어 없이 계속 진행되지 않는가?   
- 제어 버튼이 보이고, 키보드 및 보조기술로도 접근 가능한가?   
- 상태(정지/재생)가 시각적 또는 ARIA 속성으로 제공되는가?   

#### 8. 점검 방법     

- 슬라이드, 광고 배너 등 자동 콘텐츠에서 정지 기능 확인   
- 보조기술로 제어 버튼 접근 및 상태 전환 확인   
- 키보드 조작 시 기능이 제대로 작동하는지 확인   

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-pause-stop01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<button aria-pressed="false" onclick="pause()">정지</button>
```

#### 10. 미준수 사례       

```html
<!-- 자동으로 변경되지만 멈출 수 없음 -->
<div class="auto-banner">내용 A</div>
<!-- 사용자 제어 기능 없음 -->
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/bOjiqsCLHL0?si=G3w_wtqblbyuHWDr" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (정지 기능 제공)](https://www.youtube.com/embed/bOjiqsCLHL0?si=G3w_wtqblbyuHWDr){: target="_blank"}    
   
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
