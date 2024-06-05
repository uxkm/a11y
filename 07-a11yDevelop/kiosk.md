## 7. 접근성 콘텐츠 제작 기법

### 무인정보단말기 접근성
> 무인정보단말기 접근성 콘텐츠 제작 기법은 **무인정보단말기 UI플랫폼** 사이트에 자세히 안내되고 있어서 기본적인 UI가이드 정보만 안내하고 상세내용은 사이트 링크로 제공. 
무인정보단말기(키오스크) UI(사용자 인터페이스) 가이드는 무인정보단말기 시스템을 설계하고 개발할 때 필요한 UI 디자인에 대한 지침을 제공하는 문서이다. 이 가이드는 사용자 경험(UX)을 향상시키고, 사용자가 무인정보단말기를 효과적으로 이용할 수 있도록 하는 데 중점을 둔다. 무인정보단말기의 UI는 모든 사용자에게 접근 가능해야 하므로 장애인을 위한 보조 기술 및 기능성을 고려하여 UI를 설계하도록 지침을 제시한다.

<figure aria-hidden="true" style="text-align:center">
   <img src="./../images/kiosk/kioskui.or.kr.jpg" alt="무인정보단말기 UI 플랫폼 사이트 메인">
   <figcaption>
      이미지 출처 : 무인정보단말기 UI 플랫폼 사이트 메인 캡쳐<br>
      <a href="https://www.kioskui.or.kr/index.do" target="_blank" title="새 창 열림">무인정보단말기 UI 플랫폼</a>   
   </figcaption>
</figure>

#### 무인정보단말기 개요
> 무인정보단말기(키오스크) UI(사용자 인터페이스) 가이드는 무인정보단말기 시스템을 설계하고 개발할 때 필요한 UI 디자인에 대한 지침을 제공하는 문서이다. 이 가이드는 사용자 경험(UX)을 향상시키고, 사용자가 무인정보단말기를 효과적으로 이용할 수 있도록 하는 데 중점을 둔다. 무인정보단말기의 UI는 모든 사용자에게 접근 가능해야 하므로 장애인을 위한 보조 기술 및 기능성을 고려하여 UI를 설계하도록 지침을 제시한다.   
[무인정보단말기 UI 플랫폼 > 무인정보단말기 > 안내](https://www.kioskui.or.kr/index.do?menu_id=00001026&servletPath=%2Findex.do){: target="_blank"}

#### 무인정보단말기 분류
#####  대분류
> 선행 연구(NIA 연구반, 22년)를 통해 사용자의 무인정보단말기 활용 목적 및 개별 업체의 자율성을 고려하여 4개 유형으로 분류하였다. 본 가이드는 대분류 UI 가이드를 제공한다.

1. **유통(결제형)**   
   - 상품코드(바코드 등)를 사용자가 직접 스캔해서 제품을 구매하는 유형   
     * 예. 대형마트, 편의점 등   
2. **주문(티켓형)**   
   - 직원의 도움이 필요한 음식물 등의 주문 및 구매   
     * 예. 커피숍, 패스트푸드점 등   
3. **발권(티켓/서류)**   
   - 요청에 대해 정보처리 후 인쇄물 제공   
     * 예. 무인민원발급기, 무인처방전발행기, 셀프체크인(공항, 교통)   
4. **안내**   
   - 사용자 조작에 따라 정보 제공   
     * 예. 관광정보시스템, 정보제공시스템, 안내시스템 등   

#####  중분류
> 무인정보단말기 관련 고시인 「장애인·고령자 등의 정보 접근 및 이용 편의 증진을 위한 고시」(과기정통부, 22년)에서 16개 유형으로 분류되어 있으며, 아래 내용은 대분류와 대응하여 매핑한 결과이다.   

1. **유통**   
   - (1)무인주유기 (2)무인주차정산기 (3)무인결제기 (4)무인도서대여반납기      
2. **주문**   
   - (5)무인주문기   
3. **발권**   
   - (6)무인민원발급기 (7)무인발권기 (8)무인발매기 (9)무인증명발매기 (10)셀프체크인 (11)무인처방전발매기 (12)금융자동화기기   
4. **안내**   
   - (13)종합정보시스템 (14)위치정보시스템   
5. **기타**   
   - (15)무인사용자인증기 (16) 기타(사물함, 택배함 등)   


#### UI 가이드 원칙
> UI 원칙은 무인정보단말기 서비스의 사용자 경험을 위해 무인정보단말기 UI 설계 시 준수해야 할 기본 원칙과 방향성을 담고 있다.   
[무인정보단말기 UI 플랫폼 > 무인정보단말기 > UI 가이드 원칙](https://www.kioskui.or.kr/index.do?menu_id=00001210){: target="_blank"}   

1. **사용자 중심 UI**   
   - 사용자 중심 UI 원칙은 사용자 친화적인 UI를 설계해야 함을 의미한다.   
2. **사용자에 최적화된 UI**   
   - 사용자에 최적화된 UI 원칙은 사용자의 다양한 능력을 고려한 UI를 설계해야 함을 의미한다.   
3. **직관적인 UI**   
   - 직관적인 UI 원칙은 학습이 필요 없는 인지적으로 쉬운 UI를 설계해야 함을 의미한다.   
4. **조작하기 쉬운 UI**   
   - 조작하기 쉬운 UI 원칙은 사용자가 쉽게 화면을 컨트롤 할 수 있는 UI를 설계해야 함을 의미한다.   
5. **지속 가능한 일관된 UI**   
   - 지속 가능한 일관된 UI 원칙은 사용자가 사용에 있어서 일관된 UI를 설계해야 함을 의미한다.   
6. **개인의 정보가 보호되는 UI**   
   - 개인의 정보가 보호되는 UI 원칙은 입출력되는 개인정보가 보호되도록 설계해야 함을 의미한다.   

#### UI 가이드 사용성 체크리스트




### 참조
- [W3C Mobile Accessibility at W3C](https://www.w3.org/WAI/standards-guidelines/mobile/){: target="_blank"}   
- [W3C Mobile Accessibility: How WCAG 2.0 and Other W3C/WAI Guidelines Apply to Mobile](https://www.w3.org/TR/mobile-accessibility-mapping/){: target="_blank"}    
- [W3C First Public Working Draft](https://www.w3.org/news/2015/first-public-working-draft-performance-timeline-level-2/){: target="_blank"}    
- [W3C User Agent Accessibility Guidelines (UAAG) 2.0](https://www.w3.org/TR/UAAG20/){: target="_blank"}   
- [W3C Mobile Accessibility Examples from UAAG 2.0 Reference](https://www.w3.org/TR/IMPLEMENTING-UAAG20/mobile.html){: target="_blank"}   
- [MDN Mobile accessibility checklist](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Mobile_accessibility_checklist){: target="_blank"}   
- [보건복지부 블로그](https://blog.naver.com/prologue/PrologueList.naver?blogId=mohw2016){: target="_blank"}   
- [보건복지부 - 장애인의 무인정보단말기 등 접근성 강화방안 마련 연구](https://www.mohw.go.kr/synap/doc.html?fn=1635730805506_20211101104005.pdf&rs=/upload/result/202405/){: target="_blank"}   
- [무인정보단발기 UI플랫폼 - 무인정보단말기 접근성 지침](https://www.kioskui.or.kr/index.do?menu_id=00000985){: target="_blank"}   
- [무인정보단말기(키오스크, 스마트자판기 등) 접근성 지침](https://standard.go.kr/KSCI/standardIntro/getStandardSearchView.do?menu19&topMenuId=502&upperMenuId=503&ksNo=KSX9211&tmprKsNo=KS_X_NEW_2015_1845&reformNo=01){: target="_blank"}   
- [Guidelines for Public Access Terminals Accessibility - Printable Version](https://mada.org.qa/wp-content/uploads/2020/01/Ireland-Guidelines-for-Public-Access-Terminals-Accessibility.pdf){: target="_blank"}   
- [경향신문 - ‘버튼 높이는 120㎝ 아래에’ 접근성 강화한 키오스크 표준 나온다](https://www.khan.co.kr/economy/market-trend/article/202109231513001#csidxf8d9d8b51bed28bbb4fad083122f3af){: target="_blank"}   

