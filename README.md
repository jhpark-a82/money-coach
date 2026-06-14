# 머니코치 💰
> AI 재정 코치 웹앱 — Claude 기반 개인화 재정 관리

## 로컬 실행
```bash
# 별도 설치 없이 index.html을 브라우저에서 바로 열어도 됩니다
# AI 코치 기능은 Vercel 배포 후 /api/chat 연결 시 작동합니다
open index.html
```

## Vercel 배포 방법

### 1단계 — GitHub 레포 생성
```bash
git init
git add .
git commit -m "첫 번째 MVP 배포"
git branch -M main
git remote add origin https://github.com/[계정명]/money-coach.git
git push -u origin main
```

### 2단계 — Vercel 연결
1. [vercel.com](https://vercel.com) 접속 → GitHub 로그인
2. "Add New Project" → money-coach 레포 선택
3. "Deploy" 클릭 (설정 변경 불필요)

### 3단계 — 환경변수 설정 (필수!)
Vercel 대시보드 → Settings → Environment Variables
```
CLAUDE_API_KEY = sk-ant-xxxxxxxxxxxx
```

### 4단계 — 배포 완료
`https://money-coach.vercel.app` 주소로 접속 가능!

이후 `git push`할 때마다 자동으로 재배포됩니다.

## 프로젝트 구조
```
money-coach/
├── index.html        # 메인 앱 (홈/입력/AI코치/목표)
├── api/
│   └── chat.js       # Claude API 프록시 (보안)
├── vercel.json       # Vercel 배포 설정
└── .github/
    └── workflows/
        └── deploy.yml  # 자동 배포 워크플로우
```

## 기술 스택
- Frontend: Vanilla HTML/CSS/JS (빌드 불필요)
- AI: Claude Sonnet 4.6 (Anthropic)
- Backend: Vercel Serverless Functions
- 배포: Vercel (무료 플랜)
- DB: 브라우저 메모리 (추후 Supabase 연동 예정)
