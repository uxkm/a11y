# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    

**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #청각장애 사용자, #외국어 청취 어려운 사용자, #환경적 제약 사용자

   
### 자막 제공   
**관련 지침 : 멀티미디어 콘텐츠에는 자막, 대본 또는 수어를 제공해야 한다.**   
멀티미디어 콘텐츠를 장애인도 비장애인과 동등하게 인식할 수 있도록 제작하기 위해서는 자막, 대본 또는 수어를 제공해야 한다. 여기에서 가장 중요한 요소는 멀티미디어 콘텐츠와 동등한 내용을 제공하는 것이다. 가장 바람직한 방법은 폐쇄자막을 오디오와 동기화시켜 제공하는 것이다. 대사 없이 영상만 제공하는 경우, 화면해설(텍스트, 오디오, 대본)을 제공해야 한다. 음성만 제공하는 경우에도 자막, 대본 또는 수어를 제공해야 한다. 자막, 대본 또는 수어는 멀티미디어 콘텐츠에 포함된 음성의 문맥과 동등해야 한다.      


🔗 관련 WCAG 2.2 성공 기준    
[1.2.2 캡션(사전 녹화된 콘텐츠) (Level A)](https://www.w3.org/TR/WCAG22/#captions-prerecorded){: target="_blank"}      
[1.2.1 오디오 전용 및 영상 전용 (Level A)](https://www.w3.org/TR/WCAG22/#audio-only-and-video-only-prerecorded){: target="_blank"}      
[1.2.3 오디오 설명 또는 대본 (Level A)](https://www.w3.org/TR/WCAG22/#audio-description-or-media-alternative-prerecorded){: target="_blank"}    
[WAI - Understanding Captions](https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html){: target="_blank"}      
[MDN - HTML <track> 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/track){: target="_blank"}    

**대체수단 제공: 다음 중 한 가지 이상의 대체수단을 제공해야 한다.**    

- 자막 제공: 멀티미디어 콘텐츠를 재생시킬 때마다 자동적으로 자막을 화면에 표시할 수 있는 멀티미디어 콘텐츠는 본 검사항목을 준수한 것으로 간주할 수 있다. 자막은 멀티미디어 콘텐츠에 포함된 음성(대사)과 동등해야 한다. 필요에 따라 자막을 여러 언어로 제공하면, 사용자는 자신이 사용하기를 원하는 자막을 선택할 수 있다.    
- 대본 제공: 자막과는 달리 멀티미디어가 재생되는 과정에서 시나리오를 제공하는 경우도 본 검사항목을 준수한 것으로 간주한다. 대본은 멀티미디어 콘텐츠에 포함된 음성(대사)과 동등해야 한다. 필요에 따라 대본을 여러 언어로 제공하면, 사용자는 자신이 사용하기를 원하는 대본을 선택할 수 있다.    
- 수어 제공: 비디오 콘텐츠에 수어를 중첩하여 녹화한 콘텐츠도 본 검사항목을 준수한 것으로 간주한다. 수어는 멀티미디어 콘텐츠에 포함된 음성(대사)과 동등해야 한다.    


**기대효과**   

- 청각장애인은 자막을 통해 음성이나 음향 정보에 접근할 수 있다. 또한 자막을 활용하면 해당 콘텐츠에 대한 인덱스를 작성하거나 내용 검색도 용이하게 할 수 있다. 수어를 제공하는 콘텐츠도 청각장애인의 접근이 용이하다.     
- 장애인이 아닌 경우에도 자막이 포함된 영상 매체를 다양한 방법으로 활용할 수 있다.    
  예를 들어, 자막은 소란한 환경이나 오디오 재생기능이 갖추어져 있지 않은 환경에서 영상의 자세한 내용을 파악하는 데 유용하다. 사용자가 자막을 언어별로 선택할 수 있게 하면 외국어 습득과 같이 언어능력이나 읽기능력을 향상시키는 데 도움이 된다.     

#### 1. 필요성        
영상 콘텐츠에는 **청각 장애 사용자 또는 소리를 들을 수 없는 환경의 사용자**를 위해 자막, 대본(script), 수어 등의 **대체 수단**을 제공해야 합니다. 자막은 음성 정보뿐만 아니라 중요한 소리 정보(예: 박수, 경고음 등)도 포함해야 하며, 사용자에게 명확하게 전달되어야 합니다.    


- 청각장애 사용자에게 음성 콘텐츠의 의미 전달    
- 지하철, 도서관 등 **음소거 환경**에서도 영상 시청 가능    
- 자막은 외국어 콘텐츠의 이해력 향상에도 도움    
- 대본, 수어 등 다양한 수단은 접근성 선택권 확대    


#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 청각장애 사용자     | 영상 속 대사, 설명 등 이해 가능  
| 외국어 청취 어려운 사용자 | 자막을 통해 이해도 향상  
| 환경적 제약 사용자  | 음소거 환경, 소리 차단 기기 사용 시 유용  

#### 3. 체크리스트       

- 영상 콘텐츠에 자막이 제공되는가?    
- 자막이 음성 정보뿐만 아니라 중요한 소리 정보도 포함하는가?    
- 자막이 시각적으로 명확하게 표현되는가?    
- 대본 또는 수어 영상이 함께 제공되는가?    

#### 4. 테스트 방법      

- 영상 콘텐츠 재생 시 자막 표시 여부 확인    
- 음성 정보 없이 자막만으로 의미를 이해할 수 있는지 확인    
- 스크립트/수어 영상 제공 여부 확인    

#### 5. QA 지표       

- 전체 영상 중 자막 제공 비율   
- 수어/스크립트 제공 여부   
- 자막 내용 완성도(음성 외 정보 포함 여부)    

#### 6. 개발방법     

#### HTML 예시 – `<track>` 요소 사용
```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="captions_ko.vtt" kind="captions" srclang="ko" label="한국어 자막" default>
</video>
```

#### Vue 예시
```vue
<template>
  <video controls>
    <source :src="videoSrc" type="video/mp4" />
    <track
      kind="captions"
      srclang="ko"
      label="한국어 자막"
      :src="captionSrc"
      default
    />
  </video>
</template>

<script setup>
const videoSrc = "/media/sample.mp4";
const captionSrc = "/media/sample.vtt";
</script>
```

#### React 예시
```jsx
function VideoWithCaptions() {
  return (
    <video controls>
      <source src="/media/sample.mp4" type="video/mp4" />
      <track
        src="/media/sample.vtt"
        kind="captions"
        srclang="ko"
        label="한국어 자막"
        default
      />
    </video>
  );
}
```

#### 7. 점검 기준     

- 모든 영상 콘텐츠에 적절한 자막 또는 대본이 포함되었는가?    
- 수어, 텍스트 대체 콘텐츠가 접근 가능하게 제공되는가?    

#### 8. 점검 방법     

- 영상에서 `<track>` 요소 또는 별도 대본 링크 존재 여부 확인    
- 음성 정보와 자막 싱크 확인    
- 자막이 시각적으로 명확하게 표시되는지 테스트    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-captions-prerecorded01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<video controls>
  <source src="interview.mp4" type="video/mp4">
  <track src="interview_ko.vtt" kind="captions" srclang="ko" label="한국어 자막" default>
</video>
```

#### 10. 미준수 사례       

```html
<video controls>
  <source src="interview.mp4" type="video/mp4">
</video>
<!-- 자막 또는 대체 텍스트가 전혀 없음 -->
```



#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/oNnlDFOL-P4?si=VXzICisHy0Nm9A8G" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (자막 제공)](https://youtu.be/vtKmpY28IRs?si=xOZjf7NVF1ctJUBd){: target="_blank"}    
   
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
