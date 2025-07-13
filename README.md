# Claude Configuration Files

이 저장소는 Claude CLI 설정 파일들을 저장하고 새로운 환경에서 쉽게 설정할 수 있도록 도와줍니다.

## 📁 저장소 구조

```
claude-config/
├── CLAUDE.md           # Claude Code를 위한 가이드 문서
├── README.md          # 이 파일
├── .gitignore         # Git에서 제외할 파일들 (민감한 정보 보호)
├── ide/               # IDE 통합 설정들
├── statsig/           # 분석 및 기능 플래그 설정
└── templates/         # 새 환경 설정을 위한 템플릿들
```

## 🚀 새 환경에서 설정하기

### 1. 저장소 클론

```bash
git clone https://github.com/Gwang-Hyeok/claude-config.git
cd claude-config
```

### 2. Claude 설정 디렉토리로 복사

```bash
# 기존 설정이 있다면 백업
mv ~/.claude ~/.claude.backup

# 설정 파일들 복사
cp -r . ~/.claude/

# Claude 디렉토리로 이동
cd ~/.claude
```

### 3. 인증 설정

Claude CLI에 로그인하여 새로운 인증 정보를 생성합니다:

```bash
claude auth login
```

## 📝 설정 파일 설명

- **CLAUDE.md**: Claude Code가 이 환경에서 작업할 때 참조하는 가이드
- **.gitignore**: 민감한 정보(인증 토큰, 세션 데이터)가 Git에 커밋되지 않도록 보호
- **ide/**: VS Code, IntelliJ 등 IDE 통합 설정
- **statsig/**: Claude 사용 통계 및 기능 플래그 설정

## ⚠️ 보안 주의사항

이 저장소는 다음 파일들을 **포함하지 않습니다**:

- `.credentials.json` - 인증 토큰 (새 환경에서 재생성 필요)
- `projects/` - 프로젝트별 세션 데이터
- `todos/` - 개인 작업 목록

## 🔄 설정 업데이트하기

현재 환경의 설정을 저장소에 반영하려면:

```bash
cd ~/.claude
git add .
git commit -m "Update Claude configuration"
git push origin main
```

## 🛠️ 문제 해결

### Claude CLI가 설정을 인식하지 못하는 경우

1. 디렉토리 권한 확인: `chmod 755 ~/.claude`
2. Claude CLI 재시작: `claude --version`
3. 설정 파일 확인: `ls -la ~/.claude`

### 인증 문제

```bash
claude auth logout
claude auth login
```

## 📞 지원

문제가 발생하면 [Claude 공식 문서](https://docs.anthropic.com/en/docs/claude-code)를 참조하거나 이슈를 등록해주세요.
