# tmux 치트시트

> 기본 프리픽스: **`Shift + Space`**
> 아래 표에서 `Shift + Space` 뒤의 키는 프리픽스를 놓고 이어서 누릅니다.
> `$` = 쉘 명령, `:` = tmux 명령 모드

## ⭐ 자주 쓰는 핵심 (실전 필수)

| 키 / 명령 | 설명 |
|---|---|
| `tmux new -s 이름` | 이름 붙여 새 세션 시작 |
| `tmux a -t 이름` | 해당 세션에 다시 접속 |
| `tmux ls` | 세션 목록 보기 |
| `Shift + Space` → `d` | 세션에서 나가기(분리) |
| `Shift + Space` → `$` | 세션 이름 바꾸기 |
| `Shift + Space` → `c` | 윈도우 생성 |
| `Shift + Space` → `,` | 윈도우 이름 바꾸기 |
| `Shift + Space` → `&` | 현재 윈도우 닫기 |
| `Shift + Space` → `%` | 팬 좌우 분할 |
| `Shift + Space` → `"` | 팬 상하 분할 |
| `Shift + Space` → `x` | 현재 팬 닫기 |
| `Shift + Space` → `화살표` | 팬 간 이동 |
| `Shift + Space` → `z` | 팬 확대/원복 토글 |
| `Shift + Space` → `0`–`9` | 번호로 윈도우 전환 |

## 세션 (Session)

| 키 / 명령 | 설명 |
|---|---|
| `tmux` / `tmux new` | 새 세션 시작 |
| `tmux new -s 이름` | 이름 붙여 새 세션 시작 |
| `tmux new -A -s 이름` | 없으면 생성, 있으면 접속 |
| `Shift + Space` → `$` | 세션 이름 바꾸기 |
| `Shift + Space` → `d` | 세션에서 분리(detach) |
| `tmux ls` | 세션 목록 |
| `Shift + Space` → `s` | 모든 세션 표시/선택 |
| `tmux a` | 마지막 세션에 접속 |
| `tmux a -t 이름` | 해당 세션에 접속 |
| `: kill-session` | 현재 세션 종료 |
| `tmux kill-ses -t 이름` | 해당 세션 종료 |
| `tmux kill-session -a` | 현재 세션 제외 전부 종료 |
| `Shift + Space` → `w` | 세션·윈도우 미리보기 |
| `Shift + Space` → `(` / `)` | 이전 / 다음 세션 |

## 윈도우 (Window)

| 키 / 명령 | 설명 |
|---|---|
| `Shift + Space` → `c` | 윈도우 생성 |
| `Shift + Space` → `,` | 현재 윈도우 이름 바꾸기 |
| `Shift + Space` → `&` | 현재 윈도우 닫기 |
| `Shift + Space` → `w` | 윈도우 목록 |
| `Shift + Space` → `p` / `n` | 이전 / 다음 윈도우 |
| `Shift + Space` → `0`–`9` | 번호로 윈도우 전환 |
| `Shift + Space` → `l` | 마지막 활성 윈도우로 |
| `tmux new -s 세션 -n 윈도우` | 세션·윈도우 이름 지정 생성 |
| `: swap-window -s 2 -t 1` | 윈도우 2와 1 위치 교환 |
| `: movew -s 0:9` | 현재 세션 내 윈도우 위치 변경 |
| `: movew -r` | 윈도우 번호 빈틈 재정렬 |

## 팬 (Pane)

| 키 / 명령 | 설명 |
|---|---|
| `Shift + Space` → `%` | 좌우로 분할 (수직선) |
| `Shift + Space` → `"` | 상하로 분할 (수평선) |
| `Shift + Space` → `화살표` | 해당 방향 팬으로 이동 |
| `Shift + Space` → `o` | 다음 팬으로 |
| `Shift + Space` → `;` | 마지막 활성 팬으로 |
| `Shift + Space` → `q` | 팬 번호 표시 |
| `Shift + Space` → `z` | 팬 확대/원복 토글 |
| `Shift + Space` → `Space` | 팬 레이아웃 전환 |
| `Shift + Space` → `{` / `}` | 팬을 왼쪽 / 오른쪽으로 이동 |
| `Shift + Space` → `Ctrl + 화살표` | 현재 팬 크기 조정 |
| `Shift + Space` → `!` | 팬을 윈도우로 분리 |
| `Shift + Space` → `x` | 현재 팬 닫기 |
| `: join-pane -s 2 -t 1` | 윈도우 2를 1의 팬으로 병합 |
| `: setw synchronize-panes` | 모든 팬에 동시 입력 토글 |

## 복사 모드 (Copy Mode)

| 키 / 명령 | 설명 |
|---|---|
| `: setw -g mode-keys vi` | vi 키 사용 설정 |
| `Shift + Space` → `[` | 복사 모드 진입 |
| `q` | 모드 종료 |
| `g` / `G` | 맨 위 / 맨 아래 줄로 |
| `h` `j` `k` `l` | 커서 좌·하·상·우 이동 |
| `w` / `b` | 단어 단위 앞 / 뒤로 |
| `/` / `?` | 앞으로 / 뒤로 검색 |
| `n` / `N` | 다음 / 이전 검색 결과 |
| `Space` | 선택 시작 |
| `Enter` | 선택 복사 |
| `Esc` | 선택 지우기 |
| `Shift + Space` → `]` | 붙여넣기 |
| `: list-buffers` | 모든 버퍼 표시 |
| `: save-buffer buf.txt` | 버퍼 내용을 파일로 저장 |

## 기타 · 도움말

| 키 / 명령 | 설명 |
|---|---|
| `Shift + Space` → `:` | 명령 모드 진입 |
| `: set mouse on` | 마우스 모드 활성화 |
| `: set -g OPTION` | 모든 세션에 옵션 설정 |
| `: setw -g OPTION` | 모든 윈도우에 옵션 설정 |
| `tmux -V` | tmux 버전 표시 |
| `Shift + Space` → `?` | 단축키(키 바인딩) 목록 |
| `tmux info` | 세션·윈도우·팬 정보 표시 |
