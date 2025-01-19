# 주간 내용정리

## 1월
<details>
  <summary><h3>2주차</h3></summary>

  <details>
    <summary>CLI(Command LIne Interface)</summary>
    
    <h4>CLI&GUI</h4>
    
    - CLI: <strong>명령어</strong>를 통해 사용자와 컴퓨터가 상호 작용하는 방식 <br>=> CLI에서 가장 중요한 것은 <strong>내가 어디 있는지(경로)</strong> 아는 것 
    - GUI: <strong>그래픽</strong>을 통해 사용자와 컴퓨터가 상호 작용하는 방식

    CLI 사용하는 이유
    - 효율성
        - 키보드만으로 모든 작업을 수행 가능
        - 메모리와 CPU 사용량이 적어 저사양 시스템에서도 <strong>효율적</strong>
    - 정밀한 제어
        - 특정 프로그램이나 시스템의 세부 설정을 보다 정밀하게 제어 가능
    - 표준성
        - CLI 명령어는 대부분의 Unix 운영체제 기반 시스템에서 <strong>동일하게 작동</strong>하여 여러 환경에 적용 가능
  </details>

  <details>
    <summary>Git</summary>
    
    <h4>Git 개념</h4>
    
    - git: 분산 버전 관리
        - 버전 관리란 변화를 **기록하고 추적**하는 것
        - 중앙 집중식과 다르게 분산식을 사용하여 버전을 여러 복제된 저장소에 저장 및 관리
            - 중앙 서버에 의존하지 않고 동시에 다양한 작업을 수행하며 작업 충동을 줄이고 생산성 향상
            - 백업과 복구가 용이
            - 인터넷에 연결되지 않아도 로컬 저장소에 기록하고 중앙 서버와 동기화 가능
        - git의 역할
            - 히스토리를 관리
            - 개발 과정 파악
            - 이전 버전과 변경 사항 비교 => 코드의 <strong>변경 이력</strong>을 기록하고 <strong>협업</strong>을 원활하게 하는 도구
        - git의 역할
            - Working Directory: 실제 작업 중인 파일들이 위치하는 영역
            - Staging Area: 개념적인 영역으로 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 영역 
            - Repository: 버전 이역과 파일들이 영구적으로 저장되는 영역으로 모든 버전과 변경 이력이 기록, 버젼 = commit
    
    <h4>Git bash 명령어</h4>

    - CLI에서 '.'(점): '.'은 현재 디렉토리, '..'는 현재의 상위 디렉토리(부모 폴더)를 의미
    - touch: 파일 생성
    - mkdir: 새 디렉토리 생성
    - ls: 현재 작업 중인 디렉토리 내부의 폴더/파일 목록을 출력
    - cd: 현재 작업 중인 디렉토리를 변경 (위치 이동)
    - start: 폴더/파일 열기
    - rm: 파일 삭제 (디렉토리 삭제는 -r옵션을 추가 사용)
        - rm dir -r, rm -r dir 상관 X
    - git init: 로컬 저장소 설정(초기화) => git의 버전 관리를 시작할 디렉토리에서 진행
    - git add: 변경사항이 있는 파일을 staging area에 추가
    
  </details>

  <details>
    <summary>Chat GPT&API</summary>
    
    - cd
  </details>
  
</details>
