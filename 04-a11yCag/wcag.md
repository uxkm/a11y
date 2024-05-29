## 4. 접근성 가이드라인

### 4.1 웹 콘텐츠 접근성
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

#### 4.1.4 W3C 표준화 제정 단계
> Rescinded Recommendation (철회 권고) 

<img src="https://nuli.navercorp.com/upload/2021/7f75e859-5ba1-4962-ad25-5bcbedd02496_[%EC%A0%91%EA%B7%BC%EC%84%B1]%EC%95%84%ED%8B%B0%ED%81%B4_WCAG3.png" alt="W3C 표준화 제정 단계 : 웹 기술을 표준화하기 위한 절차와 요구 사항">
[이미지 출처 : NULI]

#### 4.1.5 WCAG 2.1 4가지 원칙
>WCAG 2.1은 터치를 이용한 상호작용(Interaction)을 지원하고 보다 복잡한 제스처(gestures)를 처리하며 의도하지 않은 인터페이스 활성화를 방지함으로써 모바일 기기 사용자를 위한 가이드 라인으로 17개의 새로운 성공 기준을 제공합니다. 모바일 기능을 더욱 친근하게 개선하고 최종 사용자에게 최고의 사용성을 제공하기 위한 것입니다.
1. **Perceivable(인지 가능성)**
   - 사용자가 정보를 인지하고 콘텐츠를 볼 수 있어야 합니다.
   - 예) 시각적 콘텐츠는 대체 텍스트를 통해 설명되어야 하며, 오디오 콘텐츠는 자막이나 수화 번역을 통해 제공되어야 합니다.
2. **Operable(운용 가능성)**
   - 사용자가 콘텐츠의 인터페이스 요소를 운용할 수 있어야 합니다.
   - 이는 웹사이트가 키보드만으로도 전체적으로 사용될 수 있어야 하며, 충분한 시간을 제공하고, 발작을 유발할 수 있는 콘텐츠를 피하는 것을 의미합니다.
3. **Understandable(이해 가능성)**
   - 사용자가 정보와 인터페이스의 운용 방식을 이해할 수 있어야 합니다.
   - 이는 웹 페이지가 예측 가능하게 작동하며, 사용자가 실수를 할 경우 이를 정정할 수 있는 방법을 제공해야 함을 의미합니다.
4. **견고성(Robust)**
   - 다양한 사용자 에이전트(브라우저 등)와 보조 기술에서 콘텐츠를 정확하게 해석할 수 있어야 합니다.
   - 이는 웹 콘텐츠가 현재 및 미래의 기술과 호환될 수 있도록 보장합니다.

#### 4.1.6 WCAG 2.1 Guideline(가이드라인)
1. **[인지 가능성(Perceivable)](https://www.w3.org/TR/WCAG21/#perceivable)**
   - [1.1 Text Alternatives(대체 텍스트)](https://www.w3.org/TR/WCAG21/#text-alternatives)
   - [1.2 Time-based Media(시간 기반 미디어)](https://www.w3.org/TR/WCAG21/#time-based-media)
   - [1.3 Adaptable(적응성)](https://www.w3.org/TR/WCAG21/#adaptable)
   - [1.4 Distinguishable(명료성)](https://www.w3.org/TR/WCAG21/#distinguishable)
2. **[운용 가능성(Operable)](https://www.w3.org/TR/WCAG21/#operable)**
   - [2.1 Keyboard Accessible(키보드 접근)](https://www.w3.org/TR/WCAG21/#keyboard-accessible)
   - [2.2 Enough Time(충분한 시간 제공)](https://www.w3.org/TR/WCAG21/#enough-time)
   - [2.3 Seizures and Physical Reactions(발작 예방)](https://www.w3.org/TR/WCAG21/#seizures-and-physical-reactions)
   - [2.4 Navigable(탐색 가능)](https://www.w3.org/TR/WCAG21/#navigable)
   - [2.5 Input Modalities(입력 양식) [New]](https://www.w3.org/TR/WCAG21/#input-modalities)
3. **[이해 가능성(Understandable)](https://www.w3.org/TR/WCAG21/#understandable)**
   - [3.1 Readable(가독성)](https://www.w3.org/TR/WCAG21/#readable)
   - [3.2 Predictable(예측 가능성)](https://www.w3.org/TR/WCAG21/#predictable)
   - [3.3 Input Assistance(입력 지원)](https://www.w3.org/TR/WCAG21/#input-assistance)
4. **[견고성(Robust)](https://www.w3.org/TR/WCAG21/#robust)**
   - [4.1 Compatible(호환성)](https://www.w3.org/TR/WCAG21/#compatible)

#### 4.1.7 WCAG 2.1 Success Criterion(성공 기준)
WCAG 전체 성공 기준 - 총 78 개(A 30 개, AA 20 개, AAA 28 개)
- [1.1.1 Non-text Content (Level A)](https://www.w3.org/TR/WCAG21/#non-text-content) 
- [1.2.1 Audio-only and Video-only (Prerecorded) (Level A)](https://www.w3.org/TR/WCAG21/#audio-only-and-video-only-prerecorded) 
- [1.2.2 Captions (Prerecorded) (Level A)](https://www.w3.org/TR/WCAG21/#captions-prerecorded) 
- [1.2.3 Audio Description or Media Alternative (Prerecorded) (Level A)](https://www.w3.org/TR/WCAG21/#audio-description-or-media-alternative-prerecorded) 
- [1.2.4 Captions (Live) (Level AA)](https://www.w3.org/TR/WCAG21/#captions-live) 
- [1.2.5 Audio Description (Prerecorded) (Level AA)](https://www.w3.org/TR/WCAG21/#audio-description-prerecorded) 
- [1.2.6 Sign Language (Prerecorded) (Level AAA)](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded) 
- [1.2.7 Extended Audio Description (Prerecorded) (Level AAA)](https://www.w3.org/TR/WCAG21/#extended-audio-description-prerecorded) 
- [1.2.8 Media Alternative (Prerecorded) (Level AAA)](https://www.w3.org/TR/WCAG21/#media-alternative-prerecorded) 
- [1.2.9 Audio-only (Live) (Level AAA)](https://www.w3.org/TR/WCAG21/#audio-only-live) 
- [1.3.1 Info and Relationships (Level A)](https://www.w3.org/TR/WCAG21/#info-and-relationships) 
- [1.3.2 Meaningful Sequence (Level A)](https://www.w3.org/TR/WCAG21/#meaningful-sequence) 
- [1.3.3 Sensory Characteristics (Level A)](https://www.w3.org/TR/WCAG21/#sensory-characteristics) 
- [1.3.4 Orientation (Level AA)](https://www.w3.org/TR/WCAG21/#orientation) 
- [1.3.5 Identify Input Purpose (Level AA)](https://www.w3.org/TR/WCAG21/#identify-input-purpose) 
- [1.3.6 Identify Purpose (Level AAA)](https://www.w3.org/TR/WCAG21/#identify-purpose) 
- [1.4.1 Use of Color (Level A)](https://www.w3.org/TR/WCAG21/#use-of-color) 
- [1.4.2 Audio Control (Level A)](https://www.w3.org/TR/WCAG21/#audio-control) 
- [1.4.3 Contrast (Minimum) (Level AA)](https://www.w3.org/TR/WCAG21/#contrast-minimum) 
- [1.4.4 Resize Text (Level AA)](https://www.w3.org/TR/WCAG21/#resize-text) 
- [1.4.5 Images of Text (Level AA)](https://www.w3.org/TR/WCAG21/#images-of-text) 
- [1.4.6 Contrast (Enhanced) (Level AAA)](https://www.w3.org/TR/WCAG21/#contrast-enhanced) 
- [1.4.7 Low or No Background Audio (Level AAA)](https://www.w3.org/TR/WCAG21/#low-or-no-background-audio) 
- [1.4.8 Visual Presentation (Level AAA)](https://www.w3.org/TR/WCAG21/#visual-presentation) 
- [1.4.9 Images of Text (No Exception) (Level AAA)](https://www.w3.org/TR/WCAG21/#images-of-text-no-exception) 
- [1.4.10 Reflow (Level AA)](https://www.w3.org/TR/WCAG21/#reflow) 
- [1.4.11 Non-text Contrast (Level AA)](https://www.w3.org/TR/WCAG21/#non-text-contrast) 
- [1.4.12 Text Spacing (Level AA)](https://www.w3.org/TR/WCAG21/#text-spacing) 
- [1.4.13 Content on Hover or Focus (Level AA)](https://www.w3.org/TR/WCAG21/#content-on-hover-or-focus) 
- [2.1.1 Keyboard (Level A)](https://www.w3.org/TR/WCAG21/#keyboard) 
- [2.1.2 No Keyboard Trap (Level A)](https://www.w3.org/TR/WCAG21/#no-keyboard-trap) 
- [2.1.3 Keyboard (No Exception) (Level AAA)](https://www.w3.org/TR/WCAG21/#keyboard-no-exception) 
- [2.1.4 Character Key Shortcuts (Level A)](https://www.w3.org/TR/WCAG21/#character-key-shortcuts) 
- [2.2.1 Timing Adjustable (Level A)](https://www.w3.org/TR/WCAG21/#timing-adjustable) 
- [2.2.2 Pause, Stop, Hide (Level A)](https://www.w3.org/TR/WCAG21/#pause-stop-hide) 
- [2.2.3 No Timing (Level AAA)](https://www.w3.org/TR/WCAG21/#no-timing) 
- [2.2.4 Interruptions (Level AAA)](https://www.w3.org/TR/WCAG21/#interruptions) 
- [2.2.5 Re-authenticating (Level AAA)](https://www.w3.org/TR/WCAG21/#re-authenticating) 
- [2.2.6 Timeouts (Level AAA)](https://www.w3.org/TR/WCAG21/#timeouts) 
- [2.3.1 Three Flashes or Below Threshold (Level A)](https://www.w3.org/TR/WCAG21/#three-flashes-or-below-threshold) 
- [2.3.2 Three Flashes (Level AAA)](https://www.w3.org/TR/WCAG21/#three-flashes) 
- [2.3.3 Animation from Interactions (Level AAA)](https://www.w3.org/TR/WCAG21/#animation-from-interactions) 
- [2.4.1 Bypass Blocks (Level A)](https://www.w3.org/TR/WCAG21/#bypass-blocks) 
- [2.4.2 Page Titled (Level A)](https://www.w3.org/TR/WCAG21/#page-titled) 
- [2.4.3 Focus Order (Level A)](https://www.w3.org/TR/WCAG21/#focus-order) 
- [2.4.4 Link Purpose (In Context) (Level A)](https://www.w3.org/TR/WCAG21/#link-purpose-in-context) 
- [2.4.5 Multiple Ways (Level AA)](https://www.w3.org/TR/WCAG21/#multiple-ways) 
- [2.4.6 Headings and Labels (Level AA)](https://www.w3.org/TR/WCAG21/#headings-and-labels) 
- [2.4.7 Focus Visible (Level AA)](https://www.w3.org/TR/WCAG21/#focus-visible) 
- [2.4.8 Location (Level AAA)](https://www.w3.org/TR/WCAG21/#location) 
- [2.4.9 Link Purpose (Link Only) (Level AAA)](https://www.w3.org/TR/WCAG21/#link-purpose-link-only) 
- [2.4.10 Section Headings (Level AAA)](https://www.w3.org/TR/WCAG21/#section-headings) 
- [2.5.1 Pointer Gestures (Level A)](https://www.w3.org/TR/WCAG21/#pointer-gestures) 
- [2.5.2 Pointer Cancellation (Level A)](https://www.w3.org/TR/WCAG21/#pointer-cancellation) 
- [2.5.3 Label in Name (Level A)](https://www.w3.org/TR/WCAG21/#label-in-name) 
- [2.5.4 Motion Actuation (Level A)](https://www.w3.org/TR/WCAG21/#motion-actuation) 
- [2.5.5 Target Size (Level AAA)](https://www.w3.org/TR/WCAG21/#target-size) 
- [2.5.6 Concurrent Input Mechanisms (Level AAA)](https://www.w3.org/TR/WCAG21/#concurrent-input-mechanisms) 
- [3.1.1 Language of Page (Level A)](https://www.w3.org/TR/WCAG21/#language-of-page) 
- [3.1.2 Language of Parts (Level AA)](https://www.w3.org/TR/WCAG21/#language-of-parts) 
- [3.1.3 Unusual Words (Level AAA)](https://www.w3.org/TR/WCAG21/#unusual-words) 
- [3.1.4 Abbreviations (Level AAA)](https://www.w3.org/TR/WCAG21/#abbreviations) 
- [3.1.5 Reading Level (Level AAA)](https://www.w3.org/TR/WCAG21/#reading-level) 
- [3.1.6 Pronunciation (Level AAA)](https://www.w3.org/TR/WCAG21/#pronunciation) 
- [3.2.1 On Focus (Level A)](https://www.w3.org/TR/WCAG21/#on-focus) 
- [3.2.2 On Input (Level A)](https://www.w3.org/TR/WCAG21/#on-input) 
- [3.2.3 Consistent Navigation (Level AA)](https://www.w3.org/TR/WCAG21/#consistent-navigation) 
- [3.2.4 Consistent Identification (Level AA)](https://www.w3.org/TR/WCAG21/#consistent-identification) 
- [3.2.5 Change on Request (Level AAA)](https://www.w3.org/TR/WCAG21/#change-on-request) 
- [3.3.1 Error Identification (Level A)](https://www.w3.org/TR/WCAG21/#error-identification) 
- [3.3.2 Labels or Instructions (Level A)](https://www.w3.org/TR/WCAG21/#labels-or-instructions) 
- [3.3.3 Error Suggestion (Level AA)](https://www.w3.org/TR/WCAG21/#error-suggestion) 
- [3.3.4 Error Prevention (Legal, Financial, Data) (Level AA)](https://www.w3.org/TR/WCAG21/#error-prevention-legal-financial-data) 
- [3.3.5 Help (Level AAA)](https://www.w3.org/TR/WCAG21/#help) 
- [3.3.6 Error Prevention (All) (Level AAA)](https://www.w3.org/TR/WCAG21/#error-prevention-all) 
- [4.1.1 Parsing (Level A)](https://www.w3.org/TR/WCAG21/#parsing) 
- [4.1.2 Name, Role, Value (Level A)](https://www.w3.org/TR/WCAG21/#name-role-value) 
- [4.1.3 Status Messages (Level AA)](https://www.w3.org/TR/WCAG21/#status-messages) 


#### 4.1.8 WCAG 2.2에 새로 추가된 Success Criterion(성공 기준)
>WCAG 2.2에서는 9개의 성공 기준의 타깃 사용자는 운동장애 사용자, 고령자(Retiree), 인지장애 및 학습장애 사용자, 저시력 사용자가 주 대상입니다.
- **[2.4.11 Focus Not Obscured (Minimum) (AA)](https://www.w3.org/TR/WCAG22/#focus-not-obscured-minimum)**
- **[2.4.12 Focus Not Obscured (Enhanced) (AAA)](https://www.w3.org/TR/WCAG22/#focus-not-obscured-enhanced)**
- **[2.4.13 Focus Appearance (AAA)](https://www.w3.org/TR/WCAG22/#focus-appearance)**
- **[2.5.7 Dragging Movements (AA)](https://www.w3.org/TR/WCAG22/#dragging-movements)**
- **[2.5.8 Target Size (Minimum) (AA)](https://www.w3.org/TR/WCAG22/#target-size-minimum)**
- **[3.2.6 Consistent Help (A)](https://www.w3.org/TR/WCAG22/#consistent-help)**
- **[3.3.7 Redundant Entry (A)](https://www.w3.org/TR/WCAG22/#redundant-entry)**
- **[3.3.8 Accessible Authentication (Minimum) (AA)](https://www.w3.org/TR/WCAG22/#accessible-authentication-minimum)**
- **[3.3.9 Accessible Authentication (Enhanced) (AAA)](https://www.w3.org/TR/WCAG22/#accessible-authentication-enhanced)**


#### 4.1.9 WCAG 2.2에 제거된 Success Criterion(성공 기준)
>이 기준은 원래 보조 기술이 HTML을 직접 분석하는 문제를 해결하기 위해 도입되었습니다. 하지만, 시간이 지나면서 보조 기술은 HTML을 직접 분석할 필요가 없어졌고, 브라우저들은 마크업의 구문 분석 오류를 처리하는 능력이 크게 향상되었습니다. 결과적으로, 정확한 마크업 구조는 더 이상 필수 요소가 아니게 되었습니다. 따라서 이 기준은 그 유용성이 사라져 삭제되었습니다.
단, 다른 기준에서 확장되어 세부적인 내용들이 추가되었습니다.
- **[4.1.1 Parsing (Obsolete and removed) (구문 분석(사용되지 않고 제거됨))](https://www.w3.org/TR/WCAG22/#parsing)**


#### 4.1.10 접근성 용어정리
1. **ATAG(웹 저작 도구 접근성 지침)**
   - Authoring Tool Accessibility Guildelines의 약자로 접근 가능한 콘텐츠를 생성하는 접근 가능한 작성 도구를 구축하기 위한 W3C 권장 사항입니다.
   - 저작도구는 “저자” (웹 개발자, 디자이너, 작가 등)가 웹 콘텐츠를 생산하는 데에 사용하는 서비스나 소프트웨어를 가리킵니다. 
   - 예) HTML 에디터, 콘텐츠 관리 시스템 (CMS) 그리고 사용자가 콘텐츠를 생산할 수 있는 블로그나 소셜 네트워킹 사이트가 있습니다.
   - 목표로는 저작도구의 접근성을 보장하여 장애가 있는 사용자가 웹 콘텐츠를 생산할 수 있도록 하고, 저자가 더 접근성이 좋은 웹 콘텐츠를 생산하는 것을 돕는데 있습니다.
2. **UAAG(사용자 에이전트 접근성 지침)**
   - User Agent Accessibility Guidelines의 약자로 사용자 에이전트는 브라우저, 브라우저 확장프로그램, 미디어 플레이어, 리더기와 같은 웹 콘텐츠를 제공하는 어플리케이션을 포함합니다.
3. **WAI-ARIA(접근가능한 리치 인터넷 어플리케이션)**
   - Web Accessibility Initiative's Accessible Rich Internet Applications의 약자로 스크린리더가 브라우저를 읽을 때 각 요소가 어떤 역할을 하는지 무슨 의미로 존재하는지 알 수 있도록 하기 위해 만들어진 기술이다.
   - ARIA는 의미를 제공하여 저자가 유저 인터페이스 행동이나 구조적 정보를 스크린 리더와 같은 보조 기술에 전달할 수 있게 합니다. ARIA 기술 명세는 역할, 상태, 접근 가능한 유저 인터페이스 요소로 정의되는 속성들의 온톨로지를 제공합니다.
   - ARIA 모음은 유저 에이전트 실행 지침을 제공하는 명세를 모은 API를 포함합니다. 그래픽, 디지털 출판을 위한 모듈 또한 포함됩니다.
   - WAI : 'Web Internet Applications'의 약자로 웹 접근성을 담당하는 조직.
   - ARIA : 'Accessible Rich Internet Applications'의 약자로 리치 인터넷을 위한 W3C 접근성 명세.

#### 4.1.11 참조
- [W3C WCAG 1.0](https://www.w3.org/TR/WCAG10/)
- [W3C WCAG 2.0](https://www.w3.org/TR/WCAG20/)
- [W3C WCAG 2.1](https://www.w3.org/TR/WCAG21/)
- [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [W3C WCAG 3.0 Draft](https://www.w3.org/TR/2021/WD-wcag-3.0-20210121/)
- [W3C WCAG 2.1 한국어](http://www.kwacc.or.kr/WAI/wcag21/)
- [W3C Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/)
- [W3C WCAG2 ko](https://www.w3.org/WAI/standards-guidelines/ko#wcag2)
- [W3C Accessibility Guidelines Working Group](https://www.w3.org/WAI/GL/)
- [W3C W3C 접근성의 4가지 원칙](https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head)
- [MDN 웹 컨텐츠 접근성 지침 이해하기](https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG)
- [MDN 접근성이란?](https://developer.mozilla.org/ko/docs/Learn/Accessibility/What_is_accessibility#accessibility_guidelines_and_the_law)
- [NULI WCAG 2.2에서 변경된 사항](https://nuli.navercorp.com/community/article/1133181)
- [brunch WCAG 2.2 작업 초안](https://brunch.co.kr/@snclab/55)
- [GITBOOK WCAG 2.1](https://a11y.gitbook.io/wcag/international-standards)
- [WAI 문서로 접근성 이해하기](https://iyu88.github.io//a11y/2023/12/24/web-accessibility-1.html)
- [deque blog WCAG 2.1](https://www.deque.com/blog/wcag-2-1-what-is-next-for-accessibility-guidelines/)
- [웹접근성 국가표준 개정 소개](https://seculayerlab.tistory.com/m/48)

- [한국형 웹 콘텐츠 접근성 지침 2.2](https://www.samsungfashion.com/webacc.do)
- [AOA GITBOOK](https://aoa.gitbook.io/skymimo/undefined)






