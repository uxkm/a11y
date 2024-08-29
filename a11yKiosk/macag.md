# 접근성 콘텐츠 제작 기법
> 접근성 콘텐츠 제작 기법은 모든 사용자, 특히 장애가 있는 사용자가 웹과 모바일 콘텐츠에 접근하고 사용할 수 있도록 보장하는 방법입니다. 이 기법은 웹 접근성 지침(WCAG: Web Content Accessibility Guidelines)과 모바일 접근성 표준을 따르는 것이 중요합니다. 각각의 영역에 대해 접근성 작업 시 도움이 될 수 있도록 작업되었습니다. 접근성은 법적 요구사항일 뿐만 아니라 사용자를 위한 기본적인 배려이기도 합니다.  
참고사항 : 사용되는 예시 사이트들은 무작위로 검색하여 샘플로 작업되었습니다.   

## 모바일 앱 접근성

개선 전 / 개선 후
오류항목
검사방법
음성테스트


1. **대체 텍스트**   
   - 텍스트 아닌 콘텐츠는 대체 가능한 텍스트와 함께 제공되어야 한다.
2. **자막, 수화 등의 제공**   
   - 영상이나 음성 콘텐츠에는 동등한 내용의 자막, 원고 또는 수화가 제공되어야 한다.
3. **색에 무관한 인식**   
   - 화면에 표시되는 모든 정보는 색에 관계없이 인식될 수 있어야 한다.
4. **명도 대비**   
   - 화면에 표시되는 모든 사용자 인터페이스 컴포넌트와 텍스트는 전경색과 배경색이 구분될 수 있도록 제공되어야 한다.
5. **명확한 지시 사항** 
   - 지시 사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.
6. **알림 기능** 
   - 알림 정보는 화면 표시, 소리, 진동 등 다양한 방법으로 제공되어야 한다.
7. **초점** 
   - 의미나 기능을 갖는 모든 사용자 인터페이스 컴포넌트에는 초점(focus)이 적용되고, 초점은 논리적인 순서로 이동되어야 한다.
8. **누르기 동작 지원** 
   - 터치(touch) 기반 모바일 기기의 모든 컨트롤은 누르기 동작으로 제어할 수 있어야 한다.
9.  **응답 시간 조절** 
    - 시간 제한이 있는 콘텐츠는 응답 시간을 조절할 수 있어야 한다.
10. **정지 기능 제공** 
    - 자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.
11. **컨트롤의 크기와 간격** 
    - 컨트롤은 충분한 크기와 간격으로 제공되어야 한다.
12. **입력 도움** 
    - 입력 서식 이용 시, 입력 오류를 방지하거나 정정할 수 있는 방법을 제공해야 한다.
13. **사용자 인터페이스의 일관성** 
    - 사용자 인터페이스 컴포넌트들은 일관성 있게 배치되어야 한다.
14. **깜박거림의 사용 제한** 
    - 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.
15. **자동재생 금지** 
    - 자동으로 재생되는 배경음을 사용하지 않아야 한다.
16. **예측가능성** 
    - 사용자가 의도하지 않는 화면 전환이나 이벤트 등이 실행되는 경우 사용자가 이해할 수 있는 방법으로 제공되어야 한다.
17. **폰트 관련 기능의 활용** 
    - 텍스트 콘텐츠는 운영체제에서 제공하는 폰트 관련 기능을 활용할 수 있는 방법을 제공해야 한다.
18. **보조 기술과의 호환성** 
    - 사용자 인터페이스 컴포넌트는 보조 기술을 이용하여 사용할 수 있도록 해야 한다.


```sh
cd dillinger
npm i
node app
```



### 참조
- [W3C Mobile Accessibility at W3C](https://www.w3.org/WAI/standards-guidelines/mobile/){: target="_blank"}
- [W3C Mobile Accessibility: How WCAG 2.0 and Other W3C/WAI Guidelines Apply to Mobile](https://www.w3.org/TR/mobile-accessibility-mapping/){: target="_blank"}
- [W3C First Public Working Draft](https://www.w3.org/news/2015/first-public-working-draft-performance-timeline-level-2/){: target="_blank"}
- [W3C User Agent Accessibility Guidelines (UAAG) 2.0](https://www.w3.org/TR/UAAG20/){: target="_blank"}
- [W3C Mobile Accessibility Examples from UAAG 2.0 Reference](https://www.w3.org/TR/IMPLEMENTING-UAAG20/mobile.html){: target="_blank"}
- [MDN Mobile accessibility checklist](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Mobile_accessibility_checklist){: target="_blank"}
- [보건복지부 블로그](https://blog.naver.com/prologue/PrologueList.naver?blogId=mohw2016){: target="_blank"}
