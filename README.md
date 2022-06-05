# 리눅스 명령어
## 1. top
* 현재 시스템의 프로세스 상태를 실시간으로 화면에 출력함.
* 시스템의 상태를 전반적으로 가장 빠르게 파악 가능(CPU, Memory, Process)
* 옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌
---
### 사용법

top [option]

---
### top 실행 전 옵션
* 순간의 정보를 확인하려면 -b 옵션 추가(batch 모드)
* **-n** : top 실행 주기 설정(반복 횟수)
---
### top 실행 후 명령어
* **shift + p** : CPU 사용률 내림차순
* **shit + m** : 메모리 사용률 내림차순
* **shift + t** : 프로세스가 돌아가고 있는 시간 순
* **k** : kill. k 입력 후 PID 번호 작성. signal은 9
* **f** : sort field 선택 화면 -> q 누르면 RES순으로 정렬
* **a** : 메모리 사용량에 따라 정렬
* **b** : Batch 모드로 작동
* **c** : 명령행/프로그램 이름 토글
* **d** :　지연 시간 간격은 다음과 같다. -d ss. tt (seconds.tenths)
* **h** : 도움말
* **H** : 스레드 토글
* **i** : 유휴 프로세스 토글
* **m** :　메모리 유닛 탐지
* **n** : 반복 횟수 제한 : -n number
* **p** : PID를 다음과 같이 모니터 :-pN1 –pN2...or –pN1,N2,...
* **s** : 보안 모드 작동
* **S** : 누적 시간 모드 토글
* **u** : 사용자별 모니터링 : u somebody
* **U** : 사용자별 모니터링 : U somebody
* **u** : 입력한 유저의 프로세스만 표시 : which u
* **(숫자)1** : CPU Core별로 사용량 보여줌
---
### top 상태
* **USER** :　BSD계열에서 나타나는 항목으로 프로세스 소유자의 이름
* **UID** : SYSTEM　V계열에서 나타나는 항목으로 프로세스 소유자의 이름
* **PID** : 프로세스의 식별번호
* **PPID** : 부모 프로세스의 ID
* **PRI** : 실제 실행 우선순위
* **NI** : nice 우선순위 번호
* **SIZE** :　프로세스의 코드와 데이터의 크기(KB단위)
* **TSIZE** : 프로세스의 코드 사이즈
* **DSIZE** : 프로세스의 데이터 사이즈
* **SWAP** : 프로세스가 swap한 메모리양
* **RSS** :　실제 메모리 사용량
* **SHARE** : 프로세스가 사용하는 공유 메모리양
* **STAT** : 현재 프로세스의 상태 코드
* **LIB** : 라이브러리 페이지의 크기
* **%CPU** : CPU 사용 비율의 추정치(BSD)
* **%MEM** : 메모리의 사용 비율의 추정치(BSD)
* **TIME** :　총 CPU 사용 시간
* **COMMAND** :　프로세스의 실행 명령행
---

## 2. ps(process status)
* 현재 실행중인 프로세스 목록과 상태를 보여줌
---
### ps 사용법

$ ps [option]


System V : 대시(dash, -)사용함
ex)　$ps- ef

BSD : 대시 사용 안함
ex)　$ps aux

---
### ps 옵션
* **-A** :　모든 프로세스를 출력함.
* **a(BSD)** : 터미널과 연관된 프로세스를 출력하는 옵션. 보통 x옵션과 연계하여 모든 프로세스를 출력할 때 사용함.
* **-a** : 세션 리더(일반적으로 로그인 셀)을 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력함.
* **-e** : 커널 프로세스를 제외한 모든 프로세스를 출력함.
* **-ef** : 모든 프로세스의 모든 정보 출력함.
* **-f** : 풀 포맷으로 보여줌. 유닉스 스타일로 출력해주는 옵션으로 UID, PID, PPID 등이 함께 표시됨.
* **-i** : 상세내역을 보여줌.
* **-l(system V) / l(BSD)** : 긴 포맷으로 보여줌. 프로세스의 정보를 길게 옵션으로 우선순위와 관련된 PRI와 NI값을 확인할 수 있음.
* **-o** : 출력 포맷을 지정하는 옵션으로, 값으로는 pid, tty, time, cmd 등을 지정할 수 있음.
* **-M** : 64비트 프로세스들을 보여줌.
* **-m** : 프로세스들 뿐만 아니라 커널 스레드들도 보여줌.
* **-p** : 특정 PID를 지정할 때 사용함.
* **-r** : 현재 실행 중인 프로세서를 보여줌.
* **u(BSD)** : 프로세스의 소유자를 기준으로 출력함.
* **-u** : 특정 사용자의 프로세스 정보를 확인할 때 사용함. 사용자를 지정하지 않으면 현재 사용자를 기준으로 정보를 출력함.
* **x(BSD)** : 데몬 프로세스처럼 터미널에 종속되지 않는 프로세스를 출력함. 보통 a옵션과 결합하여 모든 프로세스를 출력할 떼 사용함.
* **-x** : 로그인 상태에 있는 동안 아직 완료되지 않은 프로세서들을 보여줌. 
---
### ps 상태
* **USER** :　BSD계열에서 나타나는 항목으로 프로세스 소유자의 이름
* **UID** : SYSTEM　V계열에서 나타나는 항목으로 프로세스 소유자의 이름
* **PID** : 프로세스의 식별번호
* **PPID** : 부모 프로세스의 ID
* **%CPU** : CPU 사용 비율의 추정치(BSD)
* **%MEM** : 메모리의 사용 비율의 추정치(BSD)
* **VSZ** : K단위 또는 페이지 단위의 가상메모리 사용량
* **RSS** :　실제 메모리 사용량
* **TTY** :　프로세스와 연결된 터미널
* **S, STAT** : 현재 프로세스의 상태 코드 (S:System V, STAT:BSD)
* **TIME** :　총 CPU 사용 시간
* **COMMAND** :　프로세스의 실행 명령행
* **STIME** : 프로세스가 시작된 시간 혹은 날짜
* **C, CP** : 짧은 기간 동안의 CPU 사용률 (C:System V, CP:BSD)
* **F** :　프로세스의 플래그
* **PRI** : 실제 실행 우선순위
* **NI** : nice 우선순위 번호
---

## 3. jobs
* 다음의 프로세스 목록을 출력해주는 명령어
   ##### * 백그라운드로 실행중인 프로세스
   ##### * 현재 중지된 프로세스
---
### 사용법
jobs [옵션] [작업번호]

---
### jobs 옵션
* -l : 프로세스 그룹 ID를 state 필드 앞에 출력.
* -n : 프로세스 그룹 중에 대표 프로세스 ID를 출력.
* -p : 각 프로세스 ID에 대해 한 행씩 출력.
* command : 지정한 명령어를 실행.
---
### jobs로 출력되는 백그라운드 작업의 상태값
* Running : 작업이 계속 진행중임.
* Done : 작업이 완료되어 0을 반환.
* Done(code) : 작업이 종료되었으며 0이 아닌 코드를 반환.
* Stopped :　작업이 일시 중단
* Stopped(SIGTSTP) :　SIGTSTP 시그널이 작업을 일시 중단.
* Stopped(SIGSTOP) :　SIGSTOP 시그널이 작업을 일시 중단.
* Stopped(SIGTTIN) :　SIGTTIN 시그널이 작업을 일시 중단.
* Stopped(SIGTTOU) :　SIGTTOU 시그널이 작업을 일시 중단.
---

## 4. kill
* 프로세스를 죽일 때 사용함.
* 프로세스에 시그널을 보내 원하는 작업을 하게 하는 명령어
---
### 사용법

$kill [option or signal(번호 또는 이름)] <pid> [...]

---
### kill 옵션
  
* -l : 시그널의 종류를 출력함.

---
### 주요 시그널
1 ) SIGHUP : 세션이 종료될 때 시스템이 내리는 시그널
  
2 ) SIGINT : Ctrl+C, 종료 요청 시그널
  
9 ) SIGKILL : 강제 종료 시그널
  
11 ) SIGSEGV : 메모리 침범이 일어날 때 시스템이 보내는 시그널
  
15 ) SIGTERM : 기본값, 종료 요청 시그널
  
20 ) SIGTSTP : Ctrl+Z, 일시 중지 요청 시그널
---

# VIM 에디터
## 매크로 사용법
### q
매크로 저장하기 : q<저장할 매크로 문자>
### @
매크로 불러오기 :　＠<저장한 매크로 문자>

### 사용예시
* A문자에 매크로 내용을 기록하기(recoding) :　qA-> 매크로작성->q(recoding 종료)
* 특정문자에 저장한 매크로 실행 : @<저장한 매크로 문자>
* 마지막에 수행한 매크로 실행 :＠＠
* <반복하고 싶은 횟수 숫자>@<저장한 매크로 문자> :　10@A : 매크로 10회 실행


