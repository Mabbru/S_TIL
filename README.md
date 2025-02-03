# MY TIL (속기)

## 1월
<details>
  <summary><h3>3주차</h3></summary>

  <details>
    <summary>CUL & GUL</summary>
    
    - CLI(Command Line Interface): **명령어**를 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - GUL(Graphic User Interface): **그래픽**을 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - CLI를 사용해야 하는 가장 큰 이유는 **메모리와 CPU 사용량이 적어** 효율적으로 동작하기 때문이다. ⇒ 컴퓨터가 **개인화**가 되면서 혁신이 일어났다. 개발자라면 시스템을 구축하여 제공할 수 있어야 하며, 이를 위해서 효율성이 필요하다.
  </details>

  <details>
    <summary>CUL 中 (“.”, “..”, touch, mkdir, ls, cd, start, rm (-r), pwd)</summary>
    
    - ‘.’(점)의 역할은 위치를 알려주는 역할이다. 하나는 현재 디렉토리, 둘은 현재의 상위 디렉토리이다.
    - touch: 파일 생성 / mkdir: 새 디렉토리 생성 / ls: 현재 작업 중인 디렉토리 내부의 폴더 혹은 파일 목록을 출력
      1. touch text.txt
      2. mkdir new_dir
      3. ls . or ls ..
    - cd: 현재 작업 중인 디렉토리를 변경(위치 이동) / start: 폴더 혹은 파일을 열기 / rm: 파일 삭제 (디렉토리 삭제는 -r 옵션을 추가 사용) / pwd: 현재 작업 공간 확인(print working dir)
      1. cd new_dir → cd .. ⇒ 제자리
      2. start text.txt
      3. rm text.txt or rm -r new_dir
    - CLI에서 가장 중요한 것: **내가 어디 있는지(경로)** 알아야 한다.
    - **절대 경로:** Root 디렉토리부터 목적 지점까지 거치는 모든 경로를 전부 작성한 것 / **상대 경로**: 현재 작업하고 있는 디렉토리를 기준으로 계산된 상대적 위치를 작성한 것
      1. 윈도우 바탕 화면의 절대 경로 예시: C:/Users/ssafy/Desktop
      2. 만약 현재 작업하는 있는 디렉토리가 C:/Users 일 때, 윈도우 바탕 화면으로의 상대 경로는 ssafy/Desktop 이다.
      3. 나를 중심 혹은 컴퓨터를 중심으로 이동할 것인가를 생각하면 된다. 일반적으로 상대 경로를 통해 전달하는데 이는 절대 경로의 경우 보안에 위험이 있을 수 있기 때문이다.
  </details>

  <details>
    <summary>Git이란?</summary>
    
    - Google Docs를 활용한 버전 관리 예시와 유사하다. ⇒ ‘누가 언제 어떻게 왜’ 를 기록하면서 다음 버전은 이전 버전에 대해서 **변경점만을 저장**하고 있다.
    - 기존과 다르게 이전 버전에 대해서 추가사항이 어떤 것이 있는지 확인할 수 있으며 최종사항은 따로 저장
    - **분산** 버전 관리 시스템
      - 중앙 집중식: 버전은 중앙 서버에 저장되고 중앙 서버에서 파일을 가져와 다시 중앙에 업로드
        - 매니저 입장에서는 개발자 관리에 용이
      - 분산식: 버전을 여러 개의 복제된 저장소에 저장 및 관리
        - 중앙 서버의 장애나 손실에 대비하여 백업과 복구가 용이
        - 개발자들 간에 작업 충돌을 줄일 수 있고 개발 생산성을 향상
        - 인터넷에 연결되지 않은 환경에서도 작업 가능 ⇒ 변경 이력과 코드를 로컬 저장소에 기록하고, 나중에 중앙 서버 동기화
    - Git의 역할
      - 코드의 버전(히스토리)를 관리
      - 개발되어 온 과정 파악
      - 이전 버전과의 변경 사항 비교   ⇒ undoing과 연관지을 수 있음
    ⇒ 분산 버전 관리 시스템으로 코드의 ‘변경 이력’을 기록하고 ‘협업’을 도와주는 도구
  </details>

  <details>
    <summary>Git의 영역</summary>
    
    - **Working Directory(W.D)**: 실제 작업 중인 파일들이 위치하는 영역
    - **Staging Area (개념적으로만 존재)**: W.D에서 변경된 파일 중, 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 **중간 준비 영역**
    - **Repository**: **버전(commit)** 이력(history)과 파일들이 영구적으로 저장되는 영역으로 모든 **버전(commit)**과 변경 이력이 기록
      - commit(버전): 변경된 파일들을 저장하는 행위이며, 마치 사진을 찍듯이 기록한다 하여 ‘snapshot’ 이라고도 함
  </details>

  <details>
    <summary>Git의 동작</summary>
    
    - git init: 로컬 저장소 설정(초기화) → git의 버전 관리를 시작할 디렉토리에서 진행 ⇒ 현재 위치를 directory에서 working directory로 바꿈
    - git add: 변경사항이 있는 파일을 staging area에 추가
    - git commit: staging area에 있는 파일들을 저장소에 기록 → 해당 시점의 버전을 생성하고 변경 이력을 남기는 것
    - git status: staging area 상태 확인
    - git config —global [user.email](http://user.email) “메일 주소”, git config —global [user.name](http://user.email) “유저네임”
    - — global: 어디서든 입력 가능하며 이를 반복적으로 사용할 시 덮어쓰여짐
    - ls -a ⇒ ./../.git/sample ⇒ .git이 Repository이며 Version DB + settings, git_prac는 W.D
    - staging area에 한 번이라도 올라가지 않으면 git으로 관리되지 않는다. staging area란 commit할 파일들을 선별한 곳이라고 생각할 수 있다.
  </details>

  <details>
    <summary>git init 주의사항</summary>
    
    - git 로컬 저장소 내에 또 다른 git 로컬 저장소를 만들지 말 것
    - 즉, 이미 git 로컬 저장소인 디렉토리 내부 하단에서 git init 명령어를 다시 입력하지 말 것
    - git 저장소 안에 git 저장소가 있을 경우 가장 바깥쪽의 git 저장소가 안쪽의 git 저장소의 변경 사항을 추적할 수 없기 때문
    - 때문에 boot나 바탕화면이 아닌 C 드라이브 같은 곳에 설정할 것
    - git commit —amend ⇒ 이전 commit 수정
  </details>

  <details>
    <summary>Vim</summary>
    
    - i: insert mode, 완료한 뒤 :q, :q!, :wq, :wq! 와 같은 명령어로 종료 가능하다.
  </details>

  <details>
    <summary>CUL 中 (remote, push, pull, clone, gitignore)</summary>
    
    - remote: git remote add (명령어) | origin(별칭) | URL(원격 저장소)
    - push: git push (명령어) | origin(별칭) | master (branch 이름)
    - commit 이력이 없다면 push 할 수 없다. 이를 클라우드와 같이 파일을 저장만 하는 곳으로 이해하지 말 것
    - 로컬 → 원격
    - pull: git pull | URL(원격 저장소)
      - 원격 저장소에 있던 파일들을 기준으로 로컬 저장소 파일들을 업데이트 시킴
    - clone: git clone | URL(원격 저장소)
      - 원격 저장소에 있던 파일들을 로컬 저장소로 다운받음
    - gitignore: git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는 데 사용되는 텍스트 파일
      - touch .gitignore | [gitignore.io](http://gitignore.io) 사이트 참조
      - 한 번 staging area에 추가되는 순간 gitignore 효과는 사라짐. 따라서 처음 repo를 만들 때, gitignore를 포함하여 설계하는 것이 중요
  </details>
  
  <details>
    <summary>TIL</summary>
    
    - TIL(Today I Learn): 매일 내가 배운 것을 Markdown으로 정리해서 문서화하는 것
    - ‘문서화’ 의 중요성: 신입 개발자에게 요구되는 가장 중요한 덕목이며 이는 나 말고도 이를 보고 이어갈 다른 개발자 입장도 고려되어야 한다. ⇒ 꾸준히 스스로 학습해 성장할 수 있고 문서화를 통해 내 생각을 정리하고 팀에 공유할 수 있는 능력
    - 경로마다 readme 파일이 있을 수 있다.
  </details>

  <details>
    <summary>Revert&Reset&restore</summary>
    
    - commit -amend ⇒ 바로 직전 수정을 통한 재확인 및 검증
    - 과거로 되돌린다는 공통점은 있으나 Revert는 되돌렸다는 기록, history, commit을 남김, Reset은 기록 조차 없음
    - revert: 재설정, 단일 commit을 실행 취소, 프로젝트 기록에서 commit을 없었던 일로 처리 후 그 결과를 commit으로 추가. 이를 통해서 추적 가능하다.
    - git revert 정리
        - 변경 사항을 안전하게 실행 취소할 수 있도록 도와주는 순방향 실행 취소 작업
        - commit기록에서 commit을 삭제하거나 분리하는 대신 지정된 변경 사항을 반전시키는 새 commit을 생성
        - git에서 기록이 손실되는 것을 방지하며 기록의 무결성과 협업의 신뢰성 높임
    - git reset: 특정 commit으로 되돌아가는 작업, git reset [옵션 <commit id>
    - git reset 작동 원리: 되돌리기, 시계를 마치 과거로 돌리는 듯한 행위, 특정 commit 으로 되돌아 갔을 때, 되돌아간 commit 이후의 commit은 모두 삭제
        - —sort, —mixed. —hard: 삭제되는 commit들의 기록을 어떤 영역에 남겨둘 것인지 정하는 옵션.
            - soft: 삭제 commit을 staging area에 남김
    - git restore: 파일 내용 수정 전으로 되돌리기
        - staging area에 올라간 파일을 Unstage 하기
            - git rm —cached
            - git restore —staged
  </details>

  <details>
    <summary>Chat GPT</summary>
    
    - Chat Gpt가 가능하게 한 다양한 이유 중 하나는 Web Service라는 것이다. 이를 통해서 기술(Soft service) + API(소통) ⇒ GPT를 기반으로 프로젝트 등을 지향하는 것이 생산적
  </details>

  <details>
    <summary>API</summary>
    
    - Interface
        - 서로 다른 두 개의 시스템이 정보를 교환할 때, 그 사이에 존재하는 접점
        - 사용자가 기기를 쉽게 동작 시키거나, 기계와 기계가 통신할 때 필요한 ‘약속된 방’
    - UI
    - 눈에 보이지 않는 영역의 통신으로 기계와 기계, 시스템과 시스템 사이의 소통이 수 없이 많이 이루어진다.
        - 클라이언트 - 서버 구조 ⇒ Client(requests)→ ← (responses) Server
            - 클라이언트: 서비스 요청
            - 서버: 요청을 받아 처리하고, 결과를 응답
            - 사용자가 브라우저로 특정 주소(URL)를 요청 →  ←서버가 해당 페이지, 데이터 등을 보내줌
    - API: 두 소프트웨어가 서로 통신할 수 있게 하는 메커니즘 → **약속된 방식**의 인터페이스로 **특정 규칙**에 따라 데이터를 요청하고 응답하는 규칙을 제공
        - API KEY:
            - 보안 강화: 무단 접근을 막고, 승인된 사용자만 요청 가능
            - 데이터 관리: 호출 횟수, 사용량 모니터링, 일정량 이상 사용 시 과금 정책 적용 가
            - 공개된 곳에 노출되면 안되며 KEY를 안전하게 저장하는 방법들을 고려해야 한다.
    - Application: **특정 기능**을 수행하는 모든 소프트웨어 → 웹 모바일 데스크톱 앱 등, 우리가 만든 서비스나 프로그램도 모두 앱의 일종

⇒(요약) API는 클라이언트와 서버 사이의 invisiable interface. API Key는 이 통신을 더욱 안전하게 만들기 위한 핵심 수단
  </details>

</details>

<details>
<summary><h3>4주차</h3></summary>

  <details>
    <summary>프로그래밍</summary>
    - 명령어들의 집합으로 핵심은 새 연산을 정의하고 조합해 유용한 작업을 수행하는 것 ⇒ 문제를 해결하는 매우 강력한 방법
  </details>

  <details>
    <summary>Python 개념</summary>
    - Python을 배우는 이유
      - 쉽고 간결한 문법
      - 파이썬 커뮤니티의 지원
      - 광범위한 응용 분야
        - 웹 개발, 데이터 분석, 인공지능, 자동화 인공지능 등에서 다양하게 활용
    - Python 알고리즘
      - 직관적인 문법
      - 강력한 표준 라이브러리
      - 빠른 프로토타이핑
    - 표현식
      - 값으로 평가될 수 있는 코드 조각
      - 표현식이 **평가**되어 값이 반환됨
      - 평가란 표현식을 실행하여 값을 얻는 과정 ⇒ 표현식을 순차적으로 평가하여 프로그램의 동작을 결정
    - 문장
      - 실행 가능한 동작을 기술하는 코드(조건문, 반복문, 함수 정의 등) → 문장은 보통 여러 개의 표현식을 포함
  </details>

  <details>
    <summary>Python 변수</summary>
    - Type(타입): 변수나 값이 가질 수 있는 데이터의 종류를 의미 → 어떤 종류의 데이터인지 어떻게 해석되고 처리되어야 하는 지를 정의
      - 타입은 2가지 요소로 이루어짐 → “값”과 “값에 적용할 수 있는 연산” ⇒ 데이터 타입에 맞는 연산을 위해 타입의 분류는 중요
    - 산술 연산자 / 연산자 우선순위 ⇒ 노션 필기보면서 숙지할 것
    - 변수: 값을 저장하기 위한 이름 ⇒ 값을 참조하기 위한 이
    - 변수 할당: 표현식을 통해 변수에 값을 저장 (오른쪽에서 왼쪽으로)
        - 할당문
            1. 할당 연산자(=) 오른쪽에 있는 표현식을 평가해서 값(메모리 주소)을 생성
            2. 값의 메모리 주소를 ‘=’ 왼쪽에 있는 변수에 저장
                1. 존재하지 않는 변수라면 → 새 변수를 생성 (할당)
                2. 기존에 존재했던 변수라면 → 기존 변수를 재사용해서 변수에 들어 있는 메모리 주소를 변경 (재할)
    - 변수 값 그리고 메모리
        - 거리에 집 주소가 있듯이 메모리의 모든 위치에는 그 위치를 고유하게 식별하는 메모리 주소가 존재
            - 메모리 ⇒ 36.5 (타입: float, 주소: 491734)
        - 객체 (Object)
            - 타입을 갖는 메모리 주소 내 값
            - “값이 들어있는 상자”
        - 변수
            - 그 변수가 참조하는 객체의 메모리 주소를 가짐
            - 변수는 값 36.5를 참조
  </details>

  <details>
    <summary>Python Type</summary>
    - Data Types: 값의 종류와 그 값에 적용 가능한 연산과 동작을 결정하는 속
    - 데이터 타입
      - Numeric Type
        - int, float, complex
      - Sequence Types
        - list, tuple, range
      - Text Sequence Type
        - str
      - Non - Sequence Types
        - set, dict
      - 기타
        - Boolean, None, Functions
    - 데이터 타입이 필요한 이유
      - 값들을 구분하고, 어떻게 다뤄야 하는지를 알 수 있음
      - 요리 재료마다 특정한 도구가 필요하듯이 각 데이터 타입 값들도 각자에게 적합한 도구를 가짐
      - 타입을 명시적으로 지정하면 코드를 읽는 사람이 변수의 의도를 더 쉽게 이해할 수 있고, 잘못된 데이터 타입으로 인한 오류를 미리 예방
    - int(Integer): 정수 자료형
      - 정수를 표현하는 자료
      - a=10, b=0, c=-5
      - 진수
        - 2진수(binary): 0b10 → 2
        - 8진수 (octal): 0o30 → 24
        - 16진수 (hexadecimal): 0x10 → 16
     - float: 실수 자료형
       - 실수를 표현하는 자료형 ⇒ 프로그래밍 언어에 float는 실수에 대한 **근삿값**
          - 유한 정밀도: 한 숫자에 대해 저장하는 용량이 제한 (메모리 용량 문제)
            - 부동소수점 에러: 컴퓨터가 실수를 표현하는 방식으로 인해 발생하는 작은 오차 → 2진수로 변환하는 과정에서 발생하는 근사치 표현
            - 부동소수점 에러 해결책: 대표적으로 decimal 모듈을 ㅏ용해 부동소수점 연산의 정확성을 보장하는 방법
     - Sequence Types: 여러 개의 값들을 순서대로 나열하여 저장하는 자료형
      - str, list, tuple, range
      - 순서(Sequence)
        - 값들이 순서대로 저장 (정렬 X)
      - 인덱싱(Indexing)
        - 각 값에 고유한 인덱스(번호)를 가지고 있으며, 인덱스를 사용하여 특정 위치의 값을 선택하거나 수정할 수 있음
      - 슬라이싱(Slicing)
        - 인덱스 범위를 조절해 부분적인 값을 추출할 수 있음
      - 길이(Length)
        - len()함수를 사용하여 저장된 값의 개수(길이)를 구할 수 있음
      - 반복(Iteration)
        - 반복문을 사용하여 저장된 값들을 반복적으로 처리할 수 있다.
      - str: 문자들의 순서가 있는 변경 불가능한 시퀀스 자료
        - 작은 따옴표나 큰 따옴표로 감싸서 표현
        - 중첩 따옴표, \n, \t, \\, \’, \”
      - String Interpolation: 문자열 내에 변수나 표현식을 삽입하는 방법
        - f-string
        - 인덱스 0,1,2,3,4 = -5, -4, -3, -2, -1
        - 슬라이싱 및 리버스([::-1])
  </details>

  <details>
    <summary>CUL & GUL</summary>
    
    - CLI(Command Line Interface): **명령어**를 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - GUL(Graphic User Interface): **그래픽**을 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - CLI를 사용해야 하는 가장 큰 이유는 **메모리와 CPU 사용량이 적어** 효율적으로 동작하기 때문이다. ⇒ 컴퓨터가 **개인화**가 되면서 혁신이 일어났다. 개발자라면 시스템을 구축하여 제공할 수 있어야 하며, 이를 위해서 효율성이 필요하다.
  </details>

  <details>
    <summary>Data type</summary>
    
    - review
      - 부동 소수점
      - 지수표현: 3.14e+-4
      - Sequence Types: 여러 개의 값들을 순서대로 나열하여 저장하는 자료형
      - str: 문자들의 순서가 있는 변경 불가능한 시퀀스 자료형
      - String Interpolation: 문자열 내에 변수나 표현식을 삽입하는 방법
        - f - string
    - Sequence Types
      - list: 여러 개의 값을 순서대로 저장하는 변경 가능한 시퀀스 자료형
        - 리스트 표현
          - 0개 이상의 객체를 포함하여 데이터 목록을 저장
          - 대괄호 [] 로 표기
          - 데이터는 어떤 자료형 도 저장할 수 있음
        - 인덱싱, 슬라이싱, 길이 가능
        - 리스트 요소를 바꾼다고 주소가 바뀌는 것은 아니다.
      - tuple: 여러 개의 값을 순서대로 저장하는 변경 불가능한 시퀀스 자료형
        - 튜플 표현
          - 0개 이상의 객체를 포함하여 데이터 목록을 저장
          - 소괄호 () 표기
          - 데이터는 어떤 자료형도 저장할 수 있음
          - 단일 요소 튜플을 만들 대는 반드시 후행 쉼표를 사용해야 함 -> (1,)
        - 인덱싱, 슬라이싱, 길이 가능
        - 튜플 쓰임
          - 튜플의 불변 특성을 사용하여 내부 동작과 안전한 데이터 전달에 사용
            - 다중 할당, 값 교환, 그룹화 등에 쓰임
      - range: 연속된 정수 시퀀스를 생성하는 변경 불가능한 자료형
        - range 기본 구문: range(시작 값, 끝 값, 증가 값,) -> 정수 시퀀스 생성
          - 주로 반복문과 함께 사용
    - Non - sequence Types
      - dict: key - value 쌍으로 이루어진 순서와 중복이 없는 변경 가능한 자료형
        - key는 변경 불가능한 자료형만 사용 가능
        - value는 모든 자료형 사용 가능
        - 중괄호 {} 표기
        - list의 한계점을 보완하는 타입
        - 중복이 될 수 없다는 것은 key 기준
      - set: 순서와 중복이 없는 변경 가능한 자료형(집합 자료형)
      
  </details>

  <details>
    <summary>연산자</summary>
    
    - 복합 연산자
    - 비교 연산자
      - <, <=, >, >=, ==, != ,is, is not 이 있다
      - == ↔ is
      - ==
        - 값을 비교
        - 동등성
        - 1 == True ⇒ True로 나옴
      - is
        - 객체 자체가 같은지를 비교
        - 식별성
        - 두 변수가 동일한 메모리 주소를 가리키고 있을 때만 Ture
      - is 대신 ==를 사용하는 이유
        - is는 객체의 식별성을 비교하므로, 숫자나 문자열 같은 값 자체를 비교하려는 상황에서는 적절하지 않음
        - is연산자를 이용하면 코드 상에서 의도치 않게 False가 나오거나 파이썬 버전에 따라 내부 구현 차이 때문에 기대하는 결과가 달라질 수 있음
      - is 연산자 사용하는 때
        - None을 비교를 비교 할 때
        - 싱글턴 객체를 비교 할 때 → True, False
      - 정리
        - 값 비교에는 ==, 객체 비교에는 is
    - 논리 연산자
    - 멤버십 연산자
    - 시퀀스형 연산
  </details>

  <details>
    <summary>실습 중 공부</summary>
    
    -  
  </details>
  
  <details>
    <summary>함수</summary>
    
    - functions: 특정 작업을 수행하기 위한 **재사용** 가능한 코드 묶음
      - 함수를 사용하는 이유
        - 두 수의 합을 구하는 함수를 정의하고 사용함으로써 코드의 중복을 방지
        - 재사용성이 높아지고, 코드의 가독성과 유지 보수성 향상
      - return 이후의 문장들은 무시된다. return이 없다면 None 반환
      - 프린트 함수는 반환 값이 없다.
  </details>
  
  <details>
    <summary>매개변수와 인자자</summary>
    
    - 매개변수(parameter): 함수를 정의할 때, 함수가 받을 값을 나타내는 변수
    - 인자(argument): 함수를 호출할 때, 실제로 전달되는 값
    - 다양한 인자 종류
      - 위치 인자
        - 함수 호출 시 인자의 위치에 따라 전달되는 인자
        - 위치인자는 함수 호출 시 반드시 값을 전달해야 함
      - 기본 인자 값
        - 함수 정의에서 매개변수에 기본 값을 할당하는 것
        - 함수 호출 시 인자를 전달하지 않으면, 기본값이 매개변수에 할당됨
      - 키워드 인자
        - 함수 호출 시 인자의 이름과 함께 값을 전달하는 인자
        - 매개변수와 인자를 일치시키지 않고, 특정 매개변수에 값을 할당할 수 있음
        - 인자의 순서는 중요하지 않으며, 인자의 이름을 명시하여 전달
        - 단, 호출 시 키워드 인자는 위치 인자 뒤에 위치해야 함
      - 임의의 인자 목록
        - 정해지지 않는 개수의 인자를 처리하는 인자
        - 함수 정의 시 매개변수 앞에  ‘*’ 를 붙여 사용
        - 여러 개의 인자를 tuple로 처리
      - 임의의 키워드 인자 목록
        - 정해지지 않은 개수의 키워드 인자를 처리하는 인자
        - 함수 정의 시 매개변수 앞에  ‘**’ 를 붙여 사용
        - 여러 개의 인자를 dictionary로 묶어 처리
      - 함수 인자 권장 작성순서
        - 워치 → 기본 → 가변 → 가변 키워드
        - 호출 시 인자를 전달하는 과정에서 혼란을 줄일 수 있도록 함
        - 단, 모든 상황에 적용되는 절대적인 규칙은 아니며 , 상황에 따라 유연하게 조정될 수 있음
  </details>
  
  <details>
    <summary>재귀 함수</summary>
    
    - 재귀 함수: 함수 내부에서 자기 자신을 호출하는 함수
      - 팩토리얼
      - 재귀 함수의 특징
        - 특정 알고리즘 식을 표현할 때 변수의 사용이 줄어들며, 코드의 가독성이 높아짐
        - 1개 이상의 base case(종료되는 상황)가 존재하고, 수렴하도록 작성  
  </details>
  
  <details>
    <summary>내장 함수</summary>
    
    - 파이썬이 기본적으로 제공하는 함수(별도의 import 없이 바로 사용 가능)
    - map
      - map(function(함수), iterable(반복이 가능한 객체)): 순회 가능한 데이터구조의 모든 요소에 함수를 적용하고 그 결과를 map object로 변환
    - zip
      - zip(*iterables): 임의의 iterable을 모아 튜플을 원소로 하는 zip object를 반환
      - 페어가 맞지 않을 경우는 test해 볼 것 -> 실행 안
  </details>
  
  <details>
    <summary>함수와 scope</summary>
    
    - 함수는 코드 내부에 local scope를 생성하며, 그 외의 공간인 global scope로 구분
      - scope
        - global scope: 코드 어디에서든 참조할 수 있는 공간
        - local scope : 함수가 만든 scope (함수 내부에서만 참조 가능)
      - variable
        - global variable: global scope에 정의된 변수
        - local variable: local scope에 정의된 변수
    - 변수 수명주기
      - built - in scope: 영원
      - global scope: 코드 내에 한정
      - local scope: 함수 내에 한정
    - 이름 검색 규칙
      - 함수 내에서 바깥 scope의 변수에 접근 가능하나 수정은 할 수 없음 
  </details>
  
  <details>
    <summary>함수 스타일 가이드</summary>
    
    - def 안에 여러 목적을 넣는 것이 아닌 단일 목적
  </details>
  
  <details>
    <summary>packing & unpacking</summary>
    
    - packing: 여러 개의 값을 하나의 변수에 묶어서 담는 것
    - unpacking: 패킹된 변수를 풀어서 개별 변수나 함수 인자로 전달
  </details>
  
  <details>
    <summary>람다</summary>
    
    - 일회성으로 함수를 만들어서 적용시키는 함수로 이해
  </details>
  
  <details>
    <summary>모듈</summary>
    
    - 개요
      - 개발자가 프로그램 전체를 모두 혼자 힘으로 작성하는 것은 드문 일
      - 다른 프로그래머가 이미 작성해 놓은 수천, 수백 만 줄의 코드를 활용하는 것은 생산성에서 매우 중요한 일이다.
    - 모듈 활용
      - 모듈: 한 파일로 묶인 변수와 함수의 모음으로 특정한 기능을 하는 코드가 작성된 파이썬 파일( .py)
        - 모듈 예시
          - math 내장 모듈: 파이썬이 미리 작성해 둔 수학 관련 변수와 함수가 작성된 묘듈 → import math 한 뒤 .pi, sqrt(4)
        - 모듈을 가져오는 방법
          - import 문 사용 → import math
          - from 절 사용 → from math import sqrt → 이 경우 사용 시 모듈 사용 X
        - 모듈 사용하기
          - ‘.(dot)’ 연산자
          - “점의 왼쪽 객체에서 점의 오른쪽 이름을 찾아라” 라는 의미
        - 모듈 주의사항
          - 서로 다른 모듈이 같은 이름의 함수를 제공할 경우 문제 발생
          - 마지막에 import된 이름으로 대체됨
        - ‘as’ 키워드
          - ‘as’ 키워드를 사용하여 별칭을 부여 가능
  </details>
  
  <details>
    <summary>파이썬 표준 라이브러리(PSL)</summary>
    
    - 파이썬 표준 라이브러리: 파이썬 언어와 함께 제공되는 다양한 모듈과 패키지의 모음
      - 패키지: 연관된 모듈들을 하나의 디렉토리에 모아 놓은 것
        - 패키지 사용하기
          - 아래와 같은 디렉토리 구조로 작성
          - 패키지 3개: my_package, math, statistics
          - 모듈 2개: my_math, tools
      - PSL 내부 패키지: 설치 없이 바로 import하여 사용
      - 외부 패키지: pip를 사용하여 설치 후 import 필요
        - pip: 외부 패키지들을 설치하도록 도와주는 파이썬의 패키지 관리 시스템
            - $ pip install [패키지 이름]
            - $ pip uninstall [패키지 이름]
            - $ pip install requests → 외부 API 서버로 요청
        - 패키지 사용 목적: 모듈들을 효율적으로 관리하고 재사용할 수 있도록 돕는 역할
  </details>
  
  <details>
    <summary>제어문</summary>
    
    - 제어문: 코드의 실행 흐름을 제어하는 데 사용되는 구문. 조건에 따라 코드 블록을 실행하거나 반복적으로 코드를 실행
    - 종류 다양
  </details>
  
  <details>
    <summary>조건문</summary>
    
    - 조건문: 주어진 조건식을 평가하여 해당 조건이 참인 경우에만 코드 블록을 실행하거나 건너뜀
        - if statement: if, elif, else
  </details>
  
  <details>
    <summary>반복문</summary>
    
    - 반복문: 주어진 코드 블록을 여러 번 반복해서 실행하는 구문
      - for statement: 특정 작업을 반복적으로 수행
        - for: 임의의 시퀀스의 항목들을 그 시퀀스에 들어있는 순서대로 반복
          - for [변수] in [반복 가능한 객체]:
             코드 블록
          - 반복 가능한 객체(iterable): 반복문에 순회할 수 있는 객체(시퀀스 객체 뿐만 아니라 dict, set 등도 포함)
          - for 문 작동원리
            - 리스트 내 첫 항목이 반복 변수에 할당되고 코드블록이 실행
            - 다음으로 반복 변수에 리스트의 2번째 항목이 할당되고 코드블록이 다시 실행
            - 마지막으로 반복 변수에 리스트의 마지막 요소가 할당되고 코드블록이 실행
      - while statement: 주어진 조건이 참인 동안 반복해서 실행
        - while: 주어진 조건식이 참인 동안 코드를 반복해서 실행 ⇒ 조건식이 거짓이 될 때까지 반복
          - while [조건식]:
                 코드 블록
          - while 문은 반드시 종료 조건이 필요
      - for: iterable의 요소를 하나씩 순회하며 반복. while: 주어진 조건식이 참인 동안 반복
      - 적절한 반복문 활용하기
        - for
          - 반복 횟수가 명확하게 정해져 있는 경우에 유용
          - 예를 들어, 리스트, 튜플, 문자열 등과 같은 시퀀스 형식의 데이터를 처리할 때
        - while
          - 반복 횟수가 불명확하거나 조건에 따라 반복을 종료해야 할 때 유용
          - 예를 들어, 사용자의 입력을 받아서 특정 조건이 충족될 때까지 반복하는 경우
      - 반복 제어: for문과 while은 매 반복마다 본문 내 모든 코드를 실행하지만 때때로 일부만 실행하는 것이 필요할 때가 있음
        - break
          - 반복 즉시 중지
        - continue
          - 다음 반복으로 건너뜀
        - pass
          - 아무런 동작도 수행하지 않고 넘어감
      - List comprehension: 간결하고 효율적인 리스트 생성 방법
        - 남용하면 안되며, 2차월 배열 생성 시 유용하게 사용
  </details>
  
  <details>
    <summary>참고</summary>
    
    - 모듈 내부 살펴보기
      - 내장 함수 help를 사용해 모듈에 무엇이 들어있는지 확인 가능
        - help(모듈)
    - enumerate
      - enumerate(iterable, strat = 0)
        - iterable 객체의 각 요소에 대해 인덱스와 함께 반환하는 내장함수 → 인덱스와 반복문을 같이 뽑음
          - for index, fruit in enumerate(fruits, 3):
                  print(index, fruit)  ⇒ 3 apple …. 튜플 형태이다.
  </details>
  
  <details>
    <summary>추가</summary>
    
    - list를 만드는 방법 → 반복문, list comprehension, map 총 3가지 방법
  </details>
  
  <details>
    <summary>데이터, 메서</summary>
    
    - 데이터 구조: 여러 데이터를 효과적으로 사용, 관리하기 위한 구조
      - 자료 구조: 컴퓨터 공학에서는 ‘자료 구조’ 라고 하며, 각 데이터의 효율적인 저장, 관리를 위한 구조를 나눠 놓은 것
      - 데이터 구조 활용: 문자열, 리스트, 딕셔너리 등 각 데이터 구조의 (메서드 == 함수)를 호출하여 다양한 기능을 활용하기
    - 메서드: 객체에 속한 함수 (종속) ⇒ 객체의 상태를 조작하거나 동작을 수행
      - 메서드는 클래스 내부에 정의되는 함수
      - 클래스는 파이썬에서 ‘타입을 표현하는 방법’ 이며 이미 은연중에 사용해왔음
      - 예를 들어 help 함수를 통해 str을 호출해보면 class였다는 것을 확인 가능
      - 메서드는 어딘가(클래스)에 속해 있는 함수이여, 각 데이터 타입별로 다양한 기능을 가진 메서드가 존재
      - 데이터 타입 객체.메서드
  </details>
  
  <details>
    <summary>문자열</summary>
    
    - 문자열 (이하 s로 취급)
      - s.find(x): x의 첫 번째 위치를 반환. 없으면 -1을 반환
      - s.index(x): x의 첫 번째 위치를 반환. 없으면 오류 발생 → 코드가 중단
    
    ##### is로 시작하는 함수의 반환 값은 Boolean
    
      - s.isupper(): 문자열 내의 모든 문자가 대문자인지 확인
      - s.islower(): 문자열 내의 모든 문자가 소문자인지 확인
      - s.isalpha(): 문자열 내의 모든 문자가 알파벳인지 확인, 단순 알파벳이 아닌 유니 코드 상 Letter (한국어도 포함)
    ———————————————————————————
      - s.replace(old, new[,count]): 바꿀 대상 글자를 새로운 글자로 바꿔서 반환 → new.text_new = text.replace(old, new, 1), 대괄호는 선택적 인자의 의미
      - s.strip([chars]): 공백이나 특정 문자를 제거
      - s.split(sep=None, maxsplit = -1): sep를 구분자 문자열로 사용하여 문자열에 있는 단어들의 리스트를 반환
      - ‘separator’.join(iterable): 구분자로 iterable의 문자열을 연결한 문자열을 반환
  </details>
  
  <details>
    <summary>리스트</summary>
    
    - 리스트 (이하 L로 취급)
      - L.append(x): 리스트 마지막에 항목 x를 추가
      - L.extend(m): iterable m의 모든 항목들을 리스트 끝에 추가 (+= 과 같은 기능)
      - L.pop(): 리스트 가장 오른쪽에 있는 항목([:-1])을 **반환** 후 제거
      - L.pop(i): 리스트 인덱스 i에 있는 항목을 반환 후 제거
      - L.insert(i, x): 리스트 인덱스 i에 항목 x를 삽입
      - L.remove(x): 리스트 가장 왼쪽에 있는 항목(첫 번째) x를 제거. 항목이 존재하지 않을 경우, valueError
      - L.clear(): 리스트의 모든 항목 삭제 → 빈 리스트로
    —————————————————————————
      - L.reverse(): 리스트의 순서를 역순으로 변경
      - L.sort(): 리스트를 정렬
      - L.index(x): 리스트에서 첫 번째로 일치하는 항목 x의 인덱스를 반환
      - L.count(x): 리스트에서 항목 x의 개수를 반환
  </details>

  <details>
    <summary>복사</summary>
    
    - 복사
      - mutable(가변) 객체: 생성 후 내용을 변경할 수 있는 객체
      - immutable(불변) 객체: 생성 후 내용을 변경할 수 없는 객체
      - 이러한 동작 방식의 이유
        - 성능 최적화
        - 메모리 효율성
      - 얕은 복사: 객체의 최상위 요소만 새로운 메모리에 복사하는 방법 내부에 중첩된 객체가 있다면 그 객체의 참조만 복사됨
      - 깊은 복사: 객체의 모든 수준의 요소를 새로운 메모리에 복사하는 방법. 중첩된 객체까지 모두 새로운 객체로 생성됨
  </details>
  
</details>



## 2월
<details>

  <summary><h3>2주차</h3></summary>
  
  <details>
    <summary>CUL & GUL</summary>
    
    - CLI(Command Line Interface): **명령어**를 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - GUL(Graphic User Interface): **그래픽**을 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - CLI를 사용해야 하는 가장 큰 이유는 **메모리와 CPU 사용량이 적어** 효율적으로 동작하기 때문이다. ⇒ 컴퓨터가 **개인화**가 되면서 혁신이 일어났다. 개발자라면 시스템을 구축하여 제공할 수 있어야 하며, 이를 위해서 효율성이 필요하다.
  </details>

  <summary><h3>3주차</h3></summary>
  
  <details>
    <summary>CUL & GUL</summary>
    
    - CLI(Command Line Interface): **명령어**를 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - GUL(Graphic User Interface): **그래픽**을 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - CLI를 사용해야 하는 가장 큰 이유는 **메모리와 CPU 사용량이 적어** 효율적으로 동작하기 때문이다. ⇒ 컴퓨터가 **개인화**가 되면서 혁신이 일어났다. 개발자라면 시스템을 구축하여 제공할 수 있어야 하며, 이를 위해서 효율성이 필요하다.
  </details>

  <summary><h3>4주차</h3></summary>
  
  <details>
    <summary>CUL & GUL</summary>
    
    - CLI(Command Line Interface): **명령어**를 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - GUL(Graphic User Interface): **그래픽**을 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - CLI를 사용해야 하는 가장 큰 이유는 **메모리와 CPU 사용량이 적어** 효율적으로 동작하기 때문이다. ⇒ 컴퓨터가 **개인화**가 되면서 혁신이 일어났다. 개발자라면 시스템을 구축하여 제공할 수 있어야 하며, 이를 위해서 효율성이 필요하다.
  </details>

  <summary><h3>5주차</h3></summary>
  
  <details>
    <summary>CUL & GUL</summary>
    
    - CLI(Command Line Interface): **명령어**를 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - GUL(Graphic User Interface): **그래픽**을 통해 사용자와 컴퓨터가 상호 작용하는 방식
    - CLI를 사용해야 하는 가장 큰 이유는 **메모리와 CPU 사용량이 적어** 효율적으로 동작하기 때문이다. ⇒ 컴퓨터가 **개인화**가 되면서 혁신이 일어났다. 개발자라면 시스템을 구축하여 제공할 수 있어야 하며, 이를 위해서 효율성이 필요하다.
  </details>
  
</details>
