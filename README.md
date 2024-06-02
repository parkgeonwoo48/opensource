# *opensource*
-----------------------------------------
#  *top 명령어*
+ `top` 명령어는 리눅스 시스템에서 실행 중인 프로세스에 대한 정보를 실시간으로 표시하는 시스템 모니터링 도구 입니다.
+ 터미널에서 `top` 명령어를 실행하면 프로세스 목록과 cpu,메모리 사용량 등과 같은 다양한 시스템 매트릭을 동적으로 업데이트 되는 형태로 볼 수 있습니다. 시스템 관리자 및 사용자들이 시스템 성능을 모니터링 하고 리소스를 소모하는 프로세스를 식별하는 데 유용한 강력한 도구입니다.
------------------------------------------
주요 옵션

+ `top -d <초>`

  화면 갱신 주기를 설정합니다. 기본값은 3초입니다.

+ `top -p <PID>`

  특정 프로세스 ID(PID)를 모니터링합니다.

+ `top -u <사용자>`

  특정 사용자의 프로세스를 모니터링합니다.

+ `top -n <반복 횟수>`

  지정된 횟수만큼 갱신한 후 종료합니다.

+ `top -b`

  배치 모드로 실행합니다. 이 모드는 주로 스크립트에서 사용되며, 출력을 표준 출력으로 보냅니다.

---




예제

+ `top -u username`

  특정 사용자의 프로세스만 모니터링 하는 명령어

+ `top -d time`

  특정 시간 간격으로 업데이트 하는 명령어

+ `top -b -n 1 > top_output.txt`

  스크립트에서 사용하거나 특정 시간 동안의 시스템 상태를 기록하고 싶을 때 유용한 명령어

  `-n 1`은 1회 업데이트 후 종료하라는 의미
+ `top` 실행 후 `k`를 누르는 명령어

  종료하고자 하는 프로세스의 PID를 입력하여 종료시키는 명령어

+ `top -o TIME+`

  실행 시간을 기준으로 상위프로세스를 보고 싶다면 -o를 이용하여 TIME+를 기준으로 정렬하는 명령어

  ---
# *ps 명령어*
+ `ps` 명령어는 유닉스 및 유닉스 계열 운영 체제에서 현재 실행 중인 프로세스 목록을 표시하는 데 사용됩니다. 이 명령어는 시스템 관리자와 사용자에게 실행 중인 프로세스에 대한 중요한 정보를 제공합니다. 여기에는 프로세스 ID (PID), 사용자, CPU 사용량, 메모리 사용량, 실행 시간, 실행 명령어 등이 포함될 수 있습니다.
---
유용한 옵션
+ `ps aux`

  모든 사용자, 로그인하지 않은 터미널 그리고 더 상세한 포맷으로 시스템의 모든 프로세스를 나열합니다.
+ `ps -ef`

  `-e` 옵션은 모든 프로세스를 포함하고, `-F`는 풀 포맷으로 출력하여 매우 자세한 정보를 제공합니다.
+ `ps -e --forest`
  트리 형식으로 프로세스를 보여주어 각 프로세스의 부모-자식 관계를 쉽게 파악할 수 있습니다.


+ `ps -o`

  `-o` 옵션은 출력 형식을 사용자 정의할 수 있습니다.

  예를 들어, PID, PPID, 명령어, 메모리 사용률, CPU 사용률을 출력하도록 설정 할 수 있습니다.
---
필터링 및 정렬
+ `ps -u username`

  특정 사용자의 프로세스를 나열합니다.
+ `ps -p id`

  지정된 PID에 해당하는 프로세스의 정보를 출력합니다.
+ `ps aux --sort=-%mem`

  메모리 사용량을 기준으로 프로세스를 내림차순으로 정렬합니다.

  CPU 사용량을 기준으로 정렬하려면 `--sort=-%cpu`를 사용할 수 있습니다.
---
예시

+ `ps aux | grep apache`

  `ps aux`로 모든 프로세스를 나열하고 `grep` 명령어를 사용하여 "apache"라는 문자열을 포함하는 프로세스만 필터링합니다.
+ `ps -p 1234`

  특정 프로세스 ID의 정보를 확인

+ `ps -u username`

  특정 사용자의 모든 프로세스를 나열

---
# *jobs 명령어*
+ `jobs` 명령어는 UNIX 및 UNIX 계열 운영 체제(Linux 등)에서 현재 쉘 세션에서 실행 중인 백그라운드 작업을 나열하는 데 사용됩니다.
+ 이 명령어는 사용자에게 백그라운드에서 실행 중인 작업의 상태를 확인할 수 있는 간단한 방법을 제공합니다.
---
주요 옵션

+ `jobs`

  현재 쉘 세션에서 실행 중인 모든 작업을 나열합니다.

  각 작업에는 작업 번호, 상태 및 명령어가 포함됩니다.
+ `jobs -1`

  각 작업의 프로세스 ID를 포함하여 보다 자세한 정보를 나열합니다.

+ `jobs -n`

  상태가 변경된 작업만 표시합니다.
+ `jobs -p`

  각 작업의 프로세스 ID만 출력합니다.
+ `jobs -r`

  실행 중인 작업만 나열합니다.
+ `jobs -s`

  중지된 작업만 나열합니다.
---
작업 제어

+ `bg %1`

  중지된 작업을 백그라운드에서 계속 실행합니다. `%1`은 작업 번호를 나타냅니다.

+ `fg %1`

  백그라운에서 실해 중인 작업을 포그라운드로 가져옵니다.

+ `kill %1`

  특적 작업을 종료합니다.
---
예제

+ `sleep 100 &`

  `sleep 100` 명령어를 백그라운드에서 실행합니다. 이 작업은 100초 동안 대기합니다.

+ `jobs`

  현재 쉘 세션에서 실행 중인 모든 작업을 나열합니다.

+ `jobs -l`

  각 작업의 프로세스 ID와 함께 보다 자세한 정보를 나열합니다.

+ `bg %1`

  중지된 작업 번호 1을 백그라운드에서 계속 실행합니다.

+ `fg %1`

  중지된 작업 번호 1을 백그라운드에서 계속 실행합니다.

---
# *kill 명령어*
+ `kill` 명령어는 UNIX 및 UNIX 계열 운영 체제(Linux 등)에서 프로세스를 종료하거나 신호를 보내는 데 사용됩니다. 이 명령어는 시스템 관리자가 프로세스를 제어하고 관리하는 데 매우 유용합니다.
+ `kill` 명령어는 특정 프로세스 ID(PID)에 신호를 보내어 다양한 작업을 수행할 수 있습니다.
---
주요 옵션

+ `kill [option] <PID>`

  기본적으로 `kill` 명령어는 지정된 프로세스 ID에 SIGTERM(종료) 신호를 보냅니다.

+ `kill -1`

  사용 가능한 신호 목록을 출력합니다.

+ `kill -s 신호 <PID>`

  지정된 신호를 프로세스에 보냅니다. 여기서 `<신호>`는 신호 이름 또는 번호일 수 있습니다.

+ `kill -9 <PID>`
  
  SIGKILL 신호(강제 종료)를 보냅니다.
  이 신호는 프로세스를 즉시 종료하며, 프로세스가 정리 작업을 수행할 기회를 주지 않습니다.
+ `kill -15 <PID>`

  SIGTERM 신호(정상 종료)를 보냅니다. 이는 기본 신호이며, 프로세스가 정리 작업을 수행할 시간을 줍니다.
+ `kill -HUP <PID>`

  SIGHUP 신호를 보냅니다. 이는 일반적으로 프로세스를 재시작하거나 재구성하도록 요청할 때 사용됩니다.

---
신호
+ SIGTERM (15): 프로세스에게 정상 종료를 요청합니다. 프로세스가 종료하기 전에 정리 작업을 수행할 수 있습니다.
+ SIGKILL (9): 프로세스를 즉시 종료합니다. 정리 작업 없이 강제 종료되므로, 데이터 손실이 발생할 수 있습니다.
+ SIGHUP (1): 프로세스에게 연결이 끊겼음을 알립니다. 일반적으로 데몬 프로세스의 재시작에 사용됩니다.
+ SIGINT (2): 프로세스에게 인터럽트 요청을 보냅니다. 일반적으로 터미널에서 `Ctrl+C`를 누를 때 발생합니다.
+ SIGSTOP: 프로세스를 일시 중지합니다.
+ SIGCONT: 일시 중지된 프로세스를 계속 실행합니다.
---
예제

+ `kill ID`

  프로세스 ID 에게 SIGTERM 신호를 보내 종료를 요청합니다.

+ `kill -9 ID`

  프로세스 ID에게 SIGKILL 신호를 보내 강제 종료합니다.

+ `kill -l`

  시스템에서 사용 가능한 신호의 목록을 출력합니다.

+ `kill -HUP ID`

  프로세스 ID에게 SIGHUP 신호를 보내 재시작을 요청합니다.

+ `kill -s SIGUSR1 ID`

  프로세스 ID에게 사용자 정의 신호 SIGUSR1을 보냅니다.






