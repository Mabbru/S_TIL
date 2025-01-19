# 주간 내용정리

## 1월
<details>
  <summary><h2>2주차</h2></summary>

  <details>
    <summary>CLI(Command LIne Interface)</summary>
    
    CLI&GUI
    
    - CLI: 명령어를 통해 사용자와 컴퓨터가 상호 작용하는 방식 
    => CLI에서 가장 중요한 것은 내가 어디 있는지(경로) 아는 것 
    - GUI: 그래픽을 통해 사용자와 컴퓨터가 상호 작용하는 방식

    CLI 사용하는 이유
    - 효율성
        - 키보드만으로 모든 작업을 수행 가능
        - 메모리와 CPU 사용량이 적어 저사양 시스템에서도 효율적
    - 정밀한 제어
        - 특정 프로그램이나 시스템의 세부 설정을 보다 정밀하게 제어 가능
    - 표준성
        - CLI 명령어는 대부분의 Unix 운영체제 기반 시스템에서 동일하게 작동하여 여러 환경에 적용 가능
  </details>

  <details>
    <summary>Git</summary>
    
    Git 개념
    
    - git: 분산 버전 관리
        - 버전 관리란 변화를 **기록하고 추적**하는 것
        - 중앙 집중식과 다르게 분산식을 사용하여 버전을 여러 복제된 저장소에 저장 및 관리
            - 중앙 서버에 의존하지 않고 동시에 다양한 작업을 수행하며 작업 충동을 줄이고 생산성 향상
            - 백업과 복구가 용이
            - 인터넷에 연결되지 않아도 로컬 저장소에 기록하고 중앙 서버와 동기화 가능
        - git의 역할
            - 히스토리를 관리
            - 개발 과정 파악
            - 이전 버전과 변경 사항 비교 => 코드의 변경 이력을 기록하고 협업을 원활하게 하는 도구
        - git의 역할
            - Working Directory: 실제 작업 중인 파일들이 위치하는 영역
            - Staging Area: 개념적인 영역으로 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 영역 
            - Repository: 버전 이역과 파일들이 영구적으로 저장되는 영역으로 모든 버전과 변경 이력이 기록, 버젼 = commit
    
    Git bash 명령어

    - CLI에서 '.'(점): '.'은 현재 디렉토리, '..'는 현재의 상위 디렉토리(부모 폴더)를 의미
    - touch: 파일 생성
    - mkdir: 새 디렉토리 생성
    - ls: 현재 작업 중인 디렉토리 내부의 폴더/파일 목록을 출력
    - cd: 현재 작업 중인 디렉토리를 변경 (위치 이동)
    - start: 폴더/파일 열기
    - rm: 파일 삭제 (디렉토리 삭제는 -r옵션을 추가 사용)
        - rm dir -r, rm -r dir 상관 X
    - git init: 로컬 저장소 설정(초기화) => git의 버전 관리를 시작할 디렉토리에서 진행
        - git 로컬 저장소 내에 또 다른 git 로컬 저장소를 만들지 말 것
    - git add: 변경사항이 있는 파일을 staging area에 추가
    - git commit: staging area에 있는 파일들을 저장소에 기록 => 해당 시점의 버전을 생성, 변경 이력을 남김
        - -m: 메세지 설정
        - --amend: commit 메시지 수정 => Vim 에디터에서 수정
    - git config --global user.email "메일 주소" or user.name "유저네임": commit 작성자 정보 설정
        - git config --global -l: 설정 정보 보기
    - git status: 현재 로컬 저장소의 파일 상태 보기
    - git log: commit hisorty 보기
        - git log --oneline: 한 줄로 보기
    - git remote add origin remote_repo_url: 로컬 저장소에 원격 저장소 추가 
        - git remote -v: 현재 로컬 저장소에 등록된 원격 저장소 목록
        - git remote rm 원격 저장소 이름: 로컬 저장소에 등록된 원격 저장소 삭
    - git push origin master: 원격 저장소에 commit 목록을 업로드 => commit이 올라가므로 commit 이력이 없으면 push X
    - git pull origin master: 원격 저장소의 변경사항만을 받아옴 (업데이트)
    - git clone origin master: 원격 저장소 전체를 복제 (다운로드)
    - gitignore: Git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는데 사용되는 텍스트 파일
    - git revert <commit id>: 특정 commit을 없었던 일로 만드는 작업 (없앴다는 로그는 남음)
        - git revert 79ch 와 같이 사용
        - 공백이나 '..'을 사용해 한 번에 실행 취소 가능 
    - git reset [옵션] <commit id>: 특정 commit으로 되돌아가는 작업 => 삭제되는 commit들의 기록을 어떤 영역에 남겨둘 지 옵션 활용 가
        - git reset --soft <commit id>: staging area에 남김
        - git reset --mixed <commit id>: working directory에 남김 (기본 옵션 값)
        - git reset --hard <commit id>: 기록을 남기지 않음
    - git restore: Working Directory에서 파일을 수정한 뒤, 파일의 수정 사항을 취소하고, 원래 모습대로 되돌리는 작업
    - git rm --cached: Staging Area에서 Working Directory로 되돌리기 (git 저장소에 "commit이 없는 경우")
    - git restore --staged: Staging Area에서 Working Directory로 되돌리기 (git 저장소에 "commit이 있는 경우")
  </details>

  <details>
    <summary>Chat GPT&API</summary>
    
    - ChatGPT (Generative / Pre-trained / Transformer): 생성 모델 / 사전 훈련 / 트랜스포머 AI 모델 
    => GPT 모델을 기반으로 한 대화형 AI
    - API (비가시 영역의 수 많은 통신 종류 중 하나): 두 소프트웨어 (또는 시스템)가 서로 통신할 수 있게 하는 메커니즘
        - API Key: API에게 요청을 보내는 애플리케이션을 구별하기 위한 고유한 식별 문자
            - 보안 강화와 데이터 관리 측면에서 필요성 有 => 따라서 노출되면 안돼며 정기 갱신이 필요
    
  </details>
  
</details>
