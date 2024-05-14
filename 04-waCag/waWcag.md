## 4. 웹 콘텐츠 접근성 가이드라인

### 4.1 WCAG
>**웹 콘텐츠 접근성 가이드라인(WCAG - Web Content Accessibility Guidelines)** 은 웹사이트와 온라인 서비스를 모든 사용자가 접근할 수 있도록 만드는 국제 표준 문서입니다.
이 문서에서 제공된 원칙들을 따르기 위한 구체적인 기준을 제공하며, 
각 기준은 세 가지 준수 수준(**A, AA, AAA**)으로 구분됩니다. 
**A**: 최소 수준, **AA**: 중간 수준, **AAA**: 가장 높은 수준의 접근성을 의미합니다.

#### 4.1.1 WCAG 적합성 수준
1. **Level A**
   - 최소 수준의 적합성(광범위한 접근성을 달성 하지는 못함)
   - 가장 기본적인 접근성 성공 기준이 포함되어 있습니다.
   - 기본적인 만큼 Level A에 해당하는 성공 기준을 만족하지 않으면 다양한 유형의 사용자가 해당 웹 페이지를 전혀 사용할 수 없습니다.
2. **Level AA**
   - 가장 일반적인 수준의 적합성 (대부분의 법률 및 공식 요구 사항으로 준수를 권장)
   - Level A처럼 준수하지 않았을 때 전혀 사용할 수 없는 수준은 아니지만, 다양한 유형의 사용자가 동등하게 웹 페이지를 사용하기 위해 꼭 필요한 성공 기준을 포함합니다.
   - 일반적으로 웹 페이지의 접근성 요구 사항(VPAT)은 Level AA를 만족해야 합니다.
3. **Level AAA**
   - 어려운 수준의 적합성 (매우 까다롭고, 구현에 많은 시간이 요구됨)
   - WCAG가 규정하는 가장 높은 수준의 접근성 기준을 만족하기 위한 성공 기준을 포함합니다.

#### 4.1.2 접근성 적합성 수준의 준수 예시
**예) 오디오와 비디오 같은 미디어의 경우** 
1. **A** - 시각 및 청각 정보를 올바른 순서로 제공하는 텍스트 설명 등이 필요.
2. **AA** - 실시간 오디오 콘텐츠에 실시간 자막을 제공.
3. **AAA** - 사전 녹음된 오디오 콘텐츠에 수어 통역을 제공을 하는 등.
4. 국제 디지털 출판 포럼인 IDPF(International Digital Publishing Forum)에서 제정한 전자 출판물 표준인 EPUB(Electronic PUBlication) 출판물의 경우 반드시 수준 A를 충족해야 하지만 **AA는 준수하는 것을 권고**하고 있는 상황.

#### 4.1.3 WCAG 버전
최신 버전은 2023년 10월 5일 권고사항으로 WCAG 2.2 이며, 4가지 주요 원칙에 기반을 두고 있습니다.
1. WCAG 1.0 (1999) 제정
   - 1999년에 출간.
   - 14개의 가이드라인을 우선 순위에 따라 1~3점으로 구분하여 평가.
   - 접근성 가이드라인이 생겼다는 점에서는 큰 의미가 있지만, 웹 페이지가 제작되는 방식이나 보조기술 등이 급격히 발전 함에 따라 가이드라인이 해당 기술을 따라가지 못했다는 면에서 한계를 들어내기도 했습니다.
2. WCAG 1.0 개정
3. WCAG 2.0 (2008)
   - 2008년에 발표.
   - 1.0의 준수사항을 모두 통합하면서, 콘텐츠를 인지 가능하고 조작 가능하며 이해할 수 있고 견고해야 한다는 4가지 원칙으로 구조가 개편.
   - 구분된 원칙에 따라 장애가 있는 사용자가 웹 콘텐츠를 보다 쉽게 접근할 수 있도록 하기 위한 기본 목표를 제시하는 12개 가이드라인을 제시. 
   - 4가지 원칙(인지 가능, 운용 가능, 이해 가능, 견고성)도 확립.
4. WCAG 2.0 (2010) 개정
5. WCAG 2.1 (2015) 개정
6. WCAG 2.1 (2018) 권고안
   - WCAG 2.0을 확장한 버전으로 2018년 6월에 최종 권고안이 발표됨.
   - 2.0 가이드라인 자체를 대체하는 것이 아니라, 장애가 있는 사람들의 모바일 장치 사용, 저시력, 인지 또는 학습 장애를 가진 사람들이 웹 콘텐츠에 보다 쉽게 접근할 수 있도록 만드는 요구 사항 중 일부를 개선.
   - 17개의 새로운 가이드라인(성공기준)을 제공.
   - 2.0이 출시 되었던 당시(2008) 보다 모바일 장치 사용률이 높아졌고 기존 환경보다 조작 자체가 복잡해진 점 등을 고려.
   - 이전 버전의 WCAG를 개선하기 위해 지속적으로 연구된 개발 성과물.
   - WCAG 2.0과 호환 되므로 웹 사이트가 2.1에 부합하면 2.0에도 부합하는 것입니다.
   - WCAG 2.1의 새로운 요구 사항은 2.0과 마찬가지로 특정 장치, 운영 체제, 브라우저 또는 기타 기술 사용에 의존하지 않음.
7. WCAG 2.2 (2020) 초안
8. WCAG 2.2 (2022) 개정
   - 2.1 기준에서 9개 성공기준 새로 추가.
9. WCAG 2.2 (2023) 권고
10. WCAG 3.0 (2023) 초기단계(Draft)
    - 2.2 버전의 다음 버전.
    - WCAG 3.0은 웹 콘텐츠, 앱, 도구, 출판, 웹상의 신기술에 적용됩니다.

#### 4.1.4 WCAG 2.1 4가지 원칙
1. **인지 가능성(Perceivable)**
   - 사용자가 정보를 인지하고 콘텐츠를 볼 수 있어야 합니다.
   - 예) 시각적 콘텐츠는 대체 텍스트를 통해 설명되어야 하며, 오디오 콘텐츠는 자막이나 수화 번역을 통해 제공되어야 합니다.
2. **운용 가능성(Operable)**
   - 사용자가 콘텐츠의 인터페이스 요소를 운용할 수 있어야 합니다.
   - 이는 웹사이트가 키보드만으로도 전체적으로 사용될 수 있어야 하며, 충분한 시간을 제공하고, 발작을 유발할 수 있는 콘텐츠를 피하는 것을 의미합니다.
3. **이해 가능성(Understandable)**
   - 사용자가 정보와 인터페이스의 운용 방식을 이해할 수 있어야 합니다.
   - 이는 웹 페이지가 예측 가능하게 작동하며, 사용자가 실수를 할 경우 이를 정정할 수 있는 방법을 제공해야 함을 의미합니다.
4. **견고성(Robust)**
   - 다양한 사용자 에이전트(브라우저 등)와 보조 기술에서 콘텐츠를 정확하게 해석할 수 있어야 합니다.
   - 이는 웹 콘텐츠가 현재 및 미래의 기술과 호환될 수 있도록 보장합니다.

#### 4.1.5 WCAG 2.1 지침별 성공기준과 적합성 수준 개수
WCAG 전체 성공기준 개수 - 78개
1. **인지 가능성(Perceivable)**
   - 1.1 대체 텍스트(A - 1개 / 총 1개)
   - 1.2 시간 기반 미디어(A - 3개, AA - 2개, AAA - 4개 / 총 9개)
   - 1.3 적응성(A - 3개, AA - 3개 / 총 6개)
   - 1.4 명료성(A - 2개, AA - 7개, AAA - 4개 / 총 13개)
2. **운용 가능성(Operable)**
   - 2.1 키보드 접근(A - 3개, AAA - 1개 / 총 4개)
   - 2.2 충분한 시간 제공(A - 2개, AAA - 4개 / 총 6개)
   - 2.3 발작 예방(A - 1개, AAA - 2개 / 총 3개)
   - 2.4 탐색 가능(A - 4개, AA - 3개, AAA - 3개 / 총 10개)
   - 2.5 입력 양식(A - 4개, AAA - 2개 / 총 6개)
3. **이해 가능성(Understandable)**
   - 3.1 가독성(A - 1개, AA - 1개, AAA - 4개 / 총 6개)
   - 3.2 예측 가능성(A - 2개, AA - 2개, AAA - 2개 / 총 6개)
4. **견고성(Robust)**
   - 4.1 호환성(A - 2개, AA - 1개 / 총 3개)

#### 4.1.6 WCAG 2.2에 새로 추가된 성공 기준(Success Criteria)
- **2.4.11 Focus Not Obscured (Minimum)(AA)**
- **2.4.12 Focus Not Obscured (Enhanced)(AAA)**
- **2.4.13 Focus Appearance(AAA)**
- **2.5.7 Dragging Movements(AA)**
- **2.5.8 Target Size (Minimum)(AA)**
- **3.2.6 Consistent Help(A)**
- **3.3.7 Redundant Entry(A)**
- **3.3.8 Accessible Authentication (Minimum)(AA)**
- **3.3.9 Accessible Authentication (Enhanced)(AAA)**

>9개의 성공 기준의 타깃 사용자는 운동장애 사용자, 고령자(Retiree), 인지장애 및 학습장애 사용자, 저시력 사용자가 주 대상입니다.

#### 4.1.7 WCAG 2.2에 제거된 성공 기준(Success Criteria)
- **4.1.1 구문 분석(더 이상 사용되지 않으며 제거됨)**
 
>이 기준은 원래 보조 기술이 HTML을 직접 분석하는 문제를 해결하기 위해 도입되었습니다. 하지만, 시간이 지나면서 보조 기술은 HTML을 직접 분석할 필요가 없어졌고, 브라우저들은 마크업의 구문 분석 오류를 처리하는 능력이 크게 향상되었습니다. 결과적으로, 정확한 마크업 구조는 더 이상 필수 요소가 아니게 되었습니다. 따라서 이 기준은 그 유용성이 사라져 삭제되었습니다.
단, 다른 기준에서 확장되어 세부적인 내용들이 추가되었습니다.

#### 4.1.8 접근성 용어정리
1. ATAG(웹 저작 도구 접근성 지침)
   - Authoring Tool Accessibility Guildelines의 약자로 접근 가능한 콘텐츠를 생성하는 접근 가능한 작성 도구를 구축하기 위한 W3C 권장 사항입니다.
   - 저작도구는 “저자” (웹 개발자, 디자이너, 작가 등)가 웹 콘텐츠를 생산하는 데에 사용하는 서비스나 소프트웨어를 가리킵니다. 
   - 예) HTML 에디터, 콘텐츠 관리 시스템 (CMS) 그리고 사용자가 콘텐츠를 생산할 수 있는 블로그나 소셜 네트워킹 사이트가 있습니다.
   - 목표로는 저작도구의 접근성을 보장하여 장애가 있는 사용자가 웹 콘텐츠를 생산할 수 있도록 하고, 저자가 더 접근성이 좋은 웹 콘텐츠를 생산하는 것을 돕는데 있습니다.
2. UAAG(사용자 에이전트 접근성 지침)
   - User Agent Accessibility Guidelines의 약자로 사용자 에이전트는 브라우저, 브라우저 확장프로그램, 미디어 플레이어, 리더기와 같은 웹 콘텐츠를 제공하는 어플리케이션을 포함합니다.
3. WAI-ARIA(접근가능한 리치 인터넷 어플리케이션)
   - Web Accessibility Initiative's Accessible Rich Internet Applications의 약자로 스크린리더가 브라우저를 읽을 때 각 요소가 어떤 역할을 하는지 무슨 의미로 존재하는지 알 수 있도록 하기 위해 만들어진 기술이다.
   - ARIA는 의미를 제공하여 저자가 유저 인터페이스 행동이나 구조적 정보를 스크린 리더와 같은 보조 기술에 전달할 수 있게 합니다. ARIA 기술 명세는 역할, 상태, 접근 가능한 유저 인터페이스 요소로 정의되는 속성들의 온톨로지를 제공합니다.
   - ARIA 모음은 유저 에이전트 실행 지침을 제공하는 명세를 모은 API를 포함합니다. 그래픽, 디지털 출판을 위한 모듈 또한 포함됩니다.
   - WAI : 'Web Internet Applications'의 약자로 웹 접근성을 담당하는 조직.
   - ARIA : 'Accessible Rich Internet Applications'의 약자로 리치 인터넷을 위한 W3C 접근성 명세.

#### 4.1.8 참조
[W3C WCAG 1.0](https://www.w3.org/TR/WCAG10/)
[W3C WCAG 2.0](https://www.w3.org/TR/WCAG20/)
[W3C WCAG 2.1](https://www.w3.org/TR/WCAG21/)
[W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/)
[W3C WCAG 3.0 Draft](https://www.w3.org/TR/2021/WD-wcag-3.0-20210121/)
[W3C WCAG 2.1 한국어](http://www.kwacc.or.kr/WAI/wcag21/)
[W3C Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/)
[W3C WCAG2 ko](https://www.w3.org/WAI/standards-guidelines/ko#wcag2)
[W3C Accessibility Guidelines Working Group](https://www.w3.org/WAI/GL/)
[W3C W3C 접근성의 4가지 원칙](https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head)
[MDN 웹 컨텐츠 접근성 지침 이해하기](https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG)
[MDN 접근성이란?](https://developer.mozilla.org/ko/docs/Learn/Accessibility/What_is_accessibility#accessibility_guidelines_and_the_law)
[NULI WCAG 2.2에서 변경된 사항](https://nuli.navercorp.com/community/article/1133181)
[brunch WCAG 2.2 작업 초안](https://brunch.co.kr/@snclab/55)
[GITBOOK WCAG 2.1](https://a11y.gitbook.io/wcag/international-standards)
[WAI 문서로 접근성 이해하기](https://iyu88.github.io//a11y/2023/12/24/web-accessibility-1.html)
[deque blog WCAG 2.1](https://www.deque.com/blog/wcag-2-1-what-is-next-for-accessibility-guidelines/)
[웹접근성 국가표준 개정 소개](https://seculayerlab.tistory.com/m/48)

[한국형 웹 콘텐츠 접근성 지침 2.2](https://www.samsungfashion.com/webacc.do)



https://www.w3.org/TR/WCAG22/#parsing
https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head
https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG
https://experienceleague.adobe.com/ko/docs/experience-manager-65/content/managing/accessibility/qg-wcag
https://www.w3.org/WAI/standards-guidelines/wcag/
https://www.w3.org/WAI/standards-guidelines/wcag/faq/
https://www.w3.org/WAI/standards-guidelines/wcag/wcag3-intro/
https://www.w3.org/WAI/standards-guidelines/ko
https://www.atlassian.com/ko/trust/compliance/resources/wcag
https://naradesign.github.io/wcag-2.1.html
https://docs.tobesoft.co.jp/improvement_a11y_guide_nexacro_n_ko/596cf126a44ae630
https://velog.io/@liketiger/WCAGWeb-Content-Accessibility-Guidelines#1-wcag%EB%9E%80
https://a11y.gitbook.io/wcag/1-perceivable/1.1-text-alternatives
https://mulder21c.io/understanding-kwcag-22-changes-intro/
https://a11y.gitbook.io/wcag/international-standards
https://brunch.co.kr/@snclab/41
https://brunch.co.kr/@snclab/55
https://accessibleweb.com/wcag/wcag-version-history/
https://www.w3.org/WAI/GL/task-forces/silver/wiki/Major_Milestones_for_Silver
https://www.w3.org/TR/2021/WD-wcag-3.0-20210121/
https://seculayerlab.tistory.com/m/48
https://www.w3.org/WAI/standards-guidelines/ko
http://www.websoul.co.kr/accessibility/WA_guide22.asp
http://www.kwacc.or.kr/WAI/wcag21/#conformance-to-wcag-2-1
https://www.achecks.org/wcag-2-2-is-live-october-5-2023/
https://www.w3.org/WAI/standards-guidelines/ko
https://velog.io/@dadak/ReactTIL
https://velog.io/@yeonni/WCAG-2.2-Update
https://uxdesign.cc/wcag-2-2-parsing-the-success-criterion-that-didnt-make-it-ab8d4904328e

https://oneoneone.kr/content/c635d9c3












