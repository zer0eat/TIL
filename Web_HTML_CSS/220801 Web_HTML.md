# Web

- 웹 사이트의 구성요소
  
  - 웹사이트란 브라우저를 통해 접속하는 웹페이지(문서)들의 모음
    
    - 링크 들을 통해 여러 웹페이지를 연결한 것이 웹사이트
    
    - 웹페이지는 글, 그림, 동영상 여러가지 정보를 담고 있으며 마우스로 클릭하면  다른 웹 페이지로 이동하는 링크
  
  - HTML : 구조(건물의 형태)
  
  - CSS : 표현(인테리어)
  
  - Javascript : 동작(엘리베이터)

- 웹 표준과 크로스 브라우징
  
  - 웹사이트는 브라우저를 통해 동작
  
  - 브라우저마다 동작이 약간씩 달라 문제가 생기는 경우가 많음(파편화)
  
  - 해결책으로 웹 표준이 등장
    
    - 웹표준
      
      - 웹에서 표준적으로 사용되는 기술이나 규칙
      
      - 크로스브라우징 : 어떤 브라우저든 웹페이지가 동일하게 보이도록 함
        
        - 팁 버너스리 : 1994년에 W3C에서 설립
        
        - WHATWG :  HTML5 제안(HTML living standard)

- 개발 환경 설정
  
  - 크롬 개발자 도구
    
    - 웹브라우저 크롬에서 제공하는 개발과 관련된 다양한 기능 제공
    
    - 주요기능
      
      - elements : DOM 탐색 및 CSS확인 및 변경
      
      - styles : 요소에 적용된 CSS확인
      
      - computed :  스타일이 계산된 최종 결과
      
      - event listeners : 해당 요소에 적용된 이벤트(JS)
      
      - sources, network, perfomance, application, security, audits 등 

---

## HTML

- HTML : hyper text markup language의 약자
  
  - 웹페이지를 작성(구조화)하기 위한 언어
  
  - hyper text 
    
    - 참조(하이퍼링크)를 통해 사용자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트
  
  - markup language
    
    - 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어  
    
    - ex) HTML, markdown
  
  - HTML 스타일가이드
    
    - 마크업 스타일 가이드(2 space)
    
    - 2칸 안띄어도 문제는 없지만 가독성을 위한 스타일 가이드
  
  ---
  
  ### 기본구조
  
  - html : 문서의 최상위(root)요소
  
  - head : 문서 메타데이터 요소<ex)사진의 해상도, 찍은곳, 시간 ...>
    
    - 문서제목, 인코딩, 스타일, 외부파일 로딩 등
    
    - 일반적으로 브라우저에 나타나지 않는 내용
    
    - 예시
      
      - `<title>` : 브라우저 상단의 타이틀
      
      - `<meta>` : 문서 레벨 메타데이터 요소
      
      - `<link>` : 외부 리소스 연결요소 (CSS파일, favicon 등)
      
      - `<script>` : 스크립트 요소 (Javascript 파일/코드)
      
      - `<style>` : CSS 직접 작성
      
      - open graph protocol
        
        - 메타 데이터를 표현하는 새로운 규약
          
          - HTML 문서의 메타 데이터를 통해 문서의 정보전달
          
          - 메타정보에 해당하는 제목 설명 등을 쓸 수 있도록 정의
  
  - body : 문서 본문요소 <ex)사진>
    
    - 실제 화면 구성과 관련된 내용
  
  - 요소(element)
    
    - HTML 요소는 시작태그와 종료태그 그리고 태그 사이에 위치한 내용으로 구성
      
      - 시작태그 + 내용 + 종료태크
      
      - 요소는 태그로 컨텐츠(내용)를 감싸는 것으로 그 정보의 성격과 의미를 정의
      
      - 내용이 없는 태그들도 존재(닫는 태그가 없음)
        
        - br, hr, img, input, link, meta
    
    - 요소는 중첩(nested)될 수 있음
      
      - 요소의 중첩을 통해 하나의 문서를 구조화
      
      - 여는태그와 닫는태그의 쌍을 잘 확인
        
        - 오류를 반환하는 것이 아닌 그냥 레이아웃이 깨진 상태로 출력되기 때문에 디버깅이 힘듬
  
  - 속성(attribute)
    
    - <a href="https://google.com"></a>
      
      - : 속성명 : href  /  속성값 : "[https://google.com"](https://google.com")
    
    - 스타일 가이드
      
      - 공백 사용 불가, "" 쌍따옴표만 사용 가능
    
    - 속성을 통해 태그의 부가적인 정보를 설정할 수 있음
    
    - 요소는 속성을 가질 수 있으며, 경로나 크기와 같은 추가적인 정보를 제공
    
    - 요소의 시작 태그에 작성하며 보통 이름과 값이 하나의 쌍으로 존재
    
    - 태그와 상관없이 사용가능한 속성(HTML global attribute)
    
    - HTML global attribute
      
      - 모든 HTML요소가 공통으로 사용할 수 있는 대표적인 속성
        
        - (몇몇 요소에는 효과가 없을 수 있음)
          
          - id : 문서 전체에서 유일한 고유 식별자 지정
          
          - class : 공백으로 구분된 해당 요소의 클래스의 목록
            
            - (CSS, JS에서 요소를 선택하거나 접근)
          
          - data-* : 페이지에 개인 사용자 정의 데이터를 저장하기 위해 사용
          
          - style : inline 스타일
          
          - title : 요소에 대한 추가 정보 지정
          
          - tabindex : 요소의 탭 순서
  
  - 시맨틱 태그
    
    - HTML 태그가 특정 목적, 역할 및 의미적가치(semantic value)를 가지는 것
      
      - ex) h1 태그는 ' 이 페이지에서 최상위 제목'인 텍스트를 감싸는 역할
    
    - non semantic요소로는 div, span 등이 있다
      
      - a, form, table 태그들도 시맨틱태그로 볼수 있음
    
    - HTML5에서는 기존에 단순히 콘텐츠의 구획을 나타내기 위해 사용한 div 태그를 대체하여 사용하기 위해 의미론적 요소를 담은 태그들이 추가
    
    - 대표적인 시맨틱 태그
      
      - header : 문서 전체나 섹션의 헤더(머리말)
      
      - nav : 내비게이션
      
      - aside : 사이드에 위치한 공간, 메인 콘텐츠와 관련성이 적은 콘텐츠
      
      - section : 문서의 일반적인 구분, 컨텐츠의 그룹을 표현
      
      - article : 문서, 페이지, 사이트 안에서 독립적으로 구분되는 영역
      
      - footer : 문서 전체나 섹션의 푸터(마지막 부분)
  
  - 랜더링(rendaering)
    
    - 웹사이트 코드를 사용자가 보게되는 웹사이트로 바꾸는 과정
    
    - DOM(document obnect model)트리
      
      - 텍스트 파일인 HTML 문서를 브라우저에서 렌더링 하기 위한 구조
        
        - HTML 문서에 대한 모델을 구성
        
        - HTML문서 내의 각 요소에 접근 / 수정에 필요한 프로퍼티와 메서드 제공
  
  ---
  
  ### 문서 구조화
  
  - HTML 요소는 크게 인라인 / 블록 요소로 나눔
    
    - 인라인 : 글자처럼 취금
    
    - 블록 : 한 줄 모두 사용
  
  - 텍스트 요소
    
    - a태그 `<a> </a>`
      
      - href 속성을 활용하여 다른 URL로 연결하는 하이퍼링크 생성
    
    - b태그`<b> </b>`
      
      - 굵은 글씨 요소
    
    - strong태그`<strong> </strong>`
      
      - 강조하고자 하는 요소(굵은글씨)
    
    - i태그`<i> </i>`
      
      - 기울임 글씨 요소
    
    - em태그`<em> </em>`
      
      - 강조하고자 하는 요소(기울임 글씨)
    
    - br태그`<br>`
      
      - 텍스트 내에 줄 바꿈
    
    - img태그`<img>`
      
      - src 속성을 활용하여 이미지 표현
    
    - span태그`<span> </span>`
      
      - 의미 없는 인라인 컨테이너 
  
  - 그룹컨텐츠
    
    - p태그`<p> </p>`
      
      - 하나의 문단(paragraph)
    
    - hr태그`<hr>`
      
      - 문단 레벨 요소에서의 주제의 분리
      
      - 수평선으로 표현(a horizontal rule)
    
    - odered태그`<ol> </ol>`
      
      - 순서가 있는 리스트
    
    - unordered태그`<ul> </ul>`
      
      - 순서가 없는 리스트
    
    - pre태그`<pre> </pre>`
      
      - HTML에 작성한 내용 그대로 표현
      
      - 보통 고정폭 글꼴이 사용되고 공백문자 유지
    
    - blockquote태그`<blockquote> </blockquote>`
      
      - 텍스트가 긴 인용문 주로 들여쓰기로 표현
    
    - div태그`<div> </div>`
      
      - 의미 없는 블록 레벨 컨테이너
  
  - form
    
    - `<form>`은 정보(데이터)를 서버에 제출하기 위해 사용하는 태그
      
      - 데이터를 입력받기 위한 태그<ex)아이디, 비밀번호 입력, 검색창>
    
    - 기본속성
      
      - action : form을 처리할 서버의 URL(데이터를 보낼 곳)
      
      - method : form을 제출할 때 사용할 HTTP 메서드 (GET 혹은 POST)
      
      - enctype : method가 post인 경우 데이터의 유형
        
        - application/x-www-form-urlencoded : 기본값 
        
        - multipart/form-data : 파일 전송시(input type이 file인 경우)
        
        - text/plain : HTML5 디버깅 용(잘 사용하지 않음)
  
  - input
    
    - 다양한 타임을 가지는 입력 데이터 유형과 위젯이 제공됨
    
    - <input> 대표적인 속성
      
      - name : form control에 적용되는 이름(이름/값 페어로 전송)
      
      - value : form control에 적용되는 값(이름/값 페어로 전송)
      
      - required, readonly, autofocus, autocomplete, disabled
    
    - input label
      
      - label을 클릭하여 input 자체의 초점을 맞추거나 활성화 시킬 수 있음
        
        - 사용자는 선택할 수 있는 영역이 늘어나 웹/모바일(터치)환경에 편하게 사용
        
        - label과 input의 관계가 시각적 뿐만 아니라 화면리더기에서도 label을 읽어 쉽게 내용을 확인
      
      - <input>에 id 속성을, <label>에는 for 속성을 활용하여 상호 연관을 시킴
    
    - input 유형 - 일반
      
      - 일반적으로 입력받기 위해 제공, 타입별로 HTML 기본 검증 혹은 추가 속성을 활용할 수 있음
      
      - text : 일반 텍스트 입력
      
      - password : 입력 시 값이 보이지 않고 문자를 특수기호(*)로 표현
      
      - email : 이메일 형식이 아닌 경우 form 제출 불가
      
      - number : min, max, step 속성을 활용하여 숫자 범위 설정 가능
      
      - file : accept 속성을 활용하여 파일 타입 지정 가능
    
    - input 유형 - 항목 중 선택
      
      - 일반적으로 label 태그와 함께 사용하여 선택항목 지정
      
      - 동일 항목에 대해 name을 지정하고 선택된 항목에 대한 value를 지정
      
      - checkbox : 다중선택
      
      - radio : 단일 선택
    
    - input 유형 - 기타
      
      - 다양한 종류의 input을 위한 picker를 제공
        
        - color 
        
        - date
      
      - hidden input을 활용하여 사용자 입력을 받지 않고 서버에 전송되어야 하는 값을 설정
        
        - hidden : 사용자에게 보이지 않는 input

# 
