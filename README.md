# MY TIL

## 1월
<details>
  <summary><h3>2주차</h3></summary>

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
  <summary><h3>2주차</h3></summary>

  <details>
    <summary>프로그래밍</summary>
    프로그래밍: 명령어들의 집합으로 핵심은 새 연산을 정의하고 조합해 유용한 작업을 수행하는 것
  ⇒ 문제를 해결하는 매우 강력한 방법
  </details>

  <details>
    <summary>Python 개념</summary>
  </details>

  <details>
    <summary>Python 변수</summary>
  </details>

  <details>
    <summary>Python Type</summary>
  </details>
  
</details>
