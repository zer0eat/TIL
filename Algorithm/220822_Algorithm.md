# Algorithm

---

## stack2

---

- 계산기1
  
  - 문자열로 된 계산식이 주어질 때, 스택을 이용하여 계산식의 값을 계산할 수 있다.
  
  - 문자열 수식 계산의 일반적인 방법
    
    1. 중위 표기법의 수식을 후위 표기법으로 변경한다(스택이용)
       
       - 수식의 각 연산자에 대해 우선순위에 따라 괄호를 사용하여 다시 표현
       
       - 각 연산자를 오른쪽 괄호 뒤로 이동
       
       - 괄호 제거
         
         ```
         ex) A*B-C/D
         1단계 ((A*B)-(C/D))
         2단계 ((AB)*(CD)/)-
         3단계   AB*CD/-
         ```
         
         1. 입력받은 중위 표기식에서 토큰을 읽는다
         
         2. 토큰이 피연산자이면 토큰을 출력한다
         
         3. 토큰이 연산자(괄호포함)일 때 토큰이 스택의 top에 저장되어 있는 연산자보다 우선순위가 높으면 스택에 push 
         
         4. 그렇지 않다면 스택 top의 연산자의 우선순위가 토큰의 우선수위보다 작을 때까지 스택에서 pop한 후 토큰의 연산자를 push
         
         5. 만약 top에 연산자가 없으면 push
         
         6. 토큰이 오른쪽 괄호면 스택 top에 왼쪽 괄호가 올때까지 스택에 pop 연산을 수행하고 pop한 연산자를 출력한다 왼쪽 괄호 만나면 pop만 하고 출력은 안함
         
         7. 중위 표기식에 더 읽을 것이 없다면 중지하고, 더 읽을 것이 있다면 1부터 반복
         
         8. 스택에 남아있는 연산자를 모두 pop하여 출력
            
            (스택 밖의 왼쪽 괄호는 우선순위가 가장 높고, 스택 안의 왼쪽 괄호는 우선순위가 가장 낮다)
    
    2. 후위 표기법의 수식을 스택을 이용하여 계산한다
       
       - 중위표기법(infix notation)
         
         - 연산자를 피연산자 가운데 표기 (a+b)
       
       - 후위표기법(postfix notation)
         
         - 연산자를 피연산자 뒤에 표기 (ab+)

---

- 계산기2
  
  - 후위표시법의 수식을 스택을 이용하여 계산
    
    1. 피연산자를 만나면 스택에 push
    
    2. 연산자를 만나면 필요한만큼의 피연산자를 스택에서 pop하여 연산하고 연산결과를 스택에 push
    
    3. 수식이 끝나면 마지막으로 스택을 pop하여 출력

---

- 백트래킹(backtracking)
  
  - 해를 찾는 도중 막히면 되돌아가서 다시 해를 찾는 기법
  
  - 최적화문제(optimization)와 결정문제(decision)를 해결할 수 있다
    
    - 결정문제
      
      - 문제의 조건을 만족하는 해가 존재하는지 여부를 답하는 문제
      1. 미로찾기
      
      2. n-queen
      
      3. map coloring
      
      4. 부분 집합의 합
  
  - 백트래킹과 깊이우선탐색의 차이
    
    - 어떤 노드에서 출발하는 경로가 해결책으로 이어질 것 같지 않으면 더 이상 그 경로를 따라가지 않음으로써 시도의 횟수를 줄임(prunning : 가지치기)
    
    - 깊이우선탐색이 모든 경로를 추적하는데 비해 백트래킹은 불필요한 경로를 조기 차단
    
    - 깊이우선탐색을 가하기에는 경우의 수가 너무나 많음
    
    - N! 가지의 경우의 수를 가진 문제에 대해 깊이 우선탐색을 가하면 처리 불가능
    
    - 백트래킹 알고리즘은 경우의 수가 줄어들지만 최악의 경우에는 여전히 지수함수 시간을 요하여 처리 불가능이 될 수 있음
  
  - 백트래킹 기법
    
    - 어떤 노드의 유망성을 점검한 후에 유망(promising)하지 않다고 결정되면 그 노드의 부모로 되돌아가(backtracking) 다음 자식 노드로 감
    
    - 어떤 노드를 방문하였을 때 그 노드를 포함한 경로가 해답이 될 수 없으면 그 노드는 유망하지 않다고 하며, 반대로 해답의 가능성이 있으면 유망
    
    - 가지치기(pruning) : 유명하지 않은 노드가 포함되는 경로는 더 이상 고려하지 않음
  
  - 알고리즘
    
    1. 상태 공간 트리의 깊이 우선 검색을 실시
    
    2. 각 노드가 유망한지 점검
    
    3. 만일 그 노드가 유망하지 않으면, 그 노드의 부모 노드로 돌아가서 검색 계속
    
    ```python
    def checknode(V): # node
        if promising(V):
            if there is a solution at V:
                write the solution
            else:
                for u in each child of V:
                    checknode(u)
    ```

---

- 부분집합 구하기
  
  - 어떤 집합의 공집합과 자기자신을 포함한 모든 부분집합을 powerset이라고 하며 구하고자 하는 어떤 집합의 원소 개수가 n일 경우 부분집합의 수는 2^n이다
  
  - 백트래킹 기법으로 powerset으로 구하기
    
    1. 앞에서 설명한 백트래킹 기법을 이용
    
    2. n개의 원소가 들어있는 집합의 2^n개의 부분집합을 만들 때는, true 또는 fasle값을 가지는 항목들로 구성된 n개의 배열을 만드는 방법을 이용
    
    3. 여기서 배열의 i번째 항목은 i번째 원소가 부분집합의 값인지 아닌지를 나타내는 값
  
  - powerset을 구하는 백트래킹 알고리즘
    
    ```python
    def backtrack(a, k, input):
        globla MAXCANDIATES
        c = [0] * MAXCANDIATES
    
        if k == input:
            process_solution(a,k) # 답이면 원하는 직업을 한    
        else:
            k += 1
            ncandidates = construct_candidates(a, k, input, c)
            for i in range(ncandidates):
                a[k] = c[i]
                backtrack(a, k, input)
    
    def construct_candidates(a, k, input, c):
        c[0] = True
        c[1] = False
        return
    
    MAXCANDIATES = 2
    NMAX = 4
    a = [0]* NMAX
    backtrack(a, 0 ,3)
    ```

---

- 순열 구하기
  
  - 순열 알고리즘
    
    ```python
    def backtrack(a, k, input):
        globla MAXCANDIATES
        c = [0] * MAXCANDIATES
    
        if k == input:
            for i in range(1, k + 1):
                print(a[i], end="")
            print    
        else:
            k += 1
            ncandidates = construct_candidates(a, k, input, c)
            for i in range(ncandidates):
                a[k] = c[i]
                backtrack(a, k, input)
    
    def construct_candidates(a, k, input, c):
        in_perm = [False] * NMAX
        
        for i in range(1, k):
            in+pern[a[i]] = True
    
        ncandidates = 0
        for i in range(1, input + 1):
            if in_perm[i] == False:
                c[ncandidates] = i
                ncandidates += 1
        return ncandidates
    ```

---

- 분할정복 알고리즘
  
  - 유래 
    
    - 1805/12/2 아우스터리츠 전투에서 나폴레옹이사용한 전략
    
    - 전력이 우세한 연합군을 공격하기 위해 나폴레옹은 연합군의 중앙부로 쳐들어가 연합군을 둘로 나눔
    
    - 둘로 나눈 연합군을 부분 격파
  
  - 설계 전략
    
    - 분할(divide)
      
      - 해결할 문제를 여러개의 작은 부분으로 나눈다
    
    - 정복(conquer)
      
      - 나눈 작은 문제를 각각 해결한다
    
    - 통합(combine)
      
      - (필요하다면) 해결된 해답을 모은다

---

- 퀵정렬
  
  - 주어진 배열을 두개로 분할하고 각각을 정렬
  
  - 합병정렬과 다른점
    
    - 합병정렬은 그냥 두 부분으로 나누는 반면 퀵정렬은 분할할 때 기준 아이템(pivot item) 중심으로 이보다 작은 것은 왼편, 큰것은 오른편에 위치
    
    - 각 부분 정렬이 끝난 후 합병정렬은 '합병'이란 후처리 작업이 필요하나 퀵정렬은 필요하지 않음
  
  - 알고리즘
    
    ```python
    def quicksort(a, begin, end):
        if begin < end:
            p = partition(a, begin, end)
            quicksort(a, begint, p-1)
            quicksort(a, p+1, end)
    -----------------------------------------------------------------
    
    def partition(a, begin, end): 
        pivot = (begin + end) // 2
        L = begin
        R = end
        while L < R:
            while(L<R and a[L] < a[pivot]):
                L += 1
            while(L<R and a[R] > a[pivot]):
                R -= 1
            if L == pivot : 
                pivot = R
                a[L], a[R] = a[R], a[L]
        a[pivot], a[R] = a[R], a[pivot]
        return R
    ```
  
  - 퀵 정렬의 최악 시간복잡도는 O(n^2)이지만 평균 복잡도는 nlogn이라 평균적으로는 가장 빠르다
