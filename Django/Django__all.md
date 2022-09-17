# Django

---

- Framework
  
  - **서비스 개발에 필요한 기능들을 미리 구현해서 모아 놓은 것**
  
  - Frame(뼈대, 틀) + Work(일하다)
    
    - 일정한 틀을 가지고 일하다
    
    - 제공받은 도구들과 뼈대 규약을 가지고 무언가를 만드는 일
    
    - 특정 프로그램을 개발하기 위한 여러 도구들과 규약 제공

- WWW(world wide web)
  
  - 전세계에 퍼져 있는 거미줄 같은 연결망
    
    - 인터넷을 이용하는 것은 전세계의 컴퓨터가 연결되어 있는 하나의 인프라를 이용하는 것

- 클라이언트-서버
  
  - 웹 서비스 동작의 기반
  
  - 클라이언트 / 서버 모두 하나의 컴퓨터이며 상호작용을 통해 웹 서비스가 동작
    
    - 동작과정 (구글 홈페이지 접속 시)
      
      1. 구글 컴퓨터에게 'google 홈페이지.html' 파일을 요청
      
      2. 구글 컴퓨터가 요청을 받아 'google 홈페이지.html' 파일을 인터넷으로 응답해줌
      
      3. 웹 브라우저가 html 파일을 해석해서 보여줌
  1. **클라이언트** (웹 브라우저)
     
     - 서비스를 요청하는 주체
  
  2. **서버** (웹 페이지 / 사이트 OR 앱을 저장하는 컴퓨터)
     
     - 요청에 대한 서비스를 응답하는 주체

---

- 웹 브라우저
  
  - 웹에서 페이지를 찾아서 보여주고 하이퍼링크를 통해 다른 페이지로 이동 할 수 있게 하는 프로그램
  
  - 랜더링 
    
    - 웹페이지 파일을 우리가 보는 화면으로 바꿔줌

- 웹 페이지
  
  - 웹에 있는 문서 
    
    - 우리가 보는 화면 한장 한장이 웹 페이지
  
  - 웹 페이지 종류
    
    1. 정적 웹 페이지 (Static web page)
       
       - 있는 그대로를 제공하는 것(served as-is)을 의미
       
       - 한 번 작성 된 HTML 파일의 내용이 변하지 않고 모든 사용자에게 동일한 모습으로 전달
         
         - 서버에 미리 저장된 HTML 파일 그대로 전달된 웹 페이지
         
         - 같은 상황에서 모든 사용자에게 동일한 정보를 표시
    
    2. 동적 웹페이지 (Dynamic web page)
       
       - 사용자의 요청에 따라 추가적인 수정이 되어 전달되는 웹페이지
       
       - 웹페이지의 내용을 바꿔주는 주체 == 서버
         
         - 서버의 프로그램이 웹페이지를 변경(django가 이를 쉽게 만들 수 있게 해주는 프레임 워크)

---

- Design pattern
  
  - 자주 사용하는 구조의 해결책을 일반화해서 하나의 공법으로 만들어 둔 것

- MVC 디자인 패턴
  
  - 데이터 및 논리 제어를 구현하는데 널리 사용되는 소프트웨어 디자인 패턴
  
  - 하나의 큰 프로그램을 세가지 역할로 구분한 개발 방법론
  
  - 목적
    
    - 관심사를 분리하여 업무 분리 및 향상된 관리 제공
    
    - 개발 효율성 및 유지보수가 쉬워짐
    
    - 다수의 멤버로 개발하기 용이함
  
  - model
    
    - 데이터 관련된 로직을 관리
    
    - 응용 프로그램의 데이터 구조를 정의하고 데이터 베이스의 기록을 관리
  
  - view
    
    - 레이아웃과 화면을 처리
    
    - 화면상의 사용자 인터페이스 구조와 레이아웃을 정의
  
  - controller
    
    - 명령을 model과 view 부분으로 연결
    
    - 클라이언트의 요청에 대해 처리를  분기하는 역할

- MTV 디자인 패턴
  
  - model
  
  - template
  
  - view

- django가 담당하는 부분
  
  - model / view / urls / template 
  
  - 담당하지 않는 부분은 http response

---

- django 기본설정
  
  - 프로젝트 생성 `django-admin startproject firstpjt .`
  
  - 서버 실행 `python manage.py runserver`
  
  - 앱 생성 `python manage.py startapp articels`
    
    - 애플리케이션 이름은 복수형으로 작성하는 것을 권장
    
    - 애플리케이션은 반드시 생성후에 등록

--- 

- 요청과 응답
  
  - url > view > template 순서로 흐름 이해

- `render(request, template_name, context)`
  
  - 주어진 템플릿을 주어진 컨텍스트 데이터와 결합하고 렌더링된 텍스트와 함께 httpresponse(응답) 객체를 반환하는 함수
    
    1. request 
       
       - 응답을 생성하는데 사용되는 요청 객체
    
    2. template_name
       
       - 템플릿의 전체 이름 또는 템플릿 이름의 경로
    
    3. context
       
       - 템플릿에서 사용할 데이터(딕셔너리 타입)

- templates
  
  - 실제 내용을 보여주는데 사용되는 파일
  
  - 파일 구조나 레이아웃을 정의

---

- django template
  
  - 데이터 표현을 제어하는 도구이자 표현에 관련된 로직

- django template language(DTL)
  
  - django template의 built-in template system
  
  - python처럼 프로그래밍 구조를 사용할 수 있지만 python 코드로 실행되는 것은 아니다
  
  - 프로그래밍적 로직이 아니라 프레젠테이션을 표현하기 위한 것

- DTL syntax
  
  1. variable
     
     - 변수명은 영어, 숫자 밑줄의 조합으로 구성될 수 있으나 밑줄로는 시작할 수 없다(공백이나 구두점 사용 불가)
     
     - .(dot)을 사용하여 변수 속성에 접근 가능
     
     - render에서 넘어온 context의 key 값이 변수명이 된다
  
  2. filters
     
     - 변수 수정할 때 사용
     
     - 60개의 built-in template filter 제공
  
  3. tags
     
     - 출력 텍스트를 만들거나, 반복 또는 논리를 수행하여 제어 흐름을 만듬
     
     - 일부는 시작태그 뿐만 아니라 종료태그도 필요하다
       
       - {% if %}{% endif %}
  
  4. comments
     
     - 주석처리가 가능하다 
     
     - {# #} or {% comment %}{% endcomment %}

---

- template inheritance(템플릿 상속)
  
  - 기본적으로 코드의 재사용성에 초점을 맞춤
  
  - 사이트의 모든 공통 요소를 포함
  
  - skeleton 템플릿으로 하위 템플릿을 재정의(override)
  
  - {% extends 'base.html' %}
    
    - 자식 템플릿이 부모 템플릿을 확장한다는 것을 알림
    
    - 반드시 템플릿의 최상단에 작성
  
  - {% block content %}{% endblock content %}
    
    - 하위 템플릿에서 재지정 할 수 있는 블록을 정의
    
    - 하위 템플릿이 채울 수 있는 공간
    
    - endblock에 태그의 이름은 가독성을 높이기 위한 것

---

- sending form data(client)

- html <form>
  
  - 데이터가 전송되는 방법을 정의
  
  - 사용자로부터 할당된 데이터를 서버로 전송
  
  - action
    
    - 입력 데이터가 전송될 url
    
    - 데이터를 어디로 보낼 것인지 지정하는 것 반드시 유효한 url
    
    - 속성을 지정하지 않으면 현재 form의 페이지의 url로 보내짐
  
  - method
    
    - 데이터를 어떻게 보낼 것인지 정의
    
    - 입력 데이터의 http request methods를 지정
    
    - html form 데이터는 오직 2가지 방법으로만 전송(get/post)

- html <input>
  
  - 사용자로부터 데이터를 입력받기 위해 사용
  
  - type 속성에 따라 동작 방식이 다르다
  
  - input 요소의 동작 방식은 type 특성에 따라 달라지고 지정하지 않으면 text
  
  - name
    
    - form을 통해 데이터를 제출했을 때 name 속성에 설정된 값을 서버로 전송하고, 서버는 name 속성에 설정된 값을 통해 사용자가 입력한 데이터 값에 접근
    
    - name은 key / 입력값은 value가 된다
    
    - get방식에서는 ?key=value&key=value/ 형식으로 전달

- http request method
  
  - http 문서와 같은 리소스들을 가져올 수 있도록 해주는 프로토콜
  
  - get post put delete

- get
  
  - 서버로부터 정보를 조회하는데 사용(리소스 요청)
  
  - 데이터를 가져올 때만 사용(url에 포함되어 서버로 보내짐)
  
  - GET과 get 모두 대소문자 관계없이 작동하지만 명시적 표현을 위해 대문자 사용을 권장

---

- retrieving the data(server)
  
  - 데이터 가져오기(검색하기)
  
  - 서버는 클라이언트로 받은 key value 쌍의 목록과 같은 데이터를 받음

---

- trailing slashes
