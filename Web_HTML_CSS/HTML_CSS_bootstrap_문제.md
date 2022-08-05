HTML은 무엇을 뜻할까요?

- Hyper Text Markup Language
  
  - hyperlinks and text markup language
  
  - home tool markup language
  
  - hyper tool markup language

---

마크업 스타일 가이드

- 2space
  
  - 1space
  
  - 3space
  
  - 4space

---

다음 중 닫는 태그가 없는 요소는

- br hr img input link meta는 닫는 태그가 없고
  
  - a div title h1 style 등은 있다

---

다음중 시맨틱 태그인 것은(의미적 가치를 지니는 것)

- h1 header nav aside section article footer a form table
  
  - nonsemantic : div spam 

---

인라인요소 / 블록요소

- 인라인 :글자처럼 취급

- 블록:  한줄 모두 사용

---

텍스트요소 : a b strong i em br img span

그룹컨텐츠 : p hr ol ul pre blockquote div

---

form : 데이터 제출용 태그

- attribute
  
  - action : 처리할 서버의 url
  
  - method : 제출할 때 사용할 http 메서드
  
  - enctype: 메서드가 포스트인 경우 데이터의 유형

---

CSS는 무엇을 뜻할까요?

- cascading style sheets
  
  - creative style sheets
  
  - computer style sheets
  
  - colorful style sheets

---

CSS 우선 순위

!important > inline style > id선택자 > class선택자,속성선택자,pseudo-class > 요소 선택자,pseudo-elemnt> 소스 순서

---

CSS 정의 방법

- 인라인 `<h1 style="color: blue; font-size:100px;">hello</h1>`

- 내부참조`<style>h1{color: blue; font-size:100px;}</style>`

- 외부참조`<link rel="stylesheet" href="xxx.css">`
  
  - `h1{color: blue; font-size:100px;}`

---

CSS selector

- selector 유형
  
  - 기본 선택자 
    
    - 전체 
    
    - 요소 : html 태그를 직접 선택 `태그명{}`
    
    - 클래스 : `.클래스명`으로 선택 `.클래스명{}`
    
    - 아이디 : 하나의 문서에 하나만 사용`#아이디명{}`
    
    - 속성
  
  - 결합자 
    
    - 자손결합자 인접형제결합자
  
  - 의사 클래스/요소
    
    - 링크 동적의사클래스
    
    - 구조적의사 기타의사 의사엘리먼트 속성선택자

---

<p>1</p>

<p class="blue">2</p>

<p class="blue green">3</p>
