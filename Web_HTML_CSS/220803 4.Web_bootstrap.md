# Bootstrap

- CDN(content delivery(distribution) network)
  - 컨텐츠(CSS, JS, image, text등)을 효율적으로 전달하기 위해 여러 노드에 가진 네트워크에 데이터를 제공하는 시스템
    - 개별 end-user의 가까운 서버를 통해 빠르게 전달 가능(지리적 이점)
    - 외부 서버를 활용함으로써 본인 서버의 부하가 적어짐
  - css는 개발자가 다 구현해 놓아서 class만 지정해주면 된다.

---

- 기본원리
  
  - spacing(margin and padding)
    
    - {property}{sides}-{size}
      
      - property 
        
        - margin : m
        
        - padding : p
      
      - sides 
        
        - t : top
        
        - b : bottom
        
        - s : start(left)
        
        - e : end(right)
        
        - x : sides(양옆)
        
        - y : sides(위 아래)
        
        - blank : 전부다
      
      - size 
        
        - 0 : 없음
        
        - auto : 자동
        
        - 1 : spacer 0.25rem(기본 16px의 1/4인 4px)
        
        - 2 : spacer 0.5rem(8px)
        
        - 3 : spacer 1rem(16px)
        
        - 4 : spacer 1.5rem(24px)
        
        - 5 : spacer 3rem(48px)
  
  ---
  
  - color
    
    - bg-{색상이름} : 배경 색상 지정
    
    - text-{색상이름} : 글씨 색상 지정
  
  ---
  
  - text
    
    - text-{위치이름} : 글씨 위치 지정
      
      - start : 왼쪽정렬
      
      - center : 가운데정렬
      
      - end : 오른쪽정렬
    
    - fw-{}
      
      - bold
      
      - normal
      
      - light
    
    - fst-{}
      
      - italic
  
  ---
  
  - position
    
    - position-{}
      
      - static
      
      - relative
      
      - absolute
        
        - 부모가 static이 아니어야 됨
        
        - static이면 브라우저를 기준으로 이동
      
      - fixed-{}
        
        - top, bottom ...
      
      - sticky
  
  ---
  
  - display
    
    - d-{value}
      
      - none
        
        - 코드를 넣어도 보이지 않음
      
      - inline
      
      - inline-block
      
      - grid
      
      - flex
    
    - d-{breakpoint}-{value}
      
      - breakpoint를 지정하면 화면의 크기에 따라 나타나고 사라지고 지정 가능
  
  ---
  
  - components
    
    - bootstrap의 다양한 UI요소를 활용
    
    - 기본 제공된 components를 변환해서 활용
      
      - button
        
        ```
        <button type="button btn-primary">Primary</button>
        ```
      
      - dropdown
      
      - form 
        
        - 데이터를 입력받을 때 사용
      
      - navbar
        
        - 네비게이션 바를 제작
      
      - carousel
        
        - 컨텐츠를 순환시키기 위한 슬라이드 쇼
      
      - modal
        
        - 사용자와 상호작용 하기 위해 사용 / 긴급상황 알리는데 사용
        
        - 현재 열려 있는 페이지 위에 도 다른 레이어 띄움
        
        - 페이지를 이동하면 자연스럽게 사라짐(배경 클릭시 사라짐)
        
        - < body>와 같은 top level에 두어야 중첩되지않고 실행이 됨
      
      - flexbox
      
      - card
        
        - responsive web(반응형 웹)
          
          - 화면의 크기에 따라 구성이 달라짐
  
  ---
  
  # grid system
  
  - resoibsive web
    
    - 다양한 화면 크기로 가진 디바이스들이 등장함에 따라 responsive web design 개념이 등장
    
    - 반응형 웹은 별도의 기술 이름이 아닌 웹디자인데 대한 접근 방식, 반응형 레이아웃 작성에 도움이 되는 사례들의 모음 등을 기술하는데 사용되는 용어
    
    - 예시
      
      - Media Queries, Flexbox, Bootstrap Grid System, The viewport meta tag
  
  - grid system
    
    - 요소들의 디자인 배치에 도움을 주는 시스템
    
    - 기본요소
      
      - column : 실제 컨텐츠를 포함하는 부분
      
      - gutter : 칼럼과 칼럼 사이의 공간
      
      - container : column들을 담고 있는 공간
    
    - flexbox로 제작
    
    - container, rows, column으로 컨텐츠를 배치하고 정렬
      
      - 12개의 column
      
      - 6개의 breakpoints
  
  - breakpoints
    
    - col-{breakpoint}-{원하는 크기(1~12)}
    
    - | Breakpoint        | Class infix | Dimensions |
      | ----------------- | ----------- | ---------- |
      | Extra small       | *None*      | <576px     |
      | Small             | `sm`        | ≥576px     |
      | Medium            | `md`        | ≥768px     |
      | Large             | `lg`        | ≥992px     |
      | Extra large       | `xl`        | ≥1200px    |
      | Extra extra large | `xxl`       | ≥1400px    |
    
    - 원하는 구간마다 표현하는 것을 다르게 지정할 수 있다
  
  - nesting
    
    - < div class="row">
      
          < div class="row">
      
          </div>
      
      </div>
    
    - 중첩
  
  - offset-{원하는크기(1~12)}
    
    - grid 칸을 비우고 싶을 때 사용
