# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #인지장애 사용자, #시각장애 사용자, #지체 장애 사용자, #모든 사용자


### 응답시간 조절 
**관련 지침 : 시간제한이 있는 콘텐츠는 응답시간을 조절할 수 있어야 한다.**   
웹 콘텐츠 제작 시 시간제한이 있는 콘텐츠는 가급적 포함하지 않는 것이 바람직하며, 보안 등의 사유로 시간제한이 반드시 필요할 경우 이를 회피할 수 있는 수단을 제공해야 한다.     

[2.2.1 타이밍 조절 (Level A)](https://www.w3.org/TR/WCAG22/#timing-adjustable){: target="_blank"}    
[WAI - Understanding Timing Adjustable](https://www.w3.org/WAI/WCAG22/Understanding/timing-adjustable.html){: target="_blank"}      
[MDN - setTimeout()](https://developer.mozilla.org/ko/docs/Web/API/setTimeout){: target="_blank"}    

- 시간제한 콘텐츠 사용 배제: 시간제한이 있는 콘텐츠는 제공하지 않아야 한다.    
- 예외 콘텐츠: 시간제한이 있더라도 온라인 경매, 실시간 게임 등과 같이 반응시간의 조절이 원천적으로 허용되지 않는 경우, 본 검사항목이 적용되지 않는다. 다만, 이 경우에도 사용자에게 시간제한이 있다는 것을 미리 알려주고, 종료되었을 경우에도 이를 알려주어야 한다. 세션 시간이 20시간 이상인 콘텐츠의 경우에도 예외로 간주한다.     
- 반응시간 조절이 필요한 콘텐츠: 반응시간이 정해진 웹 콘텐츠를 사용자가 이용할 수 있도록 하기 위해서는 반응시간이 완료되기 전에 사용자가 다음 중 한 가지 방법을 선택하여 반응시간을 조절할 수 있는 수단을 제공해야 한다. 또한 반응시간 조절 기능은 충분한 시간(최소 20초 이상)을 두고 사전에 알려주어야 한다.    
  (가) 시간제한을 해제할 수 있어야 한다.    
  (나) 시간제한을 연장할 수 있어야 한다.     


**기대효과**   

- 비장애인보다 문서를 읽고 이해하는 데 더 많은 시간이 필요한 지적장애 또는 학습장애가 있는 사용자도 시간제한이 있는 콘텐츠를 시간에 관계없이 이용할 수 있게 된다.    

#### 1. 필요성        
로그인 세션, 설문조사, 퀴즈, 게임 등 시간제한이 포함된 콘텐츠는 사용자가 **시간 연장, 일시정지, 해제 또는 비활성화**할 수 있는 기능을 제공해야 합니다. 이는 장애 사용자나 느린 사용자도 콘텐츠를 완전히 이용할 수 있게 하기 위함입니다.    

- 느린 독해 사용자나 보조기술 사용자는 제한 시간 내 완료가 어려움   
- 정보 입력 중 갑작스러운 만료는 혼란과 좌절을 유발   
- 사용자의 능력 차이를 고려한 조정 가능한 응답 시간이 중요   

#### 2. 대상       

| 사용자 유형         | 이유 |
|----------------------|------|
| 인지장애 사용자       | 시간 압박 시 오류 발생 가능성 높음  
| 시각장애 사용자       | 스크린 리더로 느린 탐색 시 제한 시간 초과  
| 지체 장애 사용자       | 조작 속도 느림  
| 모든 사용자           | 세션 유지 등 유연한 사용자 경험 필요  

#### 3. 체크리스트       

- 시간 제한 콘텐츠에 대해 연장/해제 옵션이 제공되는가?   
- 경고 또는 시간 종료 전에 알림이 제공되는가?   
- 기본 시간 제한이 너무 짧지 않은가? (최소 20초 연장 기회 제공)   
- 세션 타이머가 사용자에게 명확히 전달되는가?   

#### 4. 테스트 방법      

- 제한 시간 콘텐츠를 실행하고, 연장/일시정지 옵션 제공 여부 확인   
- 시각적 타이머 또는 알림 존재 여부 확인   
- 스크린 리더로 남은 시간 인식 가능 여부 확인   

#### 5. QA 지표       

- 시간 연장 기능 제공률   
- 시간 제한 경고 알림 제공 여부   
- 시간 제한 인식 가능률(스크린 리더 포함)   

#### 6. 개발방법     

#### HTML 예시 – 시간 연장 버튼 제공
```html
<p id="timer">남은 시간: <span id="seconds">30</span>초</p>
<button onclick="extendTime()">시간 연장</button>

<script>
  let time = 30;
  const seconds = document.getElementById("seconds");
  const interval = setInterval(() => {
    if (time > 0) {
      time--;
      seconds.textContent = time;
    } else {
      clearInterval(interval);
      alert("시간이 종료되었습니다.");
    }
  }, 1000);

  function extendTime() {
    time += 20;
  }
</script>
```

#### Vue 예시
```vue
<template>
  <div>
    <p>남은 시간: {{ time }}초</p>
    <button @click="extendTime">시간 연장</button>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
const time = ref(30);
let timer;

onMounted(() => {
  timer = setInterval(() => {
    if (time.value > 0) time.value--;
    else clearInterval(timer);
  }, 1000);
});

function extendTime() {
  time.value += 20;
}
</script>
```

#### React 예시
```jsx
import { useState, useEffect } from 'react';

function Timer() {
  const [time, setTime] = useState(30);

  useEffect(() => {
    const timer = setInterval(() => {
      setTime(t => {
        if (t > 0) return t - 1;
        clearInterval(timer);
        return 0;
      });
    }, 1000);
    return () => clearInterval(timer);
  }, []);

  return (
    <div>
      <p>남은 시간: {time}초</p>
      <button onClick={() => setTime(t => t + 20)}>시간 연장</button>
    </div>
  );
}
```

#### 7. 점검 기준     

- 시간제한 콘텐츠에 사용자 제어 기능이 있는가?   
- 시각/청각적 경고 제공 여부 확인   
- 화면에 시간 표시 및 제어 버튼이 있는가?   

#### 8. 점검 방법     

- 시간 제한 콘텐츠 접근 후 연장 가능 여부 테스트   
- 접근성 도구로 시간 정보 인식 테스트   
- 타이머 동작 후 사용자 제어 가능 여부 확인   

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-timing-adjustable01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<p>남은 시간: <span>30</span>초</p>
<button>시간 연장</button>
```

#### 10. 미준수 사례       

```html
<!-- 제한 시간 후 자동 종료되지만 제어 없음 -->
<script>
  setTimeout(() => {
    location.href = '/logout';
  }, 30000);
</script>
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/JXIHdCKgBpk?si=7C18XXoU9dsQfPkf" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (응답시간 조절)](https://www.youtube.com/embed/JXIHdCKgBpk?si=7C18XXoU9dsQfPkf){: target="_blank"}    
   
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
