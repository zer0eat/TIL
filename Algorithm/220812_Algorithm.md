# Algorithm

---

## 문자열(string)

- 컴퓨터에서 문자표현
  
  - 비트로 만들어진 코드체계를 사용하여 문자를 저장
  
  - 표준안 
    
    - 미국 ASCII(American Standard Code for Infomation Interchange) 문자 인코딩 표준이 제정
  
  - ASCII 
    
    - 7bit 인코딩 / 128문자 : 33개의 출력 불가능한 제어 문자 / 공백 / 95개의 출력가능한 문자로 구성
  
  - 확장 아스키
    
    - 악센트 도형 특수문자 특수기호 등 부가적인 문자 128개 추가하는 부호
    
    - 8bit를 모두 사용하여 추가적인 문자 표현
    
    - 표준아스키와는 교환 불가 (세계적 통용되는 방법이 아니라 올바른 해독 필요)
  
  - 다국어 처리를 위한 표준 = 유니코드
    
    - 유니코드 인코딩
      
      - charater set 으로 분류
        
        - ucs(universal character set)-2 / usc-4
        
        - 유니코드를 저장하는 변수의 크기 정의
        
        - 바이트 순서에 대해 표준화 실패
          
          - 파일 인식 시 usc-2/usc-4인지 인식하고 각 경우를 구분해서 구현해야함
          
          - 적당한 외부 인코딩이 필요
    
    - endian : 
      
      - big endian: byte order ABCD  / little endian : byte order DCBA
    
    - UTF : unicode transformation format
      
      - utf-32(in unix): MIN: 32bit MAX:32bit(4byte*1)
      
      - utf-8(in web) : MIN: 8bit MAX:32bit(1byte*4)
      
      - utf-16(in window, java): MIN:16bit MAX:32bit(2byte*2)
    
    - python 인코딩
      
      - 2.x 버전은 아스키코드가 기본이라 -\*-coding:utf-8-*- 명시필요
      
      - 3.x 버전은 유니코드utf-8이 기본이라 생략가능
      
      - 다른 인코딩 방식 처리 시 첫 줄에 인코딩 방식을 지정
    
    - 2진수 : 1bit = 2^0 / 1byte = 2^8
    
    - 16진수 

---

- 문자열
  
  - 분류
    
    - 문자열(string)
      
      - fixed length
      
      - variable length
        
        - length controlled : java 언어의 문자열
        
        - delimited : c언어 문자열
  
  - string 클래스에는 기본적인 객체 메타 데이터 외에도 hash count(문자열의 길이) offset(문자열 데이터 시작점)  value(실제 문자열 배열에 대한 참조) 등이 포함 되어있다.
  
  - python에서의 문자열 처리
    
    - char타입이 없음
    
    - 텍스트 데이터의 취급방법의 통일
    
    - 문자열 기호
      
      - '홑따옴표/"쌍따옴표/'''홑따옴표3개/"""쌍따옴표3개
      
      - 연결(concatenation)
        
        - 문자열 + 문자열 : 이어붙어줌
      
      - 반복
        
        - 문자열 * 수 : 수만큼 문자열 반복
    
    - 문자열은 시퀀스 자료형으로 분류되고, 시퀀스 자료형에서 사용할 수 있는 인덱싱, 슬라이싱 연산들을 사용
    
    - 문자열 클래스 메소드
      
      - replace() / split() / isalpha() / find()
    
    - 문자열은 튜플과 같이 요소값을 변경할 수 없음(immutable)
  
  - 문자열 뒤집기
    
    - 자기 문자열 뒤집기
      
      -  swap을 위한 임신 변수가 필요하고 문자열 길이의 반만을 수행
      
      - 빈 문자열을 만들어 뒤에서 부터 읽어서 타겟에 쓰는 방법
    
    ```python
    # 방법 1 _ 파이썬만 가능
    s = 'Reverse this strings'
    print(s[::-1])
    
    # 방법 2 _ 다른 언어에서도 가능
    a = list(s)
    a.reverse()
    a = ''.join(a)
    print(a)
    
    # 방법 3 _ for문 이용
    ans = ''
    for char in s:
        ans = char + ans
    print(ans)
    
    # 방법 4 _ for문 이용
    ans2 = ''
    for idx in range(len(s)-1,-1,-1):
        ans2 += s[idx]
    print(ans2)
    ```
  
  - 문자열 정수로 변환하기
    
    ```python
    # int()와 같은 atoi()함수 만들기
    def atoi(s):
        i = 0
        for x in s:
            i = i*10 + ord(x) - ord('0')
        return i
    
    # str()와 같은 itoa()함수 만들기
    def itoa(num):
        ans = ''
        while num:
            num, reminder = divmod(num, 10)
            # num, reminder = num//10, num%10
            ans = chr(reminder + ord('0')) + ans
        return ans
    ```

---

- 패턴매칭
  
  - ## 고지식한 패턴 검색 알고리즘(**Brute force**)
    
    - 본문 문자열을 처음부터 끝까지 차례대로 순회하면서 패턴 내의 문자들을 일일이 비교하는 방식
    
    ```python
    # Brute force
    
    # 방법_1
    t = 'this is book'
    p = 'is'
    print(p in t) # True
    
    # 방법_2 <---- 반드시 이해 및 활
    def func1(t, p):
        for i in range(len(t) - len(p) + 1):
            for j in range(len(p)):
                if t[i + j] != p[j]:
                    break
            else:
                return i
        return -1
    print(func1(t, p)) # 2
    
    # 방법_3
    def func2(t, p):
        m = len(p)
        for a in range(len(t) - len(p) + 1):
            if t[a:a+m] == p:
                return a
        return -1
    print(func2(t, p)) # 2
    
    # 방법_4
    def func3(t, p):
        i = 0
        j = 0
        while j<len(p) and i<len(t):
            if t[i] != p[j]:
                i = i - j
                j = -1
            i = i + 1
            j = j + 1
        if j == len(p):
            return i - len(p)
        else:
            return -1
    print(func3(t, p)) # 2
    ```
  
  - 카프 -라빈 알고리즘
  
  - KMP 알고리즘
    
    - 불일치가 발생한 텍스트 스트링의 앞 부분에 어떤 문자가 있는지를 미리 알고 있으므로, 불일치가 발생한 앞 부분에 대하여 다시 비교하지 않고 매칭을 수행
    
    - 과정
      
      - 패턴에 대한 prefix list 작성
      
      - 비교하여 pattern 만큼 skip
    
    - 중계리스트
  
  - 보이어 - 무어 알고리즘
    
    - 오른쪽에서 왼쪽으로 비교
    
    - 대부분 소프트웨어에서 채택하고 있는 알고리즘
    
    - 패턴에 오른쪽 끝에 있는 문자가 불일치하고 이 문자가 패턴 내 존재하지 않는 경우, 이동거리는 패턴만큼이 된다.

- 문자열 암호화
  
  - 시저암호
    
    -  줄리어스 시저가 사용한 암화
    
    - 기원전 100년경 로마에서 사용
    
    - 일정한 수만큼 평행이동 시킴으로써 암호화를 행한다
  
  - 문자변환표
    
    - 단일치환암호 
    
    - 시저암호보다 훨씬 강력한 암호화 기법
    
    - 단일 치환 암호의 복호화
      
      - 복호화 하기 위해서는 모든 키의조합(key space)이 필요하다
      
      - 단일치환암호의 키의 총 개수는 : 26!
  
  - bit열의 암호화
    
    - 배타적 논리합(exclusive-or) 연산 사용
    
    - exclusive-or 
      
      - x or y가 둘다 1일 때 결과가 1이 아니라 0이 나온다
      
      - | origin(x) | key(y) | and | or  | exclusive-or(x-or) |
        |:---------:|:------:|:---:|:---:|:------------------:|
        | 0         | 0      | 0   | 0   | 0                  |
        | 0         | 1      | 0   | 1   | 1                  |
        | 1         | 0      | 0   | 1   | 1                  |
        | 1         | 1      | 1   | 1   | 0                  |

- 문자열 압축
  
  - 저장소의 크기를 줄이며 정확한 정보를 저장
  
  - run -length encoding 알고리즘
  
  - 같은 값이 몇 번 반복되는지를 나타냄으로써 압축
  
  - 이미지 파일 포맷 중 BMP  압축방법
  
  - 더 효율적인 방법은 허프만 코딩 알고리즘


