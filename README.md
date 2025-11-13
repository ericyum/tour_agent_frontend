# FestMoment Frontend 🎨✨

> "축제의 순간을 AI로 재해석하다"
>
> **Team FestMoment** | 염정운, 최가윤

**FestMoment Frontend**는 AI 축제 가이드 서비스의 사용자 인터페이스입니다. React 기반의 현대적이고 직관적인 UI로 축제 검색부터 AI 감성 분석, 렌더링 이미지까지 모든 기능을 아름답게 시각화합니다.

---

## 📑 목차

1. [핵심 화면](#-핵심-화면)
2. [주요 기능](#-주요-기능)
3. [기술 스택](#-기술-스택)
4. [프로젝트 구조](#-프로젝트-구조)
5. [Quick Start](#-quick-start)
6. [상세 설치 가이드](#-상세-설치-가이드)
7. [개발 가이드](#-개발-가이드)

---

## 🎨 핵심 화면

### 홈 화면
- **메인 배너**: 서비스 컨셉 소개
- **빠른 검색**: 지역/카테고리 선택으로 즉시 검색

### 축제 검색 화면
- **다각적 필터링**: 지역, 카테고리, 진행 상태별 검색
- **카드형 레이아웃**: 축제 썸네일, 기간, 위치 한눈에 파악
- **페이지네이션**: 수백 개 축제를 빠르게 탐색

### 축제 상세 화면
- **기본 정보**: 일정, 장소, 연락처, 홈페이지
- **AI 분석 탭**:
  - 📊 감성 분석 대시보드 (도넛 차트, 막대 그래프, 워드클라우드)
  - 📈 검색량 트렌드 그래프
  - 🎨 AI 렌더링 이미지 (계절/시간대별)
  - ⚠️ AI 주의사항
- **블로그 리뷰**: 실시간 리뷰 목록 및 AI 요약

### 나만의 여행 코스
- **드래그 앤 드롭**: 직관적인 코스 설계
- **AI 검증**: 이동 시간 및 현실성 검토
- **지도 연동**: 코스 위치 시각화

---

## 🌟 주요 기능

### 1. 스마트 검색 시스템

- **계층적 필터링**:
  - 지역 → 시군구 드릴다운
  - 대분류 → 중분류 → 소분류 카테고리
  - 축제 진행 상태 (진행중/예정/종료)
- **실시간 검색**: 필터 변경 시 즉시 결과 업데이트
- **결과 통계**: 검색 결과 개수 및 페이지 정보 표시

### 2. AI 분석 시각화

- **감성 분석 대시보드**:
  - 긍정/부정 비율 도넛 차트 (Recharts)
  - 만족도 분포 막대 그래프
  - 절대 점수 라인 차트
  - 이상치 박스 플롯
  - 긍정/부정 워드클라우드
- **애니메이션**: Framer Motion으로 부드러운 전환 효과
- **반응형 차트**: 화면 크기에 맞춰 자동 조정

### 3. AI 렌더링 갤러리

- **베스트 포토**: AI가 선정한 축제 대표 이미지
- **계절/시간대 렌더링**:
  - 봄/여름/가을/겨울 버전
  - 낮/밤 분위기
- **포스터 스타일**: 영화 포스터 같은 감성적 이미지
- **라이트박스**: 클릭하면 확대 보기

### 4. 사용자 경험

- **반응형 디자인**: 모바일/태블릿/데스크톱 완벽 대응
- **다크 모드 준비**: Tailwind CSS 테마 시스템
- **로딩 상태**: 스켈레톤 UI 및 로딩 인디케이터
- **에러 핸들링**: 친절한 에러 메시지 및 재시도 옵션

---

## 🛠️ 기술 스택

### Core
- **Framework**: React 18 (Hooks, Suspense)
- **Language**: TypeScript 5
- **Build Tool**: Vite 5 (HMR, Fast Refresh)
- **Styling**: Tailwind CSS 3

### State Management
- **Global State**: Zustand (코스 저장소)
- **Server State**: React Query (캐싱, 재검증) - 선택사항

### UI & Visualization
- **Components**: React Components (함수형)
- **Charts**: Recharts (선언적 차트)
- **Icons**: Lucide React
- **Animations**: Framer Motion
- **Forms**: React Hook Form (선택사항)

### Networking
- **HTTP Client**: Axios
- **API Proxy**: Vite Dev Server (개발 시)

### Routing
- **Router**: React Router v6
- **Routes**:
  - `/` - 홈
  - `/search` - 축제 검색
  - `/festivals/:name` - 축제 상세
  - `/facilities/:name` - 문화시설 상세
  - `/courses/:name` - 여행코스 상세
  - `/my-course` - 나만의 코스

---

## 📁 프로젝트 구조

```
tour_agent_frontend/
├── public/                 # 정적 파일
│   └── vite.svg
│
├── src/
│   ├── main.tsx           # 앱 진입점
│   ├── App.tsx            # 루트 컴포넌트
│   ├── index.css          # 글로벌 스타일 (Tailwind)
│   │
│   ├── components/        # 재사용 컴포넌트
│   │   ├── charts/       # 차트 컴포넌트
│   │   │   ├── AbsoluteScoreLineChart.tsx
│   │   │   ├── OutlierBoxPlot.tsx
│   │   │   ├── SatisfactionBarChart.tsx
│   │   │   └── SentimentDonutChart.tsx
│   │   ├── festival/     # 축제 관련 컴포넌트
│   │   │   └── FestivalCard.tsx
│   │   ├── layout/       # 레이아웃
│   │   │   ├── Header.tsx
│   │   │   ├── Footer.tsx
│   │   │   └── Layout.tsx
│   │   └── search/       # 검색 컴포넌트
│   │       └── SearchFilters.tsx
│   │
│   ├── pages/            # 페이지 컴포넌트 (라우팅)
│   │   ├── HomePage.tsx
│   │   ├── SearchPage.tsx
│   │   ├── FestivalDetailPage.tsx
│   │   ├── FacilityDetailPage.tsx
│   │   ├── CourseDetailPage.tsx
│   │   └── MyCoursePage.tsx
│   │
│   ├── store/            # 상태 관리 (Zustand)
│   │   └── useCourseStore.ts
│   │
│   ├── types/            # TypeScript 타입 정의
│   │   └── index.ts
│   │
│   └── lib/              # 유틸리티 및 API
│       ├── api.ts        # Axios 클라이언트
│       └── utils.ts      # 헬퍼 함수
│
├── index.html            # HTML 진입점
├── package.json
├── vite.config.ts        # Vite 설정 (프록시)
├── tailwind.config.js    # Tailwind 설정
├── tsconfig.json         # TypeScript 설정
└── postcss.config.js     # PostCSS 설정
```

---

## 🚀 Quick Start

```bash
# 1. Clone all three projects
git clone <frontend-repo> tour_agent_frontend
git clone <backend-repo> tour_agent_backend
git clone <database-repo> tour_agent_database

# 2. Start backend server first (다른 터미널)
cd tour_agent_backend
pip install -r requirements.txt
cp .env.example .env
# Edit .env and add API keys
python api_server.py

# 3. Start frontend dev server
cd tour_agent_frontend
npm install
npm run dev

# ✅ Frontend at http://localhost:3000
# 🔗 Backend at http://localhost:8000
```

---

## 📚 상세 설치 가이드

### 필수 요구사항

- **Node.js 18 이상** (LTS 권장)
- **npm 또는 yarn**
- **Backend 서버 실행 중**

### 프로젝트 Clone

**⚠️ 중요**: Backend와 Database 프로젝트와 함께 같은 디렉토리에 clone 하세요.

```bash
cd /your/projects/folder

git clone <frontend-repo-url> tour_agent_frontend
git clone <backend-repo-url> tour_agent_backend
git clone <database-repo-url> tour_agent_database
```

**올바른 디렉토리 구조**:
```
/your/projects/folder/
├── tour_agent_frontend/  ← 이 프로젝트
├── tour_agent_backend/
└── tour_agent_database/
```

### 의존성 설치

```bash
cd tour_agent_frontend
npm install
```

### Backend API 서버 주소 설정

기본적으로 `http://localhost:8000`으로 프록시 설정되어 있습니다.

다른 주소를 사용하려면 `vite.config.ts` 파일을 수정하세요:

```typescript
// vite.config.ts
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

### 개발 서버 실행

**중요**: Backend 서버가 먼저 실행되어야 합니다!

```bash
# 터미널 1: Backend 서버
cd tour_agent_backend
python api_server.py

# 터미널 2: Frontend 개발 서버
cd tour_agent_frontend
npm run dev
```

브라우저에서 http://localhost:3000 접속

### 프로덕션 빌드

```bash
npm run build
```

빌드된 파일은 `dist/` 폴더에 생성됩니다.

### 빌드 결과 미리보기

```bash
npm run preview
```

---

## 👨‍💻 개발 가이드

### 새로운 페이지 추가

1. `src/pages/`에 새 페이지 컴포넌트 생성:

```tsx
// src/pages/NewPage.tsx
export default function NewPage() {
  return (
    <div className="container mx-auto px-4 py-8">
      <h1 className="text-3xl font-bold">New Page</h1>
    </div>
  )
}
```

2. `src/App.tsx`에 라우트 추가:

```tsx
import NewPage from './pages/NewPage'

// Routes 안에 추가
<Route path="/new" element={<NewPage />} />
```

### 새로운 API 함수 추가

1. `src/lib/api.ts`에 API 함수 추가:

```typescript
export const getNewData = async (id: string) => {
  const { data } = await api.get(`/new/${id}`)
  return data
}
```

2. 컴포넌트에서 사용:

```tsx
import { useEffect, useState } from 'react'
import { getNewData } from '@/lib/api'

export default function MyComponent() {
  const [data, setData] = useState(null)

  useEffect(() => {
    getNewData('123').then(setData)
  }, [])

  return <div>{/* ... */}</div>
}
```

### Tailwind CSS 커스터마이징

`tailwind.config.js`에서 테마 커스터마이징:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#your-color',
      },
    },
  },
}
```

### 타입 정의 추가

`src/types/index.ts`에 새로운 타입 추가:

```typescript
export interface NewType {
  id: string
  name: string
  // ...
}
```

---

## 🎨 컴포넌트 가이드

### 차트 컴포넌트 사용

```tsx
import SentimentDonutChart from '@/components/charts/SentimentDonutChart'

<SentimentDonutChart
  positiveCount={80}
  negativeCount={20}
/>
```

### Zustand 스토어 사용

```tsx
import { useCourseStore } from '@/store/useCourseStore'

function MyComponent() {
  const { courses, addCourse } = useCourseStore()

  const handleAdd = () => {
    addCourse({
      id: '1',
      name: 'Test Course',
      // ...
    })
  }

  return <div>{/* ... */}</div>
}
```

---

## 🔧 트러블슈팅

### Backend 연결 실패
```
Error: Network Error / CORS Error
```
**해결**:
- Backend 서버가 실행 중인지 확인 (`http://localhost:8000`)
- `vite.config.ts`의 프록시 설정 확인
- Backend의 CORS 설정 확인

### 빌드 오류
```
Error: TypeScript compilation error
```
**해결**:
- `npm install` 재실행
- `node_modules/` 삭제 후 재설치
- TypeScript 버전 확인

### 스타일 적용 안 됨
```
Tailwind classes not working
```
**해결**:
- `index.css`에 Tailwind directives 확인
- PostCSS 설정 확인
- 개발 서버 재시작

---

## 🤝 관련 프로젝트

- [**Backend**](../tour_agent_backend) - FastAPI 기반 AI 엔진
- [**Database**](../tour_agent_database) - 데이터베이스 및 정적 리소스

---

## 📄 라이선스

이 프로젝트는 교육 및 연구 목적으로 개발되었습니다.

---

## 👥 개발팀

**Team FestMoment**
- 염정운
- 최가윤

**문의**: [GitHub Issues](https://github.com/your-repo/issues)

---

**FestMoment** - AI로 축제의 감성을 재해석합니다 ✨
