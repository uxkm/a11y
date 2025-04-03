# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    

**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #시각장애인, #인지장애 사용자, #청각과민 사용자, #비장애 사용자

   
### 자동 재생 금지   
**관련 지침 : 자동으로 소리가 재생되지 않아야 한다.**   
웹 페이지에서 자동으로 소리(동영상, 오디오, 음성, 배경 음악 등 콘텐츠가 제공하는 모든 소리)가 재생됨으로 인해 화면낭독프로그램 사용자가 콘텐츠를 인식하고 사용하는 데 방해받지 않아야 한다.     
단, 3초 미만의 소리는 허용한다. 3초 이상 재생되는 소리는 제어할 수 있는 수단(멈춤, 일시정지, 음량 조절 등)을 함께 제공해야 한다. 참고로, 플랫폼은 콘텐츠가 제공하는 배경음의 음량을 조절하더라도 화면낭독프로그램의 음량에는 영향을 주지 않아야 한다.    

🔗 관련 WCAG 2.2 성공 기준     
[1.4.2 오디오 제어(Audio Control) (Level A)](https://www.w3.org/TR/WCAG22/#audio-control){: target="_blank"}    
[WAI - Understanding Audio Control](https://www.w3.org/WAI/WCAG22/Understanding/audio-control.html){: target="_blank"}   
[MDN - HTML audio autoplay 속성](https://developer.mozilla.org/ko/docs/Web/HTML/Element/audio#autoplay){: target="_blank"}   

- 자동 재생음을 허용하는 경우: 자동으로 재생되는 소리는 3초 내에 멈추거나, 지정된 키(예: esc키)를 누르면 재생을 멈추도록 구현한다.    
- 사용자 요구에 의한 재생: 콘텐츠에 포함된 멀티미디어 파일은 정지 상태로 제공하며 사용자가 요구할 경우에만 재생할 수 있도록 제어판(멈춤, 일시 정지, 음량 조절 등)을 제공한다.    

**기대효과**   

- 멀티미디어 콘텐츠가 자동적으로 실행되어 시각장애인이 사용하고 있는 화면낭독프로그램이 읽어주는 소리를 방해하면 큰 혼란을 야기할 수 있다. 따라서 3초 이후에는 해당 멀티미디어 콘텐츠가 자동적으로 만들어 내는 소리가 멈추어야 시각장애인이 이 페이지를 사용할 수 있다.    

#### 1. 필요성        
웹페이지에 접속했을 때 **사용자의 동의 없이 자동으로 재생되는 오디오 또는 영상 콘텐츠는 접근성을 심각하게 저해**합니다. 특히 스크린 리더 사용자나 집중이 필요한 사용자에게 불쾌감 또는 기능적 장애를 유발할 수 있으므로, **자동 재생은 반드시 비활성화**하거나 **사용자가 제어할 수 있어야** 합니다.    

- 스크린 리더 사용자는 자동 재생으로 인해 **음성 출력을 방해받음**    
- 사용자의 주의를 강제로 분산시키고 혼란을 야기   
- 모바일 환경에서는 데이터 낭비 및 배터리 사용 증가    
- 사용자 중심의 제어권 보장을 위해 필요    

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 시각장애인         | 스크린 리더 음성과 충돌  
| 인지장애 사용자     | 갑작스러운 소리에 혼란  
| 청각과민 사용자     | 감각 과부하 유발 가능  
| 비장애 사용자         | 데이터/배터리 낭비, 갑작스러운 소리로 불쾌감  

#### 3. 체크리스트       

- 웹 페이지가 로드될 때 자동으로 소리가 나는 콘텐츠가 있는가?    
- 자동 재생이 필요한 경우, 사용자 제어 기능(정지, 음소거 등)이 제공되는가?    
- 사용자 조작(클릭 등)을 통해서만 재생되도록 설정되었는가?    

#### 4. 테스트 방법      

- 페이지 접속 시 자동으로 소리 재생 여부 확인    
- 사용자 조작 없이 오디오/비디오가 재생되는지 테스트    
- 보조기술 사용 중 음성 재생 충돌 여부 확인    

#### 5. QA 지표       

- 자동 재생 콘텐츠 발생률   
- 사용자 제어 요소 제공 여부   
- 음소거 설정 가능률   

#### 6. 개발방법     

#### HTML 예시 – 사용자 제어 기반
```html
<video controls>
  <source src="video.mp4" type="video/mp4">
</video>
```

#### 잘못된 예시 – 자동 재생 + 소리 출력
```html
<audio autoplay>
  <source src="audio.mp3" type="audio/mpeg">
</audio>
```

#### Vue 예시
```vue
<template>
  <audio ref="player" controls>
    <source src="/media/alert.mp3" type="audio/mpeg" />
  </audio>
</template>
```

#### React 예시
```jsx
function AudioPlayer() {
  return (
    <audio controls>
      <source src="/media/audio.mp3" type="audio/mpeg" />
    </audio>
  );
}
```

#### 7. 점검 기준     

- `<audio>` 또는 `<video>` 태그에서 autoplay 속성이 있는가?   
- autoplay가 있는 경우, 소리가 없는 콘텐츠인가?   
- 사용자 조작으로만 재생이 가능한가?   

#### 8. 점검 방법     

- 페이지 최초 접근 시 오디오 출력 유무 확인    
- `<audio>`, `<video>` 요소에 `autoplay` 속성 존재 여부 확인    
- 소리 제어 UI 제공 여부 확인    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-contrast-minimum01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<video controls>
  <source src="tutorial.mp4" type="video/mp4">
</video>
```

#### 10. 미준수 사례       

```html
<audio autoplay>
  <source src="intro.mp3" type="audio/mpeg">
</audio>
```

#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/RX7wfKwYA7Y?si=3BAw9PuKKpiAqEMH" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (자동 재생 금지)](https://www.youtube.com/embed/RX7wfKwYA7Y?si=3BAw9PuKKpiAqEMH){: target="_blank"}    
   
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
