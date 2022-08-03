# CSS layout

---

- CSS layout techniques
  
  - display
  
  - position
  
  - float(1996) : Internet explore에서 많이 사용
  
  - flexbox(2012)
  
  - grid(2017)
  
  - 기타
    
    - responsivee web design/ Media queries

---

- CSS 원칙
  
  - normal flow
    
    - 모든 요소는 네모(박스모델) : 좌측 상단부터 쌓임
    
    - 왼쪽에서 오른쪽으로 가로로 쌓임 : inline direction
    
    - 위에서 아래로 세로로 쌓임 : block direction
  
  ---
  
  - Float
    
    - 박스를 왼쪽 혹은 오른쪽으로 이동시켜 텍스트를 포함 인라인 요소들이 주변을 wrapping 하도록 함
    
    - 요소가 normal flow를 벗어남
    
    - 속성
      
      - none : 기본값
      
      - left : 왼쪽으로 띄움
      
      - right : 오른쪽으로 띄움
  
  ---
  
  - flexbox
    
    - css flexible box layout 
      
      - internet explore에서는 부분지원 되서 사용하기 힘듬
    
    - 행과 열 형태로 아이템을 배치하는 1차원 레이아웃 모델
    
    - 축
      
      - main axis(메인 축)
      
      - cross axis(교차 축) : 메인 축의 수직방향
    
    - 구성요소
      
      - Flex container(부모 요소)
      
      - Flex item(자식요소)
    
    - display: flex; 
      
      - 정렬하려는 **부모요소**에 선언
        
        - 하위에 item은 자동으로 정렬
      
      - linline direction으로 내용의 크기만큼으로 정렬
    
    - display: inline flex;
      
      - 정렬하려는 **부모요소**에 선언
      
      - 내부의 요소의 크기에 맞게 줄어듬
    
    - flexbox 생성이유
      
      - 이전까지는 float와 position으로만 normal flow를 벗어날 수 있음
        
        - 수직정렬 어려움 해결
        
        - 아이템 너비와 높이 간격을 동일하게 배치하는 것이 어려움 해결
    
    - flex 속성
      
      - 배치속성
        
        - flex-direction 
          
          - main axis 기준방향설정
          
          - flex-direction: row; --->
            
            - main axis : 왼쪽에서 오른쪽(가로)
            
            - cross axis : main axis 수직
          
          - flex-direction: row reverse; <---
            
            - 가로방향으로 큰 크기 순 (오른쪽 정렬)
          
          - flex-direction: cloum reverse;
            
            - 세로방향으로 큰 크기 순
        
        - flex-wrap
          
          - 아이템이 컨테이너를 벗어 나는 경우 해당 영역 내에 배치되도록 설정
          
          - flex-wrap: wrap; 
            
            - 줄바꿔서 컨테이너 내에 모두 배치
          
          - flex-wrap: nowrap;(기본값)
            
            - 크기를 줄여서 컨테이너 내에 한줄로 모두 배치
        
        - flex-flow: direction방향 wrap설정;
          
          - direction, wrap 값을 차례대로 작성
      
      - 공간나누기
        
        - justify-content(main axis)
          
          - main axis 기준으로 공간 배분
            
            - main axis : 왼쪽에서 오른쪽인상태에서
              
              - flex-start
                
                - 왼쪽배분
              
              - flex-end
                
                - 오른쪽배분
              
              - center
                
                - 가운데배분
              
              - space-between
                
                - 좌우 배분
              
              - space-around
                
                - 아이템 기준으로 양쪽 공간이 같음
              
              - space-evenly
                
                - 빈공간의 크기가 같음
        
        - align-content(cross axis)
          
          - cross axis 기준으로 공간 배분(아이템 한줄 배치시 확인 불가)
            
            - cross axis : 위에서 아래인  상태에서
              
              - flex-start
                
                - 위쪽배분
              
              - flex-end
                
                - 아래쪽배분
              
              - center
                
                - 가운데배분
              
              - space-between
                
                - 상하 배분
              
              - space-around
                
                - 아이템 기준으로 위아래 공간이 같음
              
              - space-evenly
                
                - 빈공간의 크기가 같음
      
      - 정렬
        
        - align-items
          
          - 모든 아이템을 cross axis 기준으로 정렬
            
            - stretch(기본값)
              
              - 컨테이너를 가득 채움
            
            - flex-start
              
              - 위
            
            - flex-end
              
              - 아래
            
            - center
              
              - 가운데
            
            - baseline
              
              - 텍스트의 베이스라인에 기준선을 맞춤
        
        - align-self
          
          - 개별 아이템을 cross axis 기준으로 정렬
            
            - stretch(기본값)
              
              - 컨테이너를 가득 채움
            
            - flex-start
              
              - 위
            
            - flex-end
              
              - 아래
            
            - center
              
              - 가운데
            
            - baseline
              
              - 텍스트의 베이스라인에 기준선을 맞춤
      
      - 기타
        
        - flex-grow 
          
          - 남은 영역(여백)을 아이템에 분배
        
        - order
          
          - 배치 순서
            
            - -1 : 맨앞 배치
            
            - 0 : order 지정 안된 아이템 보다 앞으로 배치
            
            - 1~ : order 지정 안된 아이템 다음으로 배치
    
    


