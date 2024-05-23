# opensource
-----------------------------------------
#  top 명령어
+ `top` 명령어는 리눅스 시스템에서 실행 중인 프로세스에 대한 정보를 실시간으로 표시하는 시스템 모니터링 도구 입니다.
+ 터미널에서 `top` 명령어를 실행하면 프로세스 목록과 cpu,메모리 사용량 등과 같은 다양한 시스템 매트릭을 동적으로 업데이트 되는 형태로 볼 수 있습니다. 시스템 관리자 및 사용자들이 시스템 성능을 모니터링 하고 리소스를 소모하는 프로세스를 식별하는 데 유용한 강력한 도구입니다.
------------------------------------------
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
# ps 명령어




