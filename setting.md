### install choco
Chocolatey는 Windows에서 apt나 yum처럼 편하게 프로그램 설치할 수 있게끔 하는 툴입니다. 

Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))


## install JDK
Eclipse Temurin OpenJDK 17을 설치합니다. 
choco install Temurin21 -y
혹은 choco install Temurin17

LTS version: Java 8, 11, 17, 21, 25


## install Git
### git 설치
choco install git -y

### ssh 키 생성 
ssh-keygen -t ed25519 -C "your_email@example.com"

### ssh 키 확인
cat ~/.ssh/id_ed25519.pub

### ssh GitHub 계정에 키 등록하기
이제 복사한 자물쇠를 GitHub 서버에 전달할 차례입니다.

1. GitHub에 로그인합니다.

2. 오른쪽 상단 프로필 클릭 → Settings로 이동합니다.

3. 왼쪽 메뉴에서 SSH and GPG keys를 클릭합니다.

4. New SSH key 버튼을 누릅니다.

5. Key 칸에 복사한 내용을 붙여넣습니다.

### ssh-agent 서비스를 자동실행으로 변경

Get-Service ssh-agent | Set-Service -StartupType Auto
Start-Service ssh-agent 

### 생성한 private 키를 ssh-agent로 등록 
ssh-add ssh-add ~\.ssh\id_ed25519

### git에 ssh코맨드 설정 변경
git config --global core.sshCommand C:/Windows/System32/OpenSSH/ssh.exe


## install intellj
choco install intellijidea-community

## node.js 설치 
choco install nodejs-lts -y

## vscode 설치
choco install vscode -y

## cursor 설치 
choco install cursoride -y
