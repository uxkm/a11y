# Chapter 1. SASS와 SCSS의 개요

## 1.1 SASS란 무엇인가?

SASS는 “Syntactically Awesome Style Sheets”의 약자로, CSS를 **더 프로그래밍스럽게 작성할 수 있도록 확장한 전처리기**입니다. SASS는 반복을 줄이고, 코드 재사용성을 높이며, 구조적으로 스타일을 관리할 수 있도록 다양한 기능을 제공합니다.

- **2006년** Hampton Catlin이 고안하고 Natalie Weizenbaum이 개발
- Ruby 언어로 작성되었고, 이후 Dart로 이식됨
- SCSS 문법을 포함하며, 다양한 CSS 확장 문법을 지원함

SASS는 다음과 같은 이유로 널리 사용됩니다:

- 변수, 믹스인, 조건문, 반복문 등을 지원
- 코드 중복 최소화
- 스타일시트 모듈화 가능
- CSS와 완전 호환되는 SCSS 문법

---

## 1.2 SCSS란 무엇인가?

SCSS는 SASS의 최신 구문으로, **기존 CSS 문법과 호환되도록 설계**되었습니다.  
CSS와 같은 중괄호(`{}`)와 세미콜론(`;`) 문법을 사용하므로 기존 CSS를 그대로 가져와 사용할 수 있습니다.

| 항목      | SASS 문법 예              | SCSS 문법 예              |
|-----------|---------------------------|----------------------------|
| 스타일     | 들여쓰기 기반              | 중괄호 + 세미콜론 사용       |
| 변수       | `$primary: #f00`          | `$primary: #f00;`          |
| 선택자 중첩| `.nav
  ul
    li`      | `.nav { ul { li { ... }}}` |
| 사용성     | 초기 버전                 | 현재 표준 (CSS 친화적)       |

```scss
// SCSS 예시
$primary-color: #3498db;

.button {
  background: $primary-color;
  &:hover {
    background: darken($primary-color, 10%);
  }
}
```

---

## 1.3 왜 SCSS를 사용하는가?

| 기능             | 순수 CSS | SCSS |
|------------------|----------|------|
| 변수             | ❌       | ✅   |
| 조건문/반복문    | ❌       | ✅   |
| 믹스인/상속       | ❌       | ✅   |
| 모듈화 구조       | 제한적   | 강력 |

SCSS는 다음과 같은 이유로 실무에서 필수 도구로 자리잡았습니다.

- 디자인 시스템 구성 시 일관성 유지
- 다크모드, 반응형 등 스타일 분기 처리 용이
- 유지보수, 리팩토링에 유리한 구조화 가능

---

## 1.4 SCSS의 진화

- 2006년: SASS 최초 릴리스 (`.sass` 확장자)
- 2010년: SCSS 구문 도입 (`.scss` 확장자)
- 2020년: `@use`, `@forward` 등 모듈 시스템 도입
- 현재: Dart Sass가 공식 구현체, LibSass는 중단됨

---

## 1.5 어떤 프로젝트에 적합한가?

| 프로젝트 유형         | SCSS 활용 이유 |
|----------------------|----------------|
| 컴포넌트 기반 UI      | 재사용성, 모듈화 |
| 디자인 시스템 구축    | 변수/토큰 관리 |
| 반응형/다크모드 지원 | 조건별 스타일 분기 |
| 대규모 팀 협업        | 7-1 구조, 네임스페이스 |
| 퍼블리싱 & 문서화     | 구조적 스타일 관리 |

---

## 1.6 정리

- SASS는 CSS를 코드로 발전시킨 전처리기이다.
- SCSS는 그 최신 문법이며 CSS와 호환된다.
- 모듈화, 반복 제거, 다크모드 설계 등 실무에서 광범위하게 쓰인다.

➡️ 다음 장에서는 다양한 프레임워크에서 SCSS를 설정하고 통합하는 방법을 다룬다.