# 간호 노트 에이전트

PDF(강의안·교재 필기) → 단계별 검토 → 색상 코딩 2단 요약 노트

## 사용 흐름

1. **PDF 업로드** — 강의안·교재 필기 PDF (여러 개 가능), AI 자동 구분
2. **목차 확인** — AI가 제안한 섹션 구성을 검토·수정
3. **섹션별 검토** — 각 섹션 노트를 확인하고 수정 요청 가능
4. **완성 노트** — 전체 노트 확인 후 PDF 저장

## 배포 방법 (Vercel)

### 1. GitHub에 올리기

```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/[내 유저명]/nursing-agent.git
git push -u origin main
```

### 2. Vercel 배포

1. [vercel.com](https://vercel.com) 접속 → **GitHub으로 로그인**
2. **Add New Project** → GitHub 저장소 선택
3. **Environment Variables** 에 추가:
   - Key: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-...` (Anthropic 콘솔에서 발급)
4. **Deploy** 클릭

완료되면 `https://[프로젝트명].vercel.app` 링크로 어디서든 접속 가능!

## 파일 구조

```
nursing-agent/
├── api/
│   └── claude.js        # Vercel 서버리스 함수 (API 키 보호)
├── public/
│   └── index.html       # 메인 앱
├── vercel.json          # Vercel 설정
└── README.md
```

## API 키 발급

[console.anthropic.com](https://console.anthropic.com) → API Keys → Create Key
