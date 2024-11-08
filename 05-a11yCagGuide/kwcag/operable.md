## 웹 콘텐츠 접근성

**운용의 용이성 (Operable)**
> **운용의 용이성 (Operable)** 은 사용자가 장애 유무 등에 관계없이 웹 사이트에서 제공하는 모든 기능들을 운용할 수 있도록 제공하는 것을 의미한다.    
KWCAG 2.1 **운용의 용이성**은 입력장치 접근성, 충분한 시간 제공, 광과민성 발작 예방, 쉬운 내비게이션의 **4 가지 지침**으로 구성되어 있다.   
KWCAG 2.2 **운용의 용이성**은 입력장치 접근성, 충분한 시간 제공, 광과민성 발작 예방, 쉬운 내비게이션, 입력 방식의 **5가지 지침**으로 구성되어 있다.    

### 6.1. 입력장치 접근성

#### 6.1.1. 키보드 사용 보장
> **모든 기능은 키보드만으로도 사용할 수 있어야 한다.**   
웹 페이지에서 제공하는 모든 기능을 키보드만으로도 사용할 수 있도록 제공해야 한다.    
다만, 사용자의 반응 속도나 지속성이 중요한 요소인 붓질, 헬리콥터나 비행기 등의 훈련에 사용되는 시뮬레이션 콘텐츠 등과 시각적인 방법으로만 접근이 가능한 지리 정보 콘텐츠, 가상 현실 콘텐츠 등은 이 검사 항목의 예외로 할 수 있다.    
WCAG 2.1 부분 참조.   
[2.1.1 Keyboard (Level A)](https://www.w3.org/TR/WCAG21/#keyboard){: target="_blank"}

**고려 사항**    
1. 키보드 인터페이스와 기능
   - 콘텐츠의 모든 기능은 키보드로 사용이 가능하여야 한다. 이 경우, 해당 기능을 사용하는 데 필요한 키보드의 조작 횟수의 많고 적음은 고려 대상이 아니다.   
2. 예외 콘텐츠
   - 위치 지정 도구의 커서 궤적이 중요한 역할을 하는 콘텐츠(붓질 기능이 필요한 콘텐츠, 시뮬레이션 콘텐츠, 지리정보 응용 콘텐츠, 가상현실 콘텐츠 등), 움직임 측정 센서를 이용하는 콘텐츠는 이 검사 항목의 예외 콘텐츠로 간주한다. 그러나 예외 콘텐츠의 경우에도 위치 지정 도구나 움직임 측정 센서를 이용하는 기능을 제외한 나머지 사용자 인터페이스는 키보드만으로 사용할 수 있어야 한다.   

**기대 효과**    
- 위치 지정 도구를 사용할 수 없는 시각 장애인의 경우, 키보드만으로도 웹 콘텐츠나 웹 사이트가 제공하는 모든 기능을 사용할 수 있다.


#### 6.1.2. 초점 이동
> **키보드에 의한 초점은 논리적으로 이동해야 하며 시각적으로 구별할 수 있어야 한다.**   
웹 페이지에서 제공하는 모든 기능을 키보드만으로 사용하는 경우에도 사용자 입력 간의 초점 이동은 적절한 순서를 따라야 하며, 이 과정에서 콘텐츠는 조작이 불가능한 상태가 되거나 갑작스러운 페이지의 전환 등이 일어나지 않아야 한다. 또한 초점을 받은 콘텐츠는 저시력 장애인과 지체 장애인들이 인지할 수 있도록 시각적으로 구별되어야 한다.    
WCAG 2.1 부분 참조.    
[2.1.2 No Keyboard Trap (Level A)](https://www.w3.org/TR/WCAG21/#no-keyboard-trap){: target="_blank"}    
[2.4.3 Focus Order (Level A)](https://www.w3.org/TR/WCAG21/#character-key-shortcuts){: target="_blank"}    

**고려 사항**    
1. 초점 이동 순서 유지   
   - 사용자가 키보드를 이용하여 초점을 이동하는 경우 이동 순서가 관례를 벗어나면 사용자에게 혼란을 주기 때문에 초점 이동 순서는 사용자가 예측하는 이동 순서와 일치하여야 한다. 바람직한 방법은 기존의 관례를 따르도록 콘텐츠를 제공하는 것이다. 관례와 달리 초점 이동 순서를 결정해야 하는 경우에는 사용자 입력 간의 이동 순서가 논리적이 되도록 구현해야 한다.    
     예) 사용자 아이디, 비밀번호를 입력하는 입력 창과 로그인 버튼 간의 초점 이동 순서는 사용자 아이디, 비밀번호, 로그인 버튼의 순서이어야 한다.   
2. 함정 또는 오류 방지   
   - 웹 콘텐츠는 더 이상 키보드 조작이 불가능한 상태가 되어 다음 사용자 입력 또는 컨트롤 등으로 초점을 이동할 수 없거나 이전 페이지로 초점을 이동할 수 없는 상태가 되지 않도록 구현하여야 한다.   
3. 초점의 시각화    
   - 사용자 입력 등이 위치 지정 도구(마우스)나 키보드 조작을 통해 초점을 받았을 때, 해당 컨트롤이 초점을 받았음을 시각적으로 구별할 수 있음을 의미한다.    
    대표적인 예) 키보드 조작을 통해 버튼이 초점을 받았을 때 이 버튼의 주위에 점선의 테두리가 표시되는 것을 들 수 있다. 위치 지정 도구에 의한 초점과 키보드에 의한 초점의 표시 방법이 다른 것도 허용한다.    

**기대 효과**    
- 화면 낭독 프로그램을 이용하는 사용자의 경우, 사용자 입력 주변의 상하좌우에 위치한 콘텐츠에 대한 정보를 알 수 없다. 따라서 웹 콘텐츠를 사용하는 과정에서 키보드 조작에 의한 사용자 입력 간의 이동 순서는 관례를 따라야 한다. 그렇지 않으면 사용자 입력의 조작 과정에서 혼란을 주게 된다.    
- 마우스나 키보드 조작을 통해 특정 영역으로 컨트롤을 이동하였을 경우에 해당 영역이 초점을 받았음을 시각적으로 알려준다면 저시력 장애인, 노인, 지체 장애인뿐만 아니라 비장애인들도 어느 컨트롤이 선택되었고 활성화시킬 수 있는지 쉽게 인지할 수 있다.    


#### 6.1.3. 조작 가능
> **사용자 입력 및 컨트롤은 조작 가능하도록 제공되어야 한다.**   
웹 페이지에서 제공하는 모든 이웃한 컨트롤은 개별적으로 선택하고 사용할 수 있도록 충분한 크기로 제공해야 한다.   

**고려 사항**    
1. 컨트롤의 크기    
   - 콘텐츠에 포함된 모든 컨트롤은 대각선 방향의 길이를 6.0 mm 이상으로 제공하는 것이 바람직하다.   
2. 링크, 사용자 입력, 기타 컨트롤 등의 안쪽 여백   
   - 링크, 사용자 입력 및 기타 컨트롤은 테두리 안쪽으로 1 픽셀 이상의 여백을 두고 이곳에서는 위치 지정 도구의 조작에 반응하지 않도록 구현하는 것이 바람직하다.   

**기대 효과**    
- 컨트롤을 크게 구현하면 터치스크린을 채용한 기기를 이용하는 손 떨림이 있는 사용자와 시각 장애인도 컨트롤을 용이하게 찾아서 조작할 수 있다.   

### 6.2. 충분한 시간 제공

#### 6.2.1. 응답시간 조절
> **시간제한이 있는 콘텐츠는 응답시간을 조절할 수 있어야 한다.**   
웹 콘텐츠 제작 시 시간제한이 있는 콘텐츠는 가급적 포함하지 않는 것이 바람직하며, 보안 등의 사유로 시간제한이 반드시 필요할 경우에는 이를 회피할 수 있는 수단을 제공해야 한다.    
WCAG 2.1 부분 참조.   
[2.2.1 Timing Adjustable (Level A)](https://www.w3.org/TR/WCAG21/#timing-adjustable){: target="_blank"}


**고려 사항**    
1. 시간제한 콘텐츠 사용 배제   
   - 시간제한이 있는 콘텐츠는 제공하지 않아야 한다.   
2. 예외 콘텐츠   
   - 시간제한이 있더라도 온라인 경매, 실시간 게임 등과 같이 반응 시간의 조절이 원천적으로 허용되지 않는 경우에는 이 검사 항목이 적용되지 않는다. 다만, 이 경우에도 사용자에게 시간제한이 있다는 것을 미리 알려주고, 종료되었을 경우에도 이를 알려주어야 한다. 세션 시간이 20 시간 이상인 콘텐츠의 경우에도 예외로 간주한다.   
3. 반응 시간 조절이 필요한 콘텐츠   
   - 반응 시간이 정해진 웹 콘텐츠를 사용자가 이용할 수 있도록 하기 위해서는 반응 시간이 완료되기 전에 사용자가 다음 중 한 가지 방법을 선택하여 반응 시간을 조절할 수 있는 수단을 제공해야 한다. 또한 반응 시간 조절 기능은 충분한 시간(최소 20 초 이상)을 두고 사전에 알려 주어야 한다.    
   - **시간제한을 해제할 수 있어야 한다.**
   - **시간제한을 연장할 수 있어야 한다.**

**기대 효과**    
- 비장애인보다 문서를 읽고 이해하는 데 더 많은 시간이 필요한 지적 장애 또는 학습 장애가 있는 사용자도 시간제한이 있는 콘텐츠를 시간에 관계없이 이용할 수 있게 된다.    

#### 6.2.2. 정지 기능 제공
> **자동으로 변경되는 콘텐츠는 움직임을 제어할 수 있어야 한다.**   
웹 콘텐츠는 스크롤 및 자동 갱신되는 콘텐츠를 장애인 사용자가 이용할 수 있도록 일시 정지할 수 있는 수단을 제공해야 한다.    
WCAG 2.1 부분 참조.   
[2.2.2 Pause, Stop, Hide (Level A)](https://www.w3.org/TR/WCAG21/#pause-stop-hide){: target="_blank"}


**고려 사항**    
1. 이동하거나 스크롤 되는 콘텐츠 사용 배제   
   - 스크롤 및 자동 갱신되는 콘텐츠를 사용하지 않는다.   
2. 이동하거나 스크롤되는 콘텐츠   
   - 저시력 장애인이나 지적 장애인 등은 이동하거나 스크롤되는 콘텐츠를 사용하기 어려우므로, 웹 콘텐츠는 사용자가 이동이나 스크롤을 일시 정지시키고, 지나간 콘텐츠 또는 앞으로 나타날 콘텐츠를 선택할 수 있는 컨트롤   
     (예 : ‘앞으로 이동', ‘뒤로 이동’, ‘정지’ 등)을 제공해야 한다.    

**기대 효과**    
- 배너와 같이 빠르게 변화하는 콘텐츠를 이용하기 어려운 지체 장애인, 노인, 뇌병변 장애인들도 빠르게 변화하는 콘텐츠를 이용할 수 있다.   
- 스크롤되는 뉴스 콘텐츠에서 이미 지나간 뉴스를 손쉽게 확인할 수 있는 기능이 제공되면 콘텐츠의 사용이 편리하게 된다.   

### 6.3. 광과민성 발작 예방

#### 6.3.1. 깜빡임과 번쩍임 사용 제한
> **초당 3~50 회 주기로 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다.**   
깜빡이거나(flashing) 번쩍이는(blinking) 콘텐츠로 인해 발작을 일으키지 않도록 초당 3∼50 회 주기로 깜빡이거나 번쩍이는 콘텐츠를 제공하지 않아야 한다. 10 인치 이상의 스크린을 채용하고 있는 정보통신 기기(태블릿 기기, PC 모니터, 무인 안내기 등)에서는 콘텐츠에 의한 광과민성 발작 가능성을 특히 주의해야 한다.    
WCAG 2.1 부분 참조.   
[2.3.1 Three Flashes or Below Threshold (Level A)](https://www.w3.org/TR/WCAG21/#three-flashes-or-below-threshold){: target="_blank"}


**고려 사항**    
1. 번쩍이는(blinking) 콘텐츠 사용 금지   
   - 번쩍임이 초당 3~50 회이며, 10 인치 이상의 화면에 표시된 번쩍이는 콘텐츠가 차지하는 면적의 합이 화면 전체 면적의 10%를 넘지 않아야 한다.   
2. 깜빡이는(flashing) 콘텐츠 사용 금지   
   - 초당 3~50 회의 속도로 깜빡거리게 만든 콘텐츠는 그 깜빡임을 정지시킬 수 있어야 한다.    
3. 번쩍이는(blinking) 시간의 제한   
   - 웹 페이지에 포함되는 콘텐츠의 번쩍이는 시간을 3 초미만으로 제한하면 지속적인 번쩍임으로 인한 사용자(예 : 광과민성 증후 환자, 학습 장애인, 저시력 장애인 등)의 발작을 예방하면서도 콘텐츠의 중요성을 알릴 수 있다.   

**기대 효과**    
- 광과민성 증후가 있는 사용자들은 빛이 번쩍거리는 것에 민감하게 반응하여 발작을 일으킬 수 있다. 따라서 본 검사 항목을 준수한 콘텐츠는 광과민성 증후가 있는 사용자도 접근 가능하다.   
- 주의 집중에 어려움이 있는 사람의 경우, 지속적으로 번쩍거림이 있는 콘텐츠를 집중하여 응시하기가 매우 어렵다. 따라서 본 검사 항목을 만족하는 웹 콘텐츠는 주의 집중에 어려움이 있는 사람도 접근이 가능하다.   

### 6.4. 쉬운 내비게이션

#### 6.4.1. 반복 영역 건너뛰기
> **콘텐츠의 반복되는 영역은 건너뛸 수 있어야 한다.**   
키보드 사용자는 페이지가 로드된 이후 모든 웹페이지에 공통적으로 들어있는 메뉴 및 링크 목록 등을 탭 키를 이용하여 순차적으로 내비게이션 한 후에 핵심 영역에 도달하게 된다.    
화면 낭독 프로그램을 이용하는 사람들은 메뉴 등을 페이지가 로드되거나 갱신될때마다 모든 웹페이지에 공통적으로 들어있는 메뉴 등을 다시 듣게 된다. 키보드 사용자와 화면 낭독 프로그램 사용자가 겪게 되는 이러한 불편을 방지하기 위해, 사용자가 메뉴 등과 같은 반복 영역을 바로 건너뛰어 핵심 영역으로 직접 이동할 수 있는 수단을 제공해야 한다.   
WCAG 2.1 부분 참조.   
[2.4.1 Bypass Blocks (Level A)](https://www.w3.org/TR/WCAG21/#bypass-blocks){: target="_blank"}   


**고려 사항**    
1. 반복 영역을 건너 뛸 수 있는 수단 제공 : 웹 페이지가 제공하는 핵심 영역이 위치한 곳으로 직접 이동하는 건너뛰기 링크를 제공한다. 건너뛰기 링크는 웹 페이지의 가장 앞에 제공한다.   
2. 여러 개의 건너뛰기 링크 제공 : 여러 개의 건너뛰기 링크를 제공하는 경우에는 핵심 영역으로 이동하기 위한 건너뛰기 링크를 가장 먼저 나타내도록 한다.    
3. 시각적인 구현 : 건너뛰기 링크는 시각 장애인뿐 아니라 지체 장애인도 키보드 조작 횟수를 줄일 수 있게 하는 효과적인 수단이므로 메뉴 건너뛰기 링크는 화면에 보이도록 구현해야 한다.    

**기대 효과**    
- 웹 페이지의 상단이나 좌측 프레임에 동일한 링크 목록이 반복되는 영역이 포함되어 있으면 화면 낭독 프로그램은 이 링크 목록을 순서대로 읽어준 후에야 필요한 부분을 읽어주므로 매우 불편하다. 마찬가지로 키보드 사용자들은 모든 링크 목록을 순차적으로 이동해야만 핵심 영역으로 이동할 수 있어 매우 불편하다. 그러나 웹 페이지의 첫 부분에 핵심 영역으로 이동할 수 있는 건너뛰기 링크를 제공하면 키보드 사용자는 몇 번의 키보드 조작을 통해서 핵심 영역으로 빠르게 이동할 수 있다.   
- 색인이 없는 긴 문장으로 구성된 콘텐츠의 경우에 콘텐츠의 특정 위치로 이동하는 것이 매우 불편하다. 그러나 웹 페이지의 시작 부분에 색인을 제공하면 필요한 부분으로 직접 이동할 수 있어 보다 쉽고 빠르게 내비게이션할 수 있다. 콘텐츠를 장, 절, 소절 등으로 구분하면 웹브라우저 또는 보조 기술이 제공하는 장, 절, 소절 간의 빠른 이동 수단을 이용할 수 있게 된다.   
- 여러 페이지로 구성된 웹 사이트에서 사이트 맵을 제공하면 사용자는 이를 이용하여 필요한 정보가 위치한 페이지로 보다 쉽고 빠르게 이동할 수 있다.     

#### 6.4.2. 제목 제공
> **페이지, 프레임, 콘텐츠 블록에는 적절한 제목을 제공해야 한다.**
페이지, 프레임, 콘텐츠 블록의 제목은 사용자가 웹 콘텐츠를 운용하기 쉽게 도와준다.     
제목은 간단명료해야 하며, 해당 페이지, 프레임, 콘텐츠 블록을 유추할 수 있도록 제공해야 한다.    
WCAG 2.1 부분 참조.   
[2.4.2 Page Titled (Level A)](https://www.w3.org/TR/WCAG21/#page-titled){: target="_blank"}   


**고려 사항**    
1. 웹 페이지 제목(title) 제공   
   - 모든 웹 페이지가 해당 내용을 간단명료하게 기술한 제목을 포함하고 있을 경우 여러 개의 웹 페이지가 열려 있더라도 사용자(예 : 시각 장애인, 지적 장애인, 중증 지체 장애인 등)는 제목을 통해 웹 페이지를 선택하므로 모든 웹 페이지에는 해당 페이지를 간단명료하게 설명한 제목을 제공해야 한다. 또한, 웹 페이지 제목은 유일하고 서로 다르게 제공해야 한다.    
2. 팝업 창 제목(title) 제공   
   - 팝업 창에도 제목을 제공해야 한다.    
3. 프레임 제목(title) 제공   
   - 웹 페이지의 모든 프레임에는 각 프레임을 설명하는 간단명료한 제목을 제공해야 한다. 모든 프레임에 간단명료한 제목이 부여되면 사용자(예 : 시각 장애인, 지적 장애인, 중증 지체 장애인 등)는 프레임 제목을 통해 프레임의 선택, 이동 등이 가능하다. 아무런 내용이 없는 프레임에도 '빈 프레임' 등과 같이 제목을 제공한다.    
4. 콘텐츠 블록 제목 구성   
   - 콘텐츠 블록에는 적절한 제목(heading)을 제공하면 제목과 본문을 구분할 수 있으며, 제목을 이용하여 콘텐츠 블록 간의 이동이 가능하다. 그러나 본문이 없는 콘텐츠 블록에는 제목을 붙이지 않는다.     
5. 특수 기호 사용 제한   
   - 웹 페이지, 프레임 또는 콘텐츠 블록의 제목은 문장의 하나로 간주하여 불필요한 특수 기호를 반복하여 사용하지 않는다.   

**기대 효과**    
- 웹 사이트가 제공하는 모든 웹 페이지에 서로 다른 제목을 제공하면 동시에 여러 개의 웹 페이지가 열려 있더라도 사용자(예 : 시각 장애인, 지적 장애인, 지체 장애인 등)는 웹 페이지의 제목을 확인하여 열려있는 웹 페이지 간을 편리하게 이동할 수 있다. 이를 위해, 각 페이지는 해당 페이지만의 유일하고 서로 다른(unique and exclusive) 페이지 제목을 가져야 한다.   
- 웹 페이지를 구성하는 모든 프레임에 제목을 제공하면 사용자  (예 : 시각 장애인, 지적 장애인, 중증 지체 장애인 등)는 프레임 제목을 통해 프레임 간을 매우 편리하게 이동할 수 있다. 이를 위해, 페이지의 경우와 마찬가지로, 동일한 페이지에 포함된 모든 프레임은 해당 프레임만의 유일하고 서로 다른 프레임 제목을 가져야 한다.   


#### 6.4.3. 적절한 링크 텍스트 
> **링크 텍스트는 용도나 목적을 이해할 수 있도록 제공해야 한다.**   
링크는 주변 맥락을 통하여 용도나 목적지를 명확하게 이해할 수 있는 링크 텍스트를 제공해야 한다.   
WCAG 2.1 부분 참조.   
[2.4.4 Link Purpose (In Context) (Level A)](https://www.w3.org/TR/WCAG21/#link-purpose-in-context)   


**고려 사항**    
1. 맥락을 통해 이해할 수 있도록 링크 텍스트 제공   
   - 링크의 용도나 목적지를 링크 텍스트만으로 또는 주변의 맥락으로부터 충분히 이해할 수 있도록 링크 텍스트를 제공해야 한다.    
        - 문장의 일부분에 링크를 연결하는 경우 : URL(Uniform Resource Locator) 목적지, 용도 등을 표현한 텍스트에 링크를 연결해야 한다.   
        - ‘바로가기’, ‘GO’ 등의 링크 텍스트를 제공하는 경우 : URL에 관한 정보를 제공하는 문장에 이어서 링크 텍스트를 삽입한다.   
        - 이미지 링크를 제공하는 경우 : URL에 관한 정보를 제공하는 텍스트와 URL로 이동하는 이미지 링크는 하나의 링크로 구성하는 것이 바람직하다. 이 경우, 이미지 링크의 대체 텍스트는 공백 문자로 제공해야 한다.   
        - 동일한 제품을 서로 다른 관점에서 각각 설명한 페이지로 이동하는 링크들은 각 링크 텍스트를 서로 다르게 구성하는 것이 바람직하다.   
        - 탭(tab) 컨트롤을 이용하여 공지사항 목록을 나열하고, 주변에 ‘더보기’ 링크를 제공하는 콘텐츠에서 ‘더보기’ 링크는 그 맥락으로부터 ‘공지사항 더보기’임을 알 수 있다.      
1. 이미지 링크 구성
   - 아이콘(icon)으로 링크 텍스트를 대신하여 표현한 경우   
     (예 : 홈 페이지로 이동하기 위한 링크를 집 모양의 아이콘 이미지로 대신하고 해당 아이콘에 홈 페이지로 이동하는 링크를 걸어놓은 경우), 해당 아이콘 이미지만으로도 링크의 용도나 목적지, 내용 등을 충분히 이해할 수 있도록 직관적이고 명료하게 제공한다. 아이콘에 대체 텍스트를 제공하는 방법은 검사 항목 5.1.1 절의 ‘적절한 대체 텍스트 제공’을 참고해야 한다.    

**기대 효과**    
- 텍스트에 링크를 연결할 때, ‘여기를 클릭하세요.’와 같이 애매모호한 표현을 사용하여 링크를 연결한 경우, 시각 장애인이나 지적 장애인뿐 아니라 비장애인들도 클릭했을 때 어떤 일이 일어날 것이며 무슨 내용이 제시될 것인지를 알 수 없다. 그러나 링크 텍스트를 직관적으로 구성하면 장애인들은 해당 링크를 클릭했을 때 무슨 일이 벌어질 것인지를 분명하게 알 수 있으므로 시각 장애인이나 지적 장애인은 맥락을 이해하기 위한 쓸데없는 콘텐츠 간의 이동 과정을 피할 수 있다.   


#### 참조
- [W3C WCAG 1.0](https://www.w3.org/TR/WCAG10/){: target="_blank"}
- [W3C WCAG 2.0](https://www.w3.org/TR/WCAG20/){: target="_blank"}
- [W3C WCAG 2.1](https://www.w3.org/TR/WCAG21/){: target="_blank"}
- [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/){: target="_blank"}
- [W3C WCAG 3.0 Draft](https://www.w3.org/TR/2021/WD-wcag-3.0-20210121/){: target="_blank"}
- [W3C WCAG 2.1 한국어](http://www.kwacc.or.kr/WAI/wcag21/){: target="_blank"}
- [W3C Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/){: target="_blank"}
- [W3C WCAG2 ko](https://www.w3.org/WAI/standards-guidelines/ko#wcag2){: target="_blank"}
- [W3C Accessibility Guidelines Working Group](https://www.w3.org/WAI/GL/){: target="_blank"}
- [W3C W3C 접근성의 4가지 원칙](https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head){: target="_blank"}
- [MDN 웹 컨텐츠 접근성 지침 이해하기](https://developer.mozilla.org/ko/docs/Web/Accessibility/Understanding_WCAG){: target="_blank"}
- [MDN 접근성이란?](https://developer.mozilla.org/ko/docs/Learn/Accessibility/What_is_accessibility#accessibility_guidelines_and_the_law){: target="_blank"}
- [NULI WCAG 2.2에서 변경된 사항](https://nuli.navercorp.com/community/article/1133181){: target="_blank"}
- [brunch WCAG 2.2 작업 초안](https://brunch.co.kr/@snclab/55){: target="_blank"}
- [GITBOOK WCAG 2.1](https://a11y.gitbook.io/wcag/international-standards){: target="_blank"}
- [WAI 문서로 접근성 이해하기](https://iyu88.github.io//a11y/2023/12/24/web-accessibility-1.html){: target="_blank"}
- [deque blog WCAG 2.1](https://www.deque.com/blog/wcag-2-1-what-is-next-for-accessibility-guidelines/){: target="_blank"}
- [웹접근성 국가표준 개정 소개](https://seculayerlab.tistory.com/m/48){: target="_blank"}

- [한국형 웹 콘텐츠 접근성 지침 2.2](https://www.samsungfashion.com/webacc.do){: target="_blank"}
- [AOA GITBOOK](https://aoa.gitbook.io/skymimo/undefined){: target="_blank"}


