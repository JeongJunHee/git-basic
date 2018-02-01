## 대학생을 위한 Git 실전
### 버전 관리 시스템
#### 여러 VCS 중 Git의 특징

* 사실상 표준
* "분산'버전 관리 시스템
* 가볍고 빠르고 효과적
* 버전간 차이가 아니라 전체 사본(snapshot)을 보관
* 대부분의 작업을 로컬에서 할 수 있다
* 강력한 브랜치 기능

#### DVCS 장점

* 네트워크 단절 ok
* 로컬에 빠르고 가볍게 작업
* 혼자만의 실험 브랜치 진행
* 다른 사람과 공유전에 커밋을 정리정돈

#### 세 영역 (working directory, staging area, repository)

#### 버전 확인

<pre><code>$ git version
git version 2.15.1</code></pre>

#### 기본 설정

<pre><code>$ git config --global user.name "이름"
$ git config --global user.email "이메일"
$ git config --global color.ui true</code></pre>

* -global : 지금 로그온 한 계정에 전체 설정  
* -local : 현재 저장소 로컬 설정

#### git 저장소 초기화

<pre><code>/* 현재 디렉토리 기준, Git 저장소 초기화 */
$ git init
Initialized empty Git repositiry in ...</code></pre>
    
#### 상태 확인

<pre><code>/* 현재 작업영역 상태 확인 */
$ git status</code></pre>

#### 스테이지 영역에 추가

<pre><code>/* 스테이지 영역에 추가 */
$ git add .</code></pre>

#### commit

<pre><code>/* commit하면서 설명을 남긴다 */
$ git commit -m "commit message"</code></pre>

#### commit log 확인

<pre><code>/* 커밋 로그 보기 */
$ git log</code></pre>

### 브랜치

* 작업 흐름 가지, 커밋 그래프, 커밋 줄기
* 각각의 작업 흐름 병행
* 때때로 병합(merge)하거나 버리거나 삭제

#### 브랜치(branch) 장점

* 상호 독립 다수 로컬 브랜치
* 아주 쉽게 문맥 전환이 가능
* 역할 구분에 활용하기 좋다 (배포 / 개발 / 테스트)
* 구현하려는 기능 단위의 브랜치도 가능

#### master 브랜치

* 단일 브랜치
* 주(main) 작업 영역

#### 현재 브랜치 확인

<pre><code>$ git branch
* master
$ git branch -v
* master b3a9f53 "add sub.css"</code></pre>

#### 새 브랜치 만들기

<pre><code>$ git branch testing
$ git branch
* master
  testing
$ git branch -v
* master  8796815 add sub.css
  testing 8796815 add sub.css</code></pre>
  
####  HEAD

* 각 브랜치는 특정 (최종) 커밋을 가리킴  
* HEAD는 현재 브랜치를 가리킴  
* 결국, HEAD는 현재 브랜치의 최종 커밋을 가리킴

#### 새 브랜치로 전환

<pre><code>$ git checkout testing
Switched to branch 'testing'
$ git branch -v
  master  8796815 add sub.css
* testing 8796815 add sub.css</code></pre>

#### testing 브랜치에 commit

<pre><code>$ git add test.js
$ git commit -a -m add test.js</code></pre>

#### master 브랜치로 복귀

<pre><code>$ git branch -v
  master  8796815 add sub.css
* testing 612c3aa add test.js
$ git checkout master
Switched to branch 'master'
$ git branch -v
* master  8796815 add sub.css
  testing 612c3aa add test.js</code></pre>
  
#### 브랜치 변경 유의사항

* 브랜치를 전환하면 작업 디렉토리 내용도 함께 바뀜

#### master와 testing 합치기 (merge)

<pre><code>$ git merge testing
$ git branch -v
* master  612c3aa add test.js
  testing 612c3aa add test.js</code></pre>
  
#### merge 되돌리기

<pre><code>/* git reset --hard 커밋ID */
$ git reset --hard 612c3aa</code></pre>

#### 현상황 로그 간단히 보기

<pre><code>$ git log --oneline
e069675 Merge branch 'testing'
8814e19 add div
612c3aa add test.js
8796815 add sub.css
1b59c3b add styling
a08faad add hello.html</code></pre>
