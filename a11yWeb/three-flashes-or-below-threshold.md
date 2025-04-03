# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    


**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #광과민성 간질 사용자, #인지장애 사용자, #비장애 사용자


### 깜빡임과 번쩍임 사용 제한 
**관련 지침 : 초당 3~50회 주기로 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.**   
깜빡이거나(blinking) 번쩍이는(flashing) 콘텐츠로 인해 발작을 일으키지 않도록 초당 3∼50회 주기로 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다. 10인치 이상의 스크린을 채용하고 있는 정보통신기기(태블릿 기기, PC 모니터, 무인 안내기 등)에서는 콘텐츠에 의한 광과민성 발작 가능성을 특히 주의해야 한다.      

[2.3.1 삼광 플래시 임계값을 넘지 않음 (Level A)](https://www.w3.org/TR/WCAG22/#three-flashes-or-below-threshold){: target="_blank"}    
[WAI - Understanding Three Flashes](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html){: target="_blank"}      
[MDN - CSS animation 속성](https://developer.mozilla.org/ko/docs/Web/CSS/animation){: target="_blank"}    

- 번쩍이는 콘텐츠 사용 금지: 번쩍임이 초당 3~50회이며, 10인치 이상의 화면에 표시된 번쩍이는 콘텐츠가 차지하는 면적의 합이 화면 전체 면적의 10%를 넘지 않아야 한다.    
- 깜빡이는 콘텐츠 사용 금지: 초당 3~50회의 속도로 깜빡거리게 만든 콘텐츠는 그 깜빡임을 정지시킬 수 있어야 한다.    
- 번쩍이는 시간 제한: 웹 페이지에 포함되는 콘텐츠의 번쩍이는 시간을 3초 미만으로 제한하면, 지속적인 번쩍임으로 인한 사용자(예: 광과민성 증후 환자, 학습장애인, 저시력장애인 등)의 발작을 예방하면서도 콘텐츠의 중요성을 알릴 수 있다.   

**기대효과**   

- 광과민성 증후가 있는 사용자들은 빛이 번쩍거리는 것에 민감하게 반응하여 발작을 일으킬 수 있다. 따라서 본 검사항목을 준수한 콘텐츠는 광과민성 증후가 있는 사용자도 접근 가능하다.   
- 주의집중에 어려움이 있는 사람의 경우, 지속적으로 번쩍거림이 있는 콘텐츠를 집중하여 응시하기가 매우 어렵다. 따라서 본 검사항목을 만족하는 웹 콘텐츠는 주의집중에 어려움이 있는 사람도 접근이 가능하다.   

#### 1. 필요성        
깜빡이거나 번쩍이는 콘텐츠는 **광과민성 발작(Photosensitive Epilepsy)** 을 유발할 수 있으므로, 콘텐츠는 초당 3~50회 사이의 깜빡임을 포함하지 않아야 하며, **애니메이션 또는 영상 효과 사용 시 반드시 주기와 속도를 제어**해야 합니다.    

- 광과민성 간질 환자 보호   
- 시각적 과부하 방지   
- 애니메이션 사용 시 안전한 사용자 환경 제공    

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 광과민성 간질 사용자 | 특정 주기의 깜빡임에 민감하게 반응  
| 인지장애 사용자     | 강한 시각 자극으로 혼란 유발  
| 비장애 사용자         | 과도한 번쩍임으로 인한 시각 피로  

#### 3. 체크리스트       

- 초당 3~50회 깜빡임 또는 번쩍이는 콘텐츠가 있는가?   
- 사용자가 깜빡임 효과를 끌 수 있는 옵션이 있는가?   
- 깜빡임 대신 페이드 인/아웃 등 다른 효과를 사용하고 있는가?   
- 영상 또는 애니메이션이 안전한 주기로 설정되어 있는가?   

#### 4. 테스트 방법      

- 깜빡이는 콘텐츠가 3~50Hz의 주기로 움직이는지 측정   
- 애니메이션 효과의 반복 속도 확인    
- 수동 또는 자동 전환 효과가 있는 경우 전환 주기 측정    

#### 5. QA 지표       

- 고위험 주기 콘텐츠 비율   
- 애니메이션 속도 제어 여부   
- 사용자 제어 옵션 제공 여부   

#### 6. 개발방법     

#### HTML/CSS 예시 – 안전한 페이드 효과
```html
<div class="fade-box">안전한 효과</div>

<style>
.fade-box {
  animation: fade 2s ease-in-out infinite;
}
@keyframes fade {
  0% { opacity: 1; }
  50% { opacity: 0.3; }
  100% { opacity: 1; }
}
</style>
```

#### 잘못된 예시 – 깜빡임 주기 빠름 (위험)
```html
<div class="blink">위험한 깜빡임</div>

<style>
.blink {
  animation: blink 0.05s step-start infinite;
}
@keyframes blink {
  50% { opacity: 0; }
}
</style>
```

#### Vue 예시 – 안전한 트랜지션
```vue
<template>
  <transition name="fade">
    <div v-if="show">내용 표시</div>
  </transition>
</template>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 1.5s ease-in-out;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
```

#### React 예시 – 안전한 CSS 효과 활용
```jsx
function SafeBlink() {
  return (
    <div style={{
      animation: 'fade 2s ease-in-out infinite',
      '@keyframes fade': `0%{opacity:1} 50%{opacity:0.3} 100%{opacity:1}`
    }}>
      안전한 전환
    </div>
  );
}
```

#### 7. 점검 기준     

- 깜빡임 속도가 초당 3~50회 이하인가?    
- 반복 효과에 대한 제어 또는 대체 수단이 제공되는가?    

#### 8. 점검 방법     
 
- Chrome DevTools에서 애니메이션 속도 확인    
- Lighthouse 또는 Axe 등 자동화 도구 활용    
- 스크린 녹화 후 프레임 분석 (고급 점검)    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-three-flashes-or-below-threshold01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<div style="animation: fade 2s ease-in-out infinite;">부드러운 효과</div>
```

#### 10. 미준수 사례       

```html
<div style="animation: blink 0.03s step-start infinite;">과도한 깜빡임</div>
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/q0GeFyxNnJE?si=sM8X3SP-sOG8tLza" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (깜빡임과 번쩍임 사용 제한)](https://www.youtube.com/embed/q0GeFyxNnJE?si=sM8X3SP-sOG8tLza){: target="_blank"}    
   
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
