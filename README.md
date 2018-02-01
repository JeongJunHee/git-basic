## 대학생을 위한 Git 실전
### 버전 관리 시스템
#### 여러 VCS 중 Git의 특징

* 사실상 표준
* "분산'버전 관리 시스템
* 가볍고 빠르고 효과적
* 버전간 차이가 아니라 전체 사본(snapshot)을 보관
* 대부분의 작업을 로컬에서 할 수 있다
* 강력한 브랜치 기능

#### 중앙집중식 버전 관리 시스템

- 사진 넣기

#### 분산 버전 관리 시스템

- 사진 넣기

#### DVCS 장점

* 네트워크 단절 ok
* 로컬에 빠르고 가볍게 작업
* 혼자만의 실험 브랜치 진행
* 다른 사람과 공유전에 커밋을 정리정돈

#### 세 영역 (working directory, staging area, repository)

- 사진 넣기

#### 버전 확인

    $ git version
    git version 2.15.1

#### 기본 설정

    $ git config --global user.name "이름"
    $ git config --global user.email "이메일"
    $ git config --global color.ui true

* -global : 지금 로그온 한 계정에 전체 설정  
* -local : 현재 저장소 로컬 설정

#### 실습 디렉토리 준비

    mkdir hello
    cd hello
    
