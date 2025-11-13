# Tour Agent Frontend

FestMoment 프론트엔드 - React 기반 축제 정보 웹 애플리케이션

## Quick Start

```bash
# 1. Clone all three projects in the same directory
git clone <frontend-repo> tour_agent_frontend
git clone <backend-repo> tour_agent_backend
git clone <database-repo> tour_agent_database

# 2. Start backend server first
cd tour_agent_backend
pip install -r requirements.txt
cp .env.example .env
# Edit .env and add your API keys
python api_server.py

# 3. In another terminal, start frontend dev server
cd tour_agent_frontend
npm install
npm run dev

# Frontend will be available at http://localhost:3000
```

## 기술 스택

- **Framework**: React 18
- **Language**: TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **State Management**: Zustand
- **HTTP Client**: Axios
- **Charts**: Recharts
- **Routing**: React Router
- **Animations**: Framer Motion

## 프로젝트 구조

```
src/
├── components/       # 재사용 가능한 React 컴포넌트
│   ├── charts/      # 차트 컴포넌트
│   ├── festival/    # 축제 관련 컴포넌트
│   ├── layout/      # 레이아웃 컴포넌트
│   └── search/      # 검색 컴포넌트
├── pages/           # 페이지 컴포넌트
├── store/           # Zustand 상태 관리
├── types/           # TypeScript 타입 정의
└── lib/             # 유틸리티 함수 및 API 클라이언트
```

## 설치 및 실행

### 필수 요구사항

- Node.js 18 이상
- npm 또는 yarn
- Backend 서버 실행 중이어야 함

### 프로젝트 Clone

**중요**: Backend 및 Database 프로젝트와 함께 같은 부모 디렉토리에 clone 하세요.

```bash
# 같은 디렉토리에 3개 프로젝트 clone
cd /your/projects/folder

git clone <frontend-repo-url> tour_agent_frontend
git clone <backend-repo-url> tour_agent_backend
git clone <database-repo-url> tour_agent_database
```

올바른 디렉토리 구조:
```
/your/projects/folder/
├── tour_agent_frontend/  ← 이 프로젝트
├── tour_agent_backend/
└── tour_agent_database/
```

### 설치

```bash
cd tour_agent_frontend
npm install
```

### 개발 서버 실행

**주의**: Backend 서버가 먼저 실행되어야 합니다.

```bash
# 1. 먼저 Backend 서버 실행 (다른 터미널에서)
cd ../tour_agent_backend
python api_server.py

# 2. Frontend 개발 서버 실행
cd ../tour_agent_frontend
npm run dev
```

개발 서버는 기본적으로 `http://localhost:3000`에서 실행됩니다.

### 빌드

```bash
npm run build
```

빌드된 파일은 `dist/` 폴더에 생성됩니다.

### 프리뷰

```bash
npm run preview
```

## 환경 설정

### Backend API 서버 주소 변경

기본적으로 `http://localhost:8000`으로 프록시 설정되어 있습니다.

다른 주소를 사용하려면 `vite.config.ts` 파일을 수정하세요:

```typescript
server: {
  port: 3000,
  proxy: {
    '/api': {
      target: 'http://your-backend-server:port',  // 여기를 수정
      changeOrigin: true,
    },
  },
}
```

## 주요 기능

- 축제 검색 및 필터링
- 축제 상세 정보 보기
- 감성 분석 및 트렌드 차트
- 주변 시설 및 코스 추천
- 나만의 여행 코스 만들기

## 관련 프로젝트

- [Backend](../tour_agent_backend) - FastAPI 기반 백엔드 서버
- [Database](../tour_agent_database) - 데이터베이스 및 데이터 파일
