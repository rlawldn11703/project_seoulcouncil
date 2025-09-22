# 서울시의회 정보 플랫폼 (Project Seoul Council)

## 📁 프로젝트 구조 (모노레포)

```
project_seoulcouncil/
├── 📁 apps/                    # 애플리케이션들
│   ├── 📁 frontend/           # React 프론트엔드
│   │   ├── src/
│   │   │   ├── components/    # UI 컴포넌트들
│   │   │   ├── lib/          # 유틸리티 & API
│   │   │   └── styles/       # 스타일 파일들
│   │   └── package.json
│   │
│   └── 📁 backend/            # Python FastAPI 백엔드
│       ├── app/
│       └── requirements.txt
│
├── 📁 packages/               # 공유 패키지들
│   └── 📁 shared-types/      # 공통 타입 정의
│
├── 📁 docs/                   # 문서
├── 📁 tools/                  # 개발 도구
└── 📄 package-root.json      # 워크스페이스 설정
```

## 🚀 시작하기

### 전체 설치
```bash
# 루트에서 모든 의존성 설치
npm run install:all
```

### 개발 서버 실행
```bash
# 프론트엔드만 실행
npm run dev:frontend

# 백엔드만 실행 (별도 터미널)
npm run dev:backend

# 또는 각 앱에서 직접 실행
cd apps/frontend && npm run dev
cd apps/backend && uvicorn app.main:app --reload
```

### 빌드
```bash
# 프론트엔드 빌드
npm run build:frontend

# 전체 빌드
npm run build
```

## 🚀 배포

### 프론트엔드 (Vercel)
- 자동 배포: `main` 브랜치에 푸시
- 수동 배포: Vercel 대시보드에서

### 백엔드 (Railway/Render)
- `apps/backend` 폴더를 별도 배포
- 환경변수 설정 필요

## 🛠️ 개발 워크플로우

1. **기능 개발**: 각 앱에서 독립적으로 개발
2. **공통 타입**: `packages/shared-types`에서 관리
3. **빌드**: 각 앱별로 독립적 빌드
4. **배포**: 프론트엔드와 백엔드 각각 배포

## 📦 패키지 관리

- **워크스페이스**: npm workspaces 사용
- **공통 의존성**: 루트 `package.json`
- **앱별 의존성**: 각 앱의 `package.json`

---

## 기존 프로젝트 정보

가지농장은 3분 이내에 자신의 삶에 영향있는 지역 의회 안건을 파악할 수 있도록 돕는 반응형 웹 서비스입니다.

### 주요 기능
- 🏛️ **개인화된 의회 안건 추천**: 거주지와 관심사 기반 맞춤형 안건 제공
- 📊 **영향도 분석**: 각 안건이 개인의 삶에 미치는 영향도를 3단계로 표시
- 🔍 **스마트 필터링**: 높은 영향도, 최신 안건, 우리 지역 등 다양한 필터 제공
- 📱 **반응형 디자인**: 모바일과 데스크톱 모두 최적화된 사용 경험
