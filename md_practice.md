[toc]



# 220715 마크다운 연습

구조를 잡는 것이 가장 중요!



##  헤딩(#)

`#`  개수에 따라 크기 조절 가능(1~6개)

`[toc]` : 전체 목차를 구조화하여 보여줌



## 강조표현

### Bold(** **)(단축키:ctrl + b)

`** **` : 사이에 단어를 넣으면 **볼드처리**

### Italic(* *)(단축키 : ctrl + i)

`* *` : 사이에 단어를 넣으면 *이탤릭체*

### 밑줄(~~ ~~)

`~~ ~~`: 사이에 단어를 넣으면 ~~밑줄~~





## Unorderd list(\- +스페이스바)

`\- + 스페이스바` 

- tab을 통해 한 depth 뒤로 이동

- shift + tap을 통해 한 depth 앞으로 이동

  - used

    - uded

    ​	



## Ordered list(숫자+.+스페이스)

`숫자+ . + 스페이스바`

1. 
2. 



## Escape sequence(\\\)

`\`  : 기호 그대로 사용할 때 앞에 이 기호를 붙이면 됨



## 백틱(`)

### Inlined codeblock

백틱으로 감싼다 `코드`



### Codeblock

````+스페이스바+(언어지정)`

``` python
This is pyhton
```



## 링크

- ctrl+클릭 해야 열림

- `[보여줄단어]+(url 주소)` -인터넷
  - (https:// 붙여줘야 인터넷이라는 것 알려줘야함)
  - [네이버](https://www.naver.com)

- `[보여줄단어]+(url 주소)`- 폴더내 파일 이동

  

## 이미지

- !+[대체문구(제목)]+(이미지의 위치(주소))
  - 공식문서 설정 반드시 하기
  - 상대주소를 사용하는 이유
    - md 파일을 다른데 업로드할 때, `.assets`해야 이미지도 정상적으로 올라감.

![아이유]()

![아이유](![img](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMjA2MjJfMzUg%2FMDAxNjU1ODY5MTY0Mzgw.EmJHOLZzk9omvLDHfo4-giGn_zNRsMkh-CqldA0l4B8g.cpI8_d8fC5upFWX7HYCbc5ZsSTEW9rAi1RbkpKlKOhgg.JPEG.futuresolution%2F1655869163938.jpg&type=sc960_832)



## 구분선(\---)

`---`

---



## 표 만들기(단축키 ctrl + t)

`|컬럼1|컬럼2|컬럼3|` 

- shift + \ = |

- 생성 후 크기 조절 가능-

| 컬럼1 | 컬럼2 | 컬럼3 |
| ----- | ----- | ----- |
|       |       |       |



## 인용문구

`>+스페이스바(토글)` `''+스페이스바(노션)`

> 인용문구 표시
>
> > 중첩가능



