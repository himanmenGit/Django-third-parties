# tmux
## 터미널 화면을 분할 하기 위한 Tool
### 화면 분할
* 하나의 터미널 화면을 여러 개의 터미널로 쪼갬.
* 화면 크기를 조절 가능.
* 터미널을 세션으로 관리 할 수 있다.

### 설치 방법
OS X의 Homebrew로 설치
```bash
brew install tmux
```
설치가 완료되면 `tmux -V` 로 실행 확인

### 용어
* 프리픽스(prefix)  : 단축키를 입력하기 전에 먼저 입력해야하는 키 조합 `ctrl + b`
* 세션(session) : `tmux`가 관리하는 가장 큰 단위. 세션에 `attach/detach`가 이루어짐. `detach`해도 세션은 백그라운드에서 계속 실행.
* 윈도우(window): 세션안에 존재하는 탭 기능. 하나의 세션에 여러 윈도우를 가질 수 있음. 세션안에서 윈도우를 만들고 전환이 가능하며 탭을 이동할 때 처럼 화면이 전환.
* 팬(pane) : 윈도우 안에 존재하는 화면 단위. 하나의 윈도우에 여러 개의 팬을 가질수 있다. 전체화면을 세로로 2등분하면 2개의 펜이 생김.

### Session
세션 실행
```bash
$ tmux
or
$ tmux new -s <session_name>
$ tmux new-session -s <session_name>
```

세션 종료
```bash
$ exit
or
$ tmux kill-session -t <session_name>
```

세션 attach
```bash
$ tmux attach -t <session_name>
```

세션 detach
```bash
<prefix> + d
```
ctrl+b, +d로 나오면 session은 살아 있다. 그래서 attach로 다시 session에 접속가능

세션 목록 보기
```bash
tmux ls
```

### 윈도우
윈도우와 관련된 명령어 및 단축키는 모두 세션안에서 실행해야 한다

윈도우 생성
```bash
<prefix> + c
```

윈도우 이름 변경
```bash
<prefix> + ,
```

이전, 다은 윈도우 이동
```bash
<prefix> + n
<prefix> + p
```

모든 윈도우 리스트 보기
```bash
<prefix> + w
```

### Pane
세로로 윈도우 분할
```bash
<prefix> + %
```

가로로 윈도우 분할
```bash
<prefix> + "
```

팬이동
```bash
<prefix> + q + 숫자
```

줌
특정 팬을 전체화면으로 전환
한번더 누르면 원상태 복구
```bash
<prefix> + z
```
