# tmux-helper

tmux + TPM + yazi 환경 설치 가이드입니다.

제가 사용 중인 tmux 설정 파일: [tmux.conf](https://github.com/ultra21c/tmux-helper/blob/main/tmux.conf)
(raw: <https://raw.githubusercontent.com/ultra21c/tmux-helper/main/tmux.conf>)

> 이 설정은 macOS 기준입니다(클립보드 복사에 `pbcopy` 사용). 상태 바 아이콘 표시를 위해 Nerd Font 계열 폰트를 권장합니다.

---

## Option 1) AI Agent에게 시키기

아래 프롬프트를 그대로 복사해서 사용하는 AI 코딩 에이전트(Claude Code, Codex, Cursor 등)에 붙여넣으면 에이전트가 알아서 설치를 진행합니다.

```text
아래 작업을 순서대로 수행해서 내 tmux 환경을 설치하고 설정해줘.

설정 파일(raw): https://raw.githubusercontent.com/ultra21c/tmux-helper/main/tmux.conf

수행할 작업:
1. tmux가 설치되어 있는지 확인하고, 없으면 설치해줘
   - macOS: brew install tmux
   - Linux/WSL: sudo apt install tmux
2. 기존 ~/.tmux.conf가 있으면 ~/.tmux.conf.backup으로 백업해줘
3. 위 링크에서 raw 파일을 다운로드해서 ~/.tmux.conf로 저장해줘
4. TPM(Tmux Plugin Manager)이 없으면 설치해줘
   - git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
5. yazi 파일 탐색기가 없으면 설치해줘 (설정에서 Prefix + Tab 키로 사용)
   - macOS: brew install yazi
   - 기타 OS: https://yazi-rs.github.io/docs/installation 참고
6. tmux가 실행 중이면 설정을 리로드해줘
   - tmux source-file ~/.tmux.conf
7. 마지막으로 "tmux 실행 후 Prefix + I (Shift+i)를 눌러 플러그인을 설치하세요" 라고 안내해줘

주의사항:
- 기존 설정 파일(~/.tmux.conf)은 반드시 백업 후 진행해줘
- 이미 설치된 프로그램은 재설치하지 말아줘
```

---

## Option 2) 직접 설치하기

### 1. tmux 설치

<https://github.com/tmux/tmux/wiki/Installing>

```bash
# macOS
brew install tmux

# Linux / WSL
sudo apt install tmux
```

### 2. TPM (Tmux Plugin Manager) 설치

<https://github.com/tmux-plugins/tpm?tab=readme-ov-file#installation>

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

### 3. tmux.conf 파일 저장

기존 설정이 있으면 먼저 백업하세요.

```bash
[ -f ~/.tmux.conf ] && cp ~/.tmux.conf ~/.tmux.conf.backup
curl -fsSL https://raw.githubusercontent.com/ultra21c/tmux-helper/main/tmux.conf -o ~/.tmux.conf
```

또는 [tmux.conf](https://github.com/ultra21c/tmux-helper/blob/main/tmux.conf) 내용을 복사해서 `~/.tmux.conf`에 저장해도 됩니다.

### 4. 플러그인 설치

tmux를 실행한 뒤:

`Prefix + I` (대문자 I)를 눌러 플러그인을 설치합니다.

### 5. yazi 파일 탐색기 설치

<https://yazi-rs.github.io/docs/installation>

```bash
# macOS
brew install yazi
```

설정에서 `Prefix + Tab`으로 yazi를 50% 분할 창으로 엽니다.

### 6. 설정 반영

tmux 실행 중이라면:

`Prefix + r` (설정 리로드)

또는 터미널에서:

```bash
tmux source-file ~/.tmux.conf
```
