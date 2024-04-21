# INDEX
1. [접근성이란?](01-waStart/waStart.md)
2. [장애인차별금지법 관련 지침](02-waGuideline/waGuideline.md)
3. [접근성 인증 마크](03-waMark/waMark.md)
4. [웹 콘텐츠 접근성 가이드라인](04-waCag/waWcag.md)
   4.1. [WCAG](04-waCag/waWcag.md)
   4.2. [KWCAG](04-waCag/waKwcag.md)
5. 접근성 체크리스트
   - 웹 접근성 - (탭)
   - 모바일 접근성 - (탭)
   - 무인단말기 접근성 - (탭)
6.  접근성을 고려한 콘텐츠 제작 방법
7. 접근성 항목별 준수 가이드
   - 인식의 용이성(perceivable) - (탭)
   - 운용의 용이성(operable) - (탭)
   - 이해의 용이성(understandable) - (탭)
   - 견고성(robust) - (탭)
8. WAI-ARIA 가이드라인
9. WAI-ARIA 구조
   - 역할(Role) 정의 - (탭)
   - 상태(Attributes) 및 속성(States) 정의 - (탭)
10. 역할(Role)
11. 상태(Attributes) 및 속성(States)
12. 무인정보단말기 정보접근성
13. 접근성(a11y) 자가진단 체크리스트
    - 웹 접근성 자가진단 - (탭)
    - 모바일 접근성 자가진단 - (탭)
14.  접근성(a11y) 참조 사이트


---

## 5. 접근성 체크리스트
### 웹 접근성 - tab

### 모바일 접근성 - tab
>모바일 접근성은 모바일 기기 사용자가 앱이나 웹사이트를 이용할 때 겪을 수 있는 장애를 최소화하는 것을 목표로 합니다. 웹 콘텐츠 접근성 가이드라인(WCAG)과 마찬가지로 모바일 접근성도 사용자가 콘텐츠를 인지할 수 있게 하고, 콘텐츠를 운용하며, 콘텐츠를 이해하고, 견고한 콘텐츠를 제공하는 것을 중요하게 여깁니다. 다음은 모바일 접근성을 향상시키기 위한 체크리스트의 예입니다:

1. 인지 가능성
대체 텍스트 사용: 이미지와 아이콘에는 대체 텍스트를 제공하여 시각 장애가 있는 사용자가 콘텐츠를 이해할 수 있도록 합니다.
색상 대비: 텍스트와 배경 간에 충분한 색상 대비를 확보하여 색맹이나 저시력 사용자도 읽기 쉽게 합니다.
확대/축소 지원: 사용자가 콘텐츠를 확대하거나 축소할 수 있도록 지원합니다.
2. 운용 가능성
터치 타깃 크기: 버튼, 링크, 폼 요소 등의 터치 타깃은 충분히 크게 설정하여 사용하기 쉽게 합니다.
제스처 사용 최소화: 필수적이지 않은 복잡한 제스처는 피하고, 가능한 한 단순한 조작으로 서비스를 이용할 수 있도록 합니다.
키보드 접근성: 모든 기능이 외부 키보드를 통해서도 접근 가능해야 합니다.
3. 이해 가능성
명확한 지침과 레이블 제공: 사용자 인터페이스 요소에는 명확한 레이블과 지침을 제공하여 사용자가 이해하기 쉽게 합니다.
오류 수정 제안: 입력 오류가 발생했을 때, 사용자에게 오류를 쉽게 식별하고 수정할 수 있는 방법을 제안합니다.
4. 견고성
크로스 브라우저 호환성: 다양한 브라우저 및 기기에서 앱이나 웹사이트가 제대로 작동하도록 합니다.
보조 기술과의 호환성: 스크린 리더와 같은 보조 기술을 사용하는 사용자가 모든 콘텐츠에 접근할 수 있도록 합니다.

**추가적인 고려 사항**
>오리엔테이션: 앱이나 웹사이트가 가로 및 세로 방향 모두에서 사용할 수 있도록 지원합니다.
멀티미디어 대체 옵션: 비디오나 오디오 콘텐츠에는 자막, 설명서, 수화 번역 등을 제공합니다.
모바일 접근성을 확보하는 것은 다양한 사용자의 경험을 향상시키는 동시에 법적 요구 사항을 충족하는 중요한 단계입니다. 모바일 앱이나 웹사이트를 개발할 때 이러한 체크리스트를 참고하여 접근성을 향상시키는 것이 좋습니다.

### 무인단말기 접근성 - tab

---

## 6. 접근성을 고려한 콘텐츠 제작 방법
접근성을 고려한 콘텐츠 제작은 모든 사용자가 정보를 동등하게 접근하고 이해할 수 있도록 보장하는 것을 목표로 합니다. 다음은 접근성을 고려하여 콘텐츠를 제작하는 몇 가지 방법입니다:

1. 명확하고 읽기 쉬운 텍스트 사용
간결하고 명확한 언어 사용: 전문 용어, 약어, 복잡한 문장 구조를 피하고, 정보를 명확하고 간결하게 전달합니다.
구조적인 텍스트 마크업 사용: 제목, 부제목, 목록 등의 HTML 태그를 사용하여 콘텐츠의 구조를 명확히 합니다. 이는 콘텐츠의 개요를 이해하고, 스크린 리더 사용자가 콘텐츠를 쉽게 탐색할 수 있게 돕습니다.
2. 이미지와 멀티미디어 콘텐츠 접근성 강화
대체 텍스트 제공: 이미지에는 해당 이미지의 내용과 목적을 설명하는 대체 텍스트를 제공합니다.
자막과 수화 번역 제공: 비디오 콘텐츠에는 청각 장애가 있는 사용자를 위해 자막과 수화 번역을 제공합니다.
오디오 설명 추가: 시각 장애가 있는 사용자를 위해 비디오의 중요한 시각적 요소를 설명하는 오디오 설명을 추가합니다.
3. 색상과 시각적 디자인 접근성 향상
적절한 색상 대비 사용: 텍스트와 배경 사이에 충분한 대비를 제공하여 저시력 사용자도 콘텐츠를 쉽게 읽을 수 있도록 합니다.
색상만으로 정보 전달 피하기: 색맹 사용자를 고려하여, 색상만으로 정보를 전달하지 않고, 텍스트나 기타 시각적 단서도 함께 제공합니다.
4. 접근성이 뛰어난 인터랙션 설계
키보드 접근성 보장: 모든 인터랙티브 요소가 키보드만으로도 접근 가능하도록 설계합니다.
적절한 피드백 제공: 사용자의 행동에 대한 적절한 피드백을 제공하여 사용자가 쉽게 이해할 수 있도록 합니다.
포커스 관리: 사용자가 현재 위치를 쉽게 파악할 수 있도록 키보드 포커스를 명확하게 표시합니다.
5. 접근성 검사와 사용자 피드백
접근성 검사 도구 사용: WAVE, AXE와 같은 접근성 검사 도구를 사용하여 콘텐츠의 접근성 문제를 식별하고 수정합니다.
사용자 테스트 실시: 다양한 장애를 가진 사용자들을 포함한 사용자 테스트를 실시하여 접근성 문제를 식별하고 개선합니다.

---

## 7. 접근성 항목별 준수 가이드
### 인식의 용이성(perceivable)
- 신규 자료 통합

### 운용의 용이성(operable)
- 신규 자료 통합

### 이해의 용이성(understandable)
- 신규 자료 통합

### 견고성(robust)
- 신규 자료 통합

## WAI-ARIA 가이드라인
- 신규 자료 통합

## WAI-ARIA 구조
### 역할(Role)
- 신규 자료 통합 및 정리
- 기본 구조 및 설명

### 상태(Attributes) 및 속성(States)
- 신규 자료 통합 및 정리
- 기본 구조 및 설명

## 역할(Role) 
- 신규 자료 통합 및 정리
- 종류 별 상세 설명

1. alert role
2. alertdialog role
3. application role
4. article role
5. banner role
6. button role
7. cell role
8. checkbox role
9. columnheader role
10. combobox role
11. command role
12. comment role
13. complementary role
14. composite role
15. contentinfo role
16. definition role
17. dialog role
18. directory role
19. document structural roles
20. feed role
21. figure role
22. form role
23. generic role
24. grid role
25. gridcell role
26. group role
27. heading role
28. img role
29. input role
30. landmark role
31. link role
32. list role
33. listbox role
34. listitem role
35. log role
36. main role
37. mark role
38. marquee role
39. math role
40. menu role
41. menubar role
42. menuitem role
43. menuitemcheckbox role
44. menuitemradio role
45. meter role
46. navigation role
47. none role
48. note role
49. option role
50. presentation role
51. progressbar role
52. radio role
53. radiogroup role
54. range role
55. region role
56. roletype role
57. row role
58. rowgroup role
59. rowheader role
60. scrollbar role
61. search role
62. searchbox role
63. section role
64. sectionhead role
65. select role
66. separator role
67. slider role
68. spinbutton role
69. status role
70. structure role
71. suggestion role
72. switch role
73. tab role
74. table role
75. tablist role
76. tabpanel role
77. term role
78. textbox role
79. timer role
80. toolbar role
81. tooltip role
82. tree role
83. treegrid role
84. treeitem role
85. widget role
86. window role
87. text role

## 상태(Attributes) 및 속성(States)
- 신규 자료 통합 및 정리
- 종류 별 상세 설명
  
1. aria-activedescendant
2. aria-atomic
3. aria-autocomplete
4. aria-braillelabel
5. aria-brailleroledescription
6. aria-busy
7. aria-checked
8. aria-colcount
9. aria-colindex
10. aria-colindextext
11. aria-colspan
12. aria-controls
13. aria-current
14. aria-describedby
15. aria-description
16. aria-details
17. aria-disabled
18. aria-dropeffectDeprecated
19. aria-errormessage
20. aria-expanded
21. aria-flowto
22. aria-grabbedDeprecated
23. aria-haspopup
24. aria-hidden
25. aria-invalid
26. aria-keyshortcuts
27. aria-label
28. aria-labelledby
29. aria-level
30. aria-live
31. aria-modal
32. aria-multiline
33. aria-multiselectable
34. aria-orientation
35. aria-owns
36. aria-placeholder
37. aria-posinset
38. aria-pressed
39. aria-readonly
40. aria-relevant
41. aria-required
42. aria-roledescription
43. aria-rowcount
44. aria-rowindex
45. aria-rowindextext
46. aria-rowspan
47. aria-selected
48. aria-setsize
49. aria-sort
50. aria-valuemax
51. aria-valuemin
52. aria-valuenow
53. aria-valuetext


```sh
cd dillinger
npm i
node app
```

## 무인정보단말기 정보접근성
- 신규 업데이트
- https://www.khan.co.kr/economy/market-trend/article/202109231513001#csidxf8d9d8b51bed28bbb4fad083122f3af

## 접근성(a11y) 자가진단 체크리스트
### 웹 접근성 자가진단
- 신규 업데이트

---

### 모바일 접근성 자가진단
- 신규 업데이트

---

## 접근성(a11y) 참조 사이트
- 신규 업데이트

---

## 작업하기 위한 참조
https://patrickhlauke.github.io/aria/presentation/?full#66
https://github.com/im-d-team/Dev-Docs/blob/master/HTML/ARIA.md
https://bugs.webkit.org/buglist.cgi?quicksearch=voiceover
https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG
https://a11y.gitbook.io/wcag/references
https://techblog.lotteon.com/%EC%9B%B9%EC%A0%91%EA%B7%BC%EC%84%B1-%EC%A0%90%EA%B2%80-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4-2c102c4eef79
http://210.116.77.11/pbGuide/guide/html/wah/wahGuide2.html
https://blog.naver.com/uramsol/120155676326
https://ableict.tistory.com/entry/%ED%95%9C%EA%B5%AD%ED%98%95%EC%9B%B9%EC%BD%98%ED%85%90%EC%B8%A0%EC%A0%91%EA%B7%BC%EC%84%B1%EC%A7%80%EC%B9%A8-22
https://a11y.gitbook.io/wcag/new-in-wcag-2.1
https://w3c.or.kr/
https://story.pxd.co.kr/1588
https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/feed_role#keyboard_interactions
https://www.w3.org/WAI/ARIA/apg/patterns/feed/examples/feed/
https://studio-jt.co.kr/a11y-level-up-%EC%9B%B9%EC%A0%91%EA%B7%BC%EC%84%B1-%EB%A0%88%EB%B2%A8%EC%97%85/
https://www.aditus.io/contrast-and-accessibility/
https://codingeverybody.kr/html-role-%EC%86%8D%EC%84%B1%EC%9D%98-%ED%99%9C%EC%9A%A9-%EB%B0%A9%EB%B2%95/
https://fossies.org/linux/lighthouse/shared/localization/locales/ko.json
https://dequeuniversity.com/rules/axe/4.8/aria-text
https://accessibilityresources.org/tab
https://www.scwonline.wales/accessibility-statement/report-june.html
https://velog.io/@nalsae/%EC%9A%B4%EC%9A%A9%EC%9D%98-%EC%9A%A9%EC%9D%B4%EC%84%B1