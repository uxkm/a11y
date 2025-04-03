# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines) 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  

## 웹 접근성 콘텐츠 제작 기법   
> 사용자가 장애를 가지고 있거나 특정 기능적 제한을 겪는 경우에도 원활하게 웹을 이용할 수 있도록 하는 방법을 의미합니다. 이러한 접근성을 고려한 콘텐츠 제작은 다양한 사용자들의 요구를 충족시키며, 웹의 사용성을 크게 향상시킵니다.    

**키워드**   
#웹 접근성, #웹 접근성 콘텐츠 제작 기법, #한국형 웹 콘텐츠 접근성 지침 2.2, #WCAG2.2, #KWCAG2.2, #보조기술과의호환성, #접근성 테스트 도구 활용 점검방법, #스크린 리더, #Jaws, #NVDA, #센스리더, #Sense Reader, #명도 대비, #저시력 사용자, #색상 대비, #사용자 인터페이스, #텍스트 가독성, #고령자 

   
### 텍스트 콘텐츠의 명도 대비   
**관련 지침 : 텍스트 콘텐츠와 배경 간의 명도 대비는 4.5 대 1 이상이어야 한다.**   
웹 페이지에서 보이는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 충분한 대비를 제공하여, 저시력장애인, 색각장애인, 고령자 등도 콘텐츠를 인식할 수 있도록 제공해야 한다. 다만, 로고, 장식 목적의 콘텐츠, 마우스나 키보드를 활용하여 초점을 받았을 때 명도 대비가 커지는 콘텐츠 등은 예외로 한다.   

🔗 관련 WCAG 2.2 성공 기준     
[1.4.3 명도 대비(최소) (Level AA)](https://www.w3.org/TR/WCAG22/#contrast-minimum){: target="_blank"}    
[1.4.6 명도 대비(향상된) (Level AAA)](https://www.w3.org/TR/WCAG22/#contrast-enhanced){: target="_blank"}    
[WAI - Understanding Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html){: target="_blank"}      
[WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/){: target="_blank"}      
[MDN - Color and accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_Colors_and_Luminance){: target="_blank"}    

- 콘텐츠의 명도 대비: 웹 페이지가 제공하는 텍스트 콘텐츠(텍스트 및 텍스트 이미지)와 배경 간의 명도 대비는 4.5 대 1 이상이어야 한다.    
- 폰트 크기에 따른 명도 대비: 텍스트 콘텐츠를 구성하고 있는 텍스트 폰트를 18pt 이상 또는 14pt 이상의 굵은 폰트를 사용하는 경우, 명도 대비를 3 대 1까지 낮출 수 있다.   
- 화면 확대가 가능한 콘텐츠: 화면 확대가 가능하도록 구현한 텍스트 콘텐츠(텍스트 및 텍스트 이미지)의 명도 대비는 3 대 1까지 낮출 수 있다.    

**기대효과**   

1. **저시력 사용자도 정보 인식 가능**     
   명도 대비가 높을수록 시력이 약한 사용자들도 텍스트 내용을 더욱 분명하게 읽을 수 있습니다.     
   고령자, 안과 질환자, 노출 환경(햇빛 등)에 있는 사용자에게도 도움이 됩니다.   

2. **모든 사용자에게 가독성 향상**    
   색맹, 피로 누적 사용자, 다양한 디스플레이 환경에서 명도 대비는 전반적인 **가독성을 높여** 사용자 만족도를 향상시킵니다.   

3. **사용자 오류 감소**    
   텍스트 인식 오류로 인한 **입력 실수, 정보 오독**을 줄일 수 있어 웹 사용의 정확도와 효율성이 높아집니다.   

4. **접근성 법규 및 지침 준수**    
   WCAG 2.2, KWCAG 2.2 등 국내외 접근성 기준을 만족시켜 **인증 및 법적 요구사항**을 충족할 수 있습니다.   

5. **디지털 콘텐츠의 신뢰도 향상**    
   명확하게 읽을 수 있는 디자인은 사용자의 **브랜드 신뢰도** 향상에도 기여합니다.   


#### 1. 필요성    
텍스트와 배경 간의 충분한 명도 대비를 확보해야 **시력이 낮거나 저시력 사용자가 텍스트를 명확하게 인식할 수 있습니다.** 특히 기본 텍스트는 4.5:1 이상, 큰 텍스트(18pt 이상 또는 굵은 14pt 이상)는 3:1 이상의 대비를 확보해야 합니다.        

- 저시력 사용자나 고령자도 정보 인식 가능    
- 실외, 밝은 환경 등에서도 텍스트 식별 가능성 확보    
- 디자인적으로 보기 좋더라도 접근성이 떨어질 수 있음    

#### 2. 대상       

| 사용자 유형     | 이유 |
|------------------|------|
| 저시력 사용자       | 대비가 낮은 텍스트 인식이 어려움  
| 고령자             | 시력 감퇴로 인해 대비 부족 시 정보 인지 불가  
| 비장애 사용자         | 밝은 화면에서 가독성 확보에 유리  

#### 3. 체크리스트       

- 텍스트와 배경 간의 명도 대비 비율이 4.5:1 이상인가?    
- 큰 텍스트의 경우 3:1 이상인가?    
- 텍스트 위에 이미지나 패턴이 있을 경우, 가독성 확보가 되는가?     

#### 4. 테스트 방법      

- 명도 대비 측정 도구 사용 (예: WebAIM Contrast Checker, Axe DevTools 등)    
- Chrome 개발자 도구 - 접근성 탭 활용    
- 실제 저시력 사용자 테스트    

#### 5. QA 지표       

- 4.5:1 대비 충족률    
- 사용자 가독성 만족도    
- 배경 이미지/색상 대비 구간별 텍스트 가독성     

#### 6. 개발방법     

#### HTML 예시 – 대비 충분한 경우
```html
<p style="color: #000; background-color: #fff;">명확한 대비의 텍스트입니다.</p>
```

#### 잘못된 예시 – 대비 부족
```html
<p style="color: #999; background-color: #fff;">가독성이 낮은 텍스트입니다.</p>
```

#### Vue 예시
```vue
<template>
  <p :style="{ color: '#111', backgroundColor: '#f9f9f9' }">
    충분한 명도 대비 텍스트
  </p>
</template>
```

#### React 예시
```jsx
function ContrastText() {
  return (
    <p style={{ color: '#111', backgroundColor: '#ffffff' }}>
      명도 대비가 충분한 텍스트입니다.
    </p>
  );
}
```

#### 7. 점검 기준     

- WCAG 2.2 기준 대비율(4.5:1 또는 3:1)을 충족하는가?    
- 다양한 디스플레이와 해상도에서 텍스트 가독성이 유지되는가?    

#### 8. 점검 방법     

- WebAIM Contrast Checker로 색상 코드 입력 후 분석    
- Chrome 접근성 탭에서 요소별 대비율 확인    
- CSS에서 텍스트 및 배경 색상 명확성 점검    

#### 9. 준수 사례       

<!-- <figure>
<img src="./../images/a11y-web/img-contrast-minimum01.png" alt="">
<figcaption>출처 : 웹 접근성을 고려한 콘텐츠 제작기법 개정판</figcaption>   
</figure> -->
```html
<p style="color: #000; background-color: #fff;">이 문장은 접근성 기준을 충족합니다.</p>
```

#### 10. 미준수 사례       

```html
<p style="color: #ccc; background-color: #fff;">이 문장은 대비 부족으로 기준 미달입니다.</p>
```


#### 11. 관련 영상       
<iframe style="width:100%;min-height:315px;" src="https://www.youtube.com/embed/yW52iPpb-JA?si=UFfksQq0ZdfO-r2H" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[AOA11Y 웹 접근성 (텍스트 콘텐츠의 명도 대비)](https://www.youtube.com/embed/yW52iPpb-JA?si=UFfksQq0ZdfO-r2H){: target="_blank"}    

   
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
