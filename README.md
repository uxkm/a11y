1. 작업위한 백업
2. 기존자료와 통합
3. 정리
4. 생성
5. 예제
6. wai-aria 정리
7. sns 및 블로그 연결
8. 자료 공유
9. D-day 24.06.30 

# INDEX
1. 접근성이란?
2. 장애인차별금지법 관련 지침
3. 접근성 인증 마크
4. 웹 콘텐츠 접근성 가이드라인
   1. WCAG - (탭)
   2. KWCAG - (탭)
8. 접근성 체크리스트
9. 접근성을 고려한 콘텐츠 제작 방법
10. 접근성 항목별 준수 가이드
    - 인식의 용이성(perceivable) - (탭)
    - 운용의 용이성(operable) - (탭)
    - 이해의 용이성(understandable) - (탭)
    - 견고성(robust) - (탭)
11. WAI-ARIA 가이드라인
12. WAI-ARIA 구조
    - 역할(Role) 정의 - (탭)
    - 상태(Attributes) 및 속성(States) 정의 - (탭)
13. 역할(Role)
14. 상태(Attributes) 및 속성(States)
15. 무인정보단말기 정보접근성
16. 접근성(a11y) 자가진단 체크리스트
    - 웹 접근성 자가진단 - (탭)
    - 모바일 접근성 자가진단 - (탭)
17. 접근성(a11y) 참조 사이트


## 접근성이란?

>**접근성(accessibility)은 모든 사용자가 제품, 서비스, 환경을 가능한 한 쉽게 이용할 수 있도록 보장하는 설계 원칙입니다. 
웹 접근성(Web Accessibility), 모바일 접근성(Mobile Accessibility), 무인단말기 접근성 (Kiosk Accessibility)은 이러한 원칙이 웹사이트, 온라인 서비스, 모바일 애플리케이션, ATM, 키오스크, 자동 티켓 발매기에 적용될 때의 특별한 측면을 다룹니다. 다음은 각각에 대한 간단한 설명입니다.**

>**Accessibility essenital for some, useful for all.**
**접근성은 일부에게는 필수이며 모두에게는 유용하다.**
**-- W3C WAI --**

**접근성 (Accessibility)**
접근성은 모든 사용자가 제품, 서비스, 환경에 쉽게 접근하고 사용할 수 있도록 하는 특성을 말합니다. 이는 장애가 있는 사람뿐만 아니라, 노인, 어린이, 임산부 등 다양한 사용자 그룹을 포함합니다. 국제표준화 기구(ISO) 및 웹 접근성 이니셔티브(WAI)와 같은 기구들은 접근성 관련 국제표준을 제공합니다. 대한민국에서는 이러한 국제표준을 바탕으로 대한민국형 접근성 지침을 마련하여 적용하고 있습니다.

**웹 접근성 (Web Accessibility)**
웹 접근성은 장애를 가진 사람들이 웹사이트와 웹 애플리케이션을 이해, 이용, 탐색할 수 있도록 보장하는 것을 의미합니다. 국제표준화 기구에서는 웹 콘텐츠 접근성 지침(WCAG - Web Content Accessibility Guidelines)을 제공하고 있으며, 이는 전 세계적으로 널리 채택되고 있습니다. 대한민국에서는 이를 기반으로 대한민국형 웹 접근성 지침(KWCAG - Korean Web Content Accessibility Guidelines)을 개발하여 웹 접근성 향상을 위해 노력하고 있습니다.

**모바일 접근성 (Mobile Accessibility)**
모바일 접근성은 모바일 디바이스와 애플리케이션을 사용할 때 모든 사람들이 정보와 기능에 접근할 수 있도록 하는 것을 의미합니다. 이는 터치스크린 사용, 소형 화면 크기, 다양한 입력 방식 등 모바일 특성을 고려한 접근성입니다. 국제 웹 접근성 이니셔티브는 모바일 접근성을 WCAG(Web Content Accessibility Guidelines)의 일환으로 다루고 있으며, 대한민국은 이러한 국제 기준에 맞춰 모바일 앱 접근성 지침을 마련하여 적용하고 있습니다.


**무인단말기 접근성 (Kiosk Accessibility)**
무인단말기 접근성은 ATM, 키오스크, 자동 티켓 발매기 등과 같은 무인 서비스 단말기를 모든 사용자가 쉽게 사용할 수 있도록 하는 것을 목표로 합니다. 다음은 무인단말기 접근성의 핵심 요소입니다.

- **개념**: 무인단말기 접근성은 장애를 가진 사용자를 포함하여 모든 사용자가 무인단말기를 이해하고, 사용하고, 탐색할 수 있도록 보장하는 것을 목적으로 합니다. 이는 장비의 물리적 배치, 인터페이스 디자인, 입력 및 출력 방법 등 다양한 측면을 포함합니다.

- **중요성**: 점점 더 많은 서비스가 무인단말기를 통해 제공되고 있기 때문에, 이러한 기기의 접근성은 사용자에게 독립성과 평등한 서비스 이용 기회를 제공하는 데 중요합니다.

- **구현 요소**:
물리적 접근성: 단말기는 휠체어 사용자도 접근할 수 있는 높이와 위치에 설치되어야 합니다. 또한, 시각 장애인 사용자를 위한 점자 표시나 오디오 출력 기능이 필요할 수 있습니다.
인터페이스 접근성: 화면에 표시되는 콘텐츠는 충분한 대비와 큰 글꼴 크기로 제공되어야 합니다. 입력 장치(버튼, 터치스크린 등)는 다양한 사용자가 쉽게 조작할 수 있도록 설계되어야 합니다.
소프트웨어 접근성: 소프트웨어는 명확하고 간단한 메뉴 구조를 가지며, 필요한 경우 오디오 지원을 포함해야 합니다. 사용자가 진행 상황을 쉽게 이해할 수 있도록 도와주는 피드백도 중요합니다.
법적 요구사항: 여러 국가에서는 무인단말기의 접근성을 법적으로 규정하고 있습니다. 예를 들어, 미국의 경우 미국 장애인법(ADA - The Americans with Disabilities Act)과 같은 법률이 무인단말기의 접근성 기준을 정의하고 있습니다.

결론은 접근성, 웹 접근성, 모바일 접근성, 그리고 무인단말기 접근성 모두 기술이 모든 사람에게 도달할 수 있도록 보장하는 중요한 원칙입니다. 이러한 접근성 향상은 사용자 경험을 개선하고, 사회적 포용성을 증진시키며, 법적 요구사항을 충족시키는 데 핵심적인 역할을 합니다.

이러한 모든 영역에서의 접근성 향상은 기술적인 문제뿐만 아니라 윤리적, 법적 책임도 포함하고 있습니다. 디지털 접근성은 정보와 서비스에 대한 보편적 접근을 가능하게 함으로써 모든 사람에게 더 나은 사용자 경험을 제공하고, 디지털 포용성을 증진시키는 데 중요한 역할을 합니다.

---

## 장애인차별금지법 관련 지침
>장애인 차별 금지법과 관련한 지침에는 국제 표준과 대한민국 기준이 있습니다. 여기서 국제 표준은 주로 유엔 장애인 권리 협약(UNCRPD - The United Nations Convention on the Rights of Persons with Disabilities)에 기반을 두고 있으며, 대한민국 기준은 장애인차별금지 및 권리구제 등에 관한 법률(장차법)에 의해 규정됩니다.
장애인차별금지법 및 관련 지침은 장애가 있는 사람들이 웹 사이트 및 모바일 애플리케이션을 포함한 디지털 리소스에 대한 접근성을 보장하기 위한 법적 기준을 제공합니다. 각국 또는 지역마다 이러한 법적 요구 사항은 다를 수 있으며, 웹 콘텐츠 접근성 지침(WCAG - Web Content Accessibility Guidelines)과 같은 국제 표준에 기반을 둔 경우가 많습니다.

1. 국제표준: 유엔 장애인 권리 협약(UNCRPD - The United Nations Convention on the Rights of Persons with Disabilities)
유엔 장애인 권리 협약(UNCRPD - The United Nations Convention on the Rights of Persons with Disabilities)은 장애인의 인권과 기본 자유를 보호하고 촉진하기 위해 2006년에 채택된 국제 법적 구속력이 있는 조약입니다. 이 협약은 장애인이 사회의 모든 분야에서 완전하고 효과적으로 참여할 수 있도록 보장하는 것을 목표로 합니다. 협약의 주요 내용은 다음과 같습니다:

   - 평등성: 모든 인간의 존엄성, 자율성을 포함한 개인의 권리, 인권의 불가분성을 인정합니다.
   - 차별 금지: 장애를 이유로 한 모든 형태의 차별을 금지하고, 장애인에게 법적 보호를 제공합니다.
   - 포괄적 접근성: 물리적 환경, 교통, 정보 및 커뮤니케이션 기술, 그리고 서비스에 대한 접근성을 증진시킵니다.
   - 평등한 기회: 교육, 고용, 보건, 사회 보호 등에서 장애인의 참여와 평등한 기회를 보장합니다.
2. 대한민국 기준: 장애인차별금지 및 권리구제 등에 관한 법률(장차법)
   대한민국의 장차법은 2007년에 제정되어 장애인이 사회의 모든 영역에서 차별받지 않고 동등하게 참여할 수 있도록 보장합니다. 장차법의 주요 내용은 다음과 같습니다:
   - 차별의 금지: 직접적, 간접적 차별을 포함한 모든 형태의 장애인 차별을 금지합니다.
   - 합리적 편의 제공: 장애인이 사회적, 경제적 활동에 동등하게 참여할 수 있도록 필요한 편의를 제공합니다.
   - 권리구제 절차: 차별을 경험한 장애인이 구제를 받을 수 있도록 절차를 마련하고 있으며, 장애인권익옹호기관을 통해 지원받을 수 있습니다.
   - 차별행위의 예방 및 교육: 장애인 차별의 예방과 인식 개선을 위한 교육 및 홍보 활동을 강화합니다.

두 기준 모두 장애인의 권리와 차별 금지를 강조하고 있으며, 장애인이 사회의 평등한 구성원으로서 존중받고 차별 없이 살아갈 수 있도록 다양한 조치를 제시합니다. 이러한 조치는 장애인의 삶의 질 향상은 물론, 사회 전체의 포괄성과 다양성을 증진시키는 데 기여합니다.
국제표준인 유엔 장애인 권리 협약(UNCRPD - The United Nations Convention on the Rights of Persons with Disabilities)은 국가들이 장애인 권리의 보호와 촉진을 위한 정책을 수립하고 실행할 법적 의무를 가지게 합니다. 이는 회원국들이 장애인이 교육, 고용, 건강, 정보 접근성 등 사회의 모든 영역에서 차별받지 않고 포괄적으로 참여할 수 있도록 보장해야 한다는 의미입니다.

대한민국의 장차법 역시 유사한 원칙을 따르며, 국내 법률 체계 내에서 장애인의 권리를 구체화하고 보호합니다. 이 법은 장애인이 겪는 다양한 형태의 차별을 명확히 규정하고, 이에 대한 구제 절차를 마련하여 장애인이 실제로 자신의 권리를 주장하고 보호받을 수 있는 수단을 제공합니다.
또한, 이러한 기준과 법률은 단순히 금지와 지침을 넘어서, 사회적 인식의 변화와 교육을 통해 장애인에 대한 편견을 줄이고, 모두가 존중받는 사회를 만들기 위한 노력을 강조합니다. 이는 장애인뿐만 아니라 사회 전체에 긍정적인 영향을 미치며, 다양성과 포용성이 사회 발전의 중요한 동력이 될 수 있음을 보여줍니다.

결국, 이러한 국제표준과 대한민국 기준은 장애인의 권리를 보호하고 촉진하는 것을 넘어, 보다 포괄적이고 평등한 사회를 향한 지속적인 노력의 일환입니다. 이를 통해 장애인 개인은 물론, 사회 전체가 보다 포괄적이고 다양성을 존중하는 방향으로 발전할 수 있습니다.

**장애인차별금지 및 권리구제 등에 관한 법률(장차법)**


---

## 접근성 인증 마크
웹 접근성 인증 마크란 웹사이트 또는 온라인 서비스가 특정 웹 접근성 기준이나 지침을 충족한다는 것을 인증하는 마크입니다. 이 인증 마크를 획득함으로써, 조직은 자신의 웹사이트가 광범위한 사용자들에게 접근 가능하다는 것을 공식적으로 보여줄 수 있으며, 법적 요구 사항을 준수한다는 신뢰를 제공합니다. 웹 접근성 인증 과정은 일반적으로 사이트의 검사 및 평가를 포함하며, 필요한 경우 사이트의 개선 작업 후에 인증을 받게 됩니다.

---

## 웹 콘텐츠 접근성 가이드라인
웹 콘텐츠 접근성 가이드라인(WCAG)은 웹사이트와 온라인 서비스를 모든 사용자가 접근할 수 있도록 만드는 국제 표준입니다. 이 가이드라인은 세계적으로 인정받으며, 다양한 정부 및 조직에서 웹 접근성을 위한 기준으로 채택하고 있습니다. WCAG는 웹 접근성을 보장하기 위해 따라야 할 명확한 기준과 권장 사항을 제공합니다.

WCAG(Web Content Accessibility Guidelines)는 여러 버전이 있으며, 가장 널리 사용되는 버전은 WCAG 2.0과 WCAG 2.1입니다. 이 가이드라인은 네 가지 주요 원칙에 기반을 두고 있습니다:

1. 인지 가능성(Perceivable): 사용자가 정보를 인지하고 콘텐츠를 볼 수 있어야 합니다. 예를 들어, 시각적 콘텐츠는 대체 텍스트를 통해 설명되어야 하며, 오디오 콘텐츠는 자막이나 수화 번역을 통해 제공되어야 합니다.

2. 운용 가능성(Operable): 사용자가 콘텐츠의 인터페이스 요소를 운용할 수 있어야 합니다. 이는 웹사이트가 키보드만으로도 전체적으로 사용될 수 있어야 하며, 충분한 시간을 제공하고, 발작을 유발할 수 있는 콘텐츠를 피하는 것을 의미합니다.

3. 이해 가능성(Understandable): 사용자가 정보와 인터페이스의 운용 방식을 이해할 수 있어야 합니다. 이는 웹 페이지가 예측 가능하게 작동하며, 사용자가 실수를 할 경우 이를 정정할 수 있는 방법을 제공해야 함을 의미합니다.

4. 견고성(Robust): 다양한 사용자 에이전트(브라우저 등)와 보조 기술에서 콘텐츠를 정확하게 해석할 수 있어야 합니다. 이는 웹 콘텐츠가 현재 및 미래의 기술과 호환될 수 있도록 보장합니다.

WCAG(Web Content Accessibility Guidelines)는 이 원칙들을 따르기 위한 구체적인 기준을 제공하며, 각 기준은 세 가지 준수 수준(A, AA, AAA)으로 구분됩니다. A는 최소 수준, AA는 중간 수준, AAA는 가장 높은 수준의 접근성을 의미합니다. 대부분의 조직과 정부 기관은 웹사이트가 적어도 AA 수준의 기준을 충족하도록 요구합니다.

### WCAG
### KWCAG

---

## 접근성 체크리스트
모바일 접근성은 모바일 기기 사용자가 앱이나 웹사이트를 이용할 때 겪을 수 있는 장애를 최소화하는 것을 목표로 합니다. 웹 콘텐츠 접근성 가이드라인(WCAG)과 마찬가지로 모바일 접근성도 사용자가 콘텐츠를 인지할 수 있게 하고, 콘텐츠를 운용하며, 콘텐츠를 이해하고, 견고한 콘텐츠를 제공하는 것을 중요하게 여깁니다. 다음은 모바일 접근성을 향상시키기 위한 체크리스트의 예입니다:

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
오리엔테이션: 앱이나 웹사이트가 가로 및 세로 방향 모두에서 사용할 수 있도록 지원합니다.
멀티미디어 대체 옵션: 비디오나 오디오 콘텐츠에는 자막, 설명서, 수화 번역 등을 제공합니다.
모바일 접근성을 확보하는 것은 다양한 사용자의 경험을 향상시키는 동시에 법적 요구 사항을 충족하는 중요한 단계입니다. 모바일 앱이나 웹사이트를 개발할 때 이러한 체크리스트를 참고하여 접근성을 향상시키는 것이 좋습니다.

---

## 접근성을 고려한 콘텐츠 제작 방법
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

## 접근성 항목별 준수 가이드
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