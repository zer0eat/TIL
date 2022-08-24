# Algorithm

---

## 큐(Queue)

---

- 특성
  
  - 스택과 마찬가지로 삽입과 삭제의 위치가 제한적인 자료구조(**선형 자료구조**)
  
  - **선입선출구조(FIFO : first in first out)**
    
    - 큐에 삽입한 순서대로 원소가 저장
    
    - 뒤에서만 삽입하고 앞에서는 삭제만 이뤄지는 구조 
      
      - 머리(front) : 저장된 원소 중 첫 번째 원소 또는 삭제된 위치
      
      - 꼬리(rear) : 저장된 원소 중 마지막원소
    
    - 큐의 기본연산
      
      - enQueue(item) : 큐의 뒤쪽에 원소를 삽입
      
      - deQueue() : 큐의 앞쪽에서 원소를 삭제
      
      - createQueue() : 공백상태의 큐
      
      - isEmpty() : 큐가 공백상태인지 확인
      
      - isFull() : 큐가 포화상태인지 확인
      
      - Qpeek() : 큐의 앞쪽에서 원소를 삭제없이 반환
    
    - 큐의 연산과정
      
      1. 공백큐 생성 : createQueue() / front = -1 / rear = -1
      
      2. 원소 A 삽입 : enQueue(A) / rear = 0
      
      3. 원소 B 삽입 : enQueue(B) / rear = 1
      
      4. 원소 반환 삭제 : deQueue() / front = 0이되며 0의 위치에 있는 A 나옴
      
      5. 원소 C 삽입 : enQueue(C) / rear = 2
      
      6. 원소 반환 삭제 : deQueue() / front = 1이되며 1의 위치에 있는 B 나옴
      
      7. 원소 반환 삭제 : deQueue() / front = 2이되며 2의 위치에 있는 C 나옴
         
         - 비어있는 상태가 되면 front = rear

---

- 큐의 구현
  
  - 선형큐
    
    - 1차원 배열을 이용한 큐
      
      - 큐의 크기 = 배열의 크기
      
      - front = 저장된 첫번째 원소의 인덱스
      
      - rear = 저장된 마지막 원소의 인덱스
    
    - 상태표현
      
      - 초기상태 : front =rear = -1
      
      - 공백상태 : front == rear
      
      - 포화상태 : rear == n - 1 (n 배열의 크기 / n -1 배열의 마지막 인덱스)
  
  - 초기 공백큐 생성
    
    - 크기가 n인 1차원 배열 생성
    
    - front / rear를 -1로 초기화
  
  - 삽입 : enQueue(item)
    
    - 마지막 원소 뒤에 새로운 원소를 삽입하기 위해
      
      1. rear 값을 하나 증가 시켜 새로운 원소를 삽입할 자리를 마련
      
      2. 그 인덱스에 해당하는 배열원소 Q[rear]에 item을 저장
    
    ```python
    def enQueue(item):
        global rear
        if isFull() : print("queue_full")
        else:
            rear = rear + 1
            Q[rear] = item
    ```
  
  - 삭제 : deQueue()
    
    - 가장 앞에 있는 원소를 삭제하기 위해
      
      1. front 값을 하나 증가시켜 큐에 남아있게 될 첫번째 원소 이동
      
      2. 새로운 첫번째 원소를 리턴함으로써 삭제와 동일한 기능
    
    ```python
    deQueue()
        global front
        if(isEmpty()): then Queue_empty()
        else{
            front = front +1
            return Q[front]
        }
    ```
  
  - 공백상태 및 포화 상태 검사 : isEmpty() / isFull()
    
    - 공백상태 : front == rear
    
    - 포화상태 : rear == n -1 (n 배열의크기 / n -1 배열의 마지막 인덱스)
    
    ```python
    def isEmpty():
        return front == rear
    def Full:
        return rear == len(Q)-1
    ```
  
  - 검색 : Qpeek()
    
    - 가장 앞에 있는 원소를 검색하여 반환하는 연산
    
    - 현재 front의 한자리 뒤(front + 1)에 있는 원소, 즉 큐의 첫번째에 있는 원소를 반환
    
    ```python
    def Qpeek():
        if isEmpty() : print('queue_empty')
        else: return Q[front + 1]
    ```

---

- 선형 큐 이용시의 문제점
  
  - 잘못된 포화상태 인식
    
    - 선형큐를 이용하여 원소의 삽입과 삭제를 계속할 때, 배열의 앞부분에 활용할 수 있는 공간이 있음에도 불구하고, rear = n-1인 상태 즉, 포화상태로 인식하여 더 이상의 삽입을 수행하지 않게 됨
  
  - 해결방법 1
    
    - 매 연산이 이루어질 때마다 저장된 원소들을 배열의 앞부분으로 모두 이동시킴
    
    - 원소 이동에 많은 시간이 소요되어 큐의 효율성이 급격히 떨어짐
  
  - 해결방법 2
    
    - 1차원 배열을 사용하되, 논리적으로 배열의 처음과 끝이 연결되어 원형 형태의 큐를 이룬다고 가정하고 사용
    
    - 원형 큐의 논리적 구조
      
      - 초기 공백상태
        
        - front = rear = 0
      
      - index의 순환
        
        - front와 rear의 위치가 배열의 마지막 인덱스인 n-1를 가르킨 후, 그 다음에 논리적 순환을 이루어 배열의 처음 인덱스인 0으로 이동
        
        - 이를 위해 나머지 연산자 mod를 사용
      
      - front 변수
        
        - 공백 상태와 포화 상태 구분을 쉽게 하기 위해 front가 있는 자리는 사용하지 않고 항상 빈자리로 둠
      
      - 삽입 위치 및 삭제 위치
        
        - 선형큐 
          
          - 삽입 위치 rear = rear + 1 
          
          - 삭제위치 front = front + 1
        
        - 원형큐
          
          - 삽입 위치 rear = (rear + 1) mod n 
          
          - 삭제위치 front = (front + 1) mod n
      
      - 원형 큐의 연산 과정
        
        1. create queue / front = 0 / rear = 0
        
        2. enQueue(A) / front = 0 / rear = 1
        
        3. enQueue(B) / front = 0 / rear = 2
        
        4. deQuene() / front = 1 / rear = 2
        
        5. enQuene(C) / front = 1 / rear = 3
        
        6. enQuene(C) / front = 1 / rear = 0
           
           - rear의 다음칸에 front가 있으면 가득 찬 상태 (front == rear + 1)
           
           - 비어있는 상태는 (front == rear)
      
      - 초기 공백 큐의 생성
        
        - 크기 n인 1차원 배열 생성
        
        - front와 rear를 0으로 초기화
      
      - 공백상태 및 포화상태 검사 : isEmpty(), isFull()
        
        - 공백상태 : front == rear
        
        - 포화상태 
          
          - 삽입할 rear의 다음 위치 == 현재 front - (rear + 1) mod n == front
        
        ```python
        def isEmpty():
            return front == rear
        def isFull():
            return (rear + 1) % len(cQ) == front
        ```
      
      - 삽입 : enQueue(item)
        
        - 마지막 원소 뒤에 새로운 원소를 삽입하기 위해
          
          1. rear 값을 조정하여 새로운 원소를 삽입할 자리를 마련
             
             - rear = (rear +1) mod n
          
          2. 그 인덱스에 해당하는 배열원소 cQ[rear]에 item을 저장
          
          ```python
          def enQueue(item):
              global rear
              if isFull():
                  print('Queue_Full')
              else:
                  front = (front + 1) % len(cQ)
                  cQ[rear] = item
          ```
      
      - 삭제 : deQueue(), delete()
        
        - 가장 앞에 있는 원소를 삭제하기 위해
          
          1. front 값을 조정하여 삭제할 자리를 준비
          
          2. 새로운 front원소를 리턴함으로써 삭제와 동일한 기능
          
          ```python
          def deQueue():
              global front
              if isEmpty():
                  print('Queue_empty')
              else:
                  front = (front + 1) % len(cQ)
                  return cQ[front]
          ```

---

- 우선순위 큐(priority Queue)
  
  - 우선순위 큐의 특성
    
    - 우선순위를 가진 항목들을 저장하는 큐
    
    - FIFO 순서가 아니라 우선순위가 높은 순서대로 먼저 나가게 된다
  
  - 우선순위 큐의 적용 분야
    
    - 시뮬레이션시스템
    
    - 네트워크 트래픽 제어
    
    - 운영체제의 테스크 스케줄링
  
  - 우선순위 큐의 구현
    
    - 배열을 이용한 우선순위 큐
    
    - 리스트를 이용한 우선순위 큐
  
  - 배열을 이용하여 우선순위 큐 구현
    
    - 배열을 이용하여 자료 저장
    
    - 원소를 삽입하는 과정에서 우선순위를 비교하여 적절한 위치에 삽입하는 구조
    
    - 가장 앞에 최고 우선순위의 원소가 위치하게 됨
  
  - 문제점
    
    - 배열을 사용하므로, 삽입이나 삭제 연산이 일어날 때 원소의 재배치가 발생
    
    - 이에 소요되는 시간이나 메모리 낭비가 큼

---

- 큐의 활용 : 버퍼(buffer)
  
  - 버퍼
    
    - 데이터를 한 곳에서 다른 한 곳으로 전송하는 동안 일시적으로 그 데이터를 보관하는 메모리의 영역 (순서를 유지)
    
    - 버퍼링 : 버퍼를 사용하는 방식 또는 버퍼를 채우는 동작을 의미
  
  - 버퍼의 자료구조
    
    - 버퍼는 일반적으로 입출력 및 네트워크와 관련되 기능에서 이용
    
    - 순서대로 입력/출력/전달 되어야 하므로 FIFO 방식의 자료구조인 큐가 활용

---

## BFS(breadth first search)

---

- 그래프를 탐색하는 방법
  
  1. DFS 깊이 우선 탐색
     
     - 경로가 있는지 탐색 / 경로의 개수 탐색 / 최단 경로 탐색 (가능하지만 잘 안씀)
  
  2. BFS 너비 우선 탐색
     
     - 경로가 있는지 검색 / 최단 경로 탐색  

- 너비 우선 탐색은 탐색 시작점의 인접한 정점들을 먼저 모두 차례로 방문한 후에, 방문했던 정점을 시작점으로 하여 다시 인접한 정점들을 차례로 방문

- 선입선출 자료구조인 큐를 활용
  
  - 인접한 정점들에 대해 탐색한 후, 차례로 다시 너비 우선탐색을 진행해야하므로
