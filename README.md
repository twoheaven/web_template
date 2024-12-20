
# Web Template

This project is a basic web template using React, Vite, and Styled Components. It serves as a starting point for building modern web applications with a simple and fast development setup.

## Features

- React 18
- TypeScript
- Vite for fast development and build
- Styled Components for styling
- ESLint for linting
- Axios for HTTP requests
- React Router for navigation

## Installation

To get started with the project, clone this repository and install the dependencies.

### Clone the repository

```bash
git clone https://github.com/your-username/web_template.git
cd web_template
```

---

## **`Project Structure`**


src/                    // 프로젝트의 루트 소스 디렉토리
├── assets/             // 정적 자산(이미지, 폰트 등)을 관리하는 디렉토리
│   ├── images/         // 프로젝트에서 사용하는 이미지 파일 저장
│   └── fonts/          // 프로젝트에서 사용하는 폰트 파일 저장
├── components/         // 재사용 가능한 UI 컴포넌트를 관리하는 디렉토리
│   ├── common/         // 공통적으로 사용되는 컴포넌트들을 관리하는 디렉토리
│   │   ├── Button/     // 버튼 컴포넌트 관련 파일들 관리
│   │   │   ├── Button.tsx          // 버튼 컴포넌트의 구현 파일
│   │   │   ├── Button.styles.ts    // 버튼 컴포넌트의 스타일 정의
│   │   │   └── index.ts            // 버튼 컴포넌트의 모듈을 내보내는 파일
│   │   └── Input/      // 입력 컴포넌트 관련 파일들 관리
│   ├── layout/         // 레이아웃을 구성하는 컴포넌트들을 관리하는 디렉토리
│   │   ├── Header/     // 헤더 컴포넌트 관련 파일들 관리
│   │   ├── Footer/     // 푸터 컴포넌트 관련 파일들 관리
│   │   └── Sidebar/    // 사이드바 컴포넌트 관련 파일들 관리
│   └── feature/        // 특정 기능과 관련된 컴포넌트를 관리하는 디렉토리
│       ├── Auth/       // 인증 관련 기능 컴포넌트들 관리
│       └── Dashboard/  // 대시보드 관련 기능 컴포넌트들 관리
├── pages/              // 페이지 단위의 컴포넌트를 관리하는 디렉토리
│   ├── Home/           // 홈 페이지 컴포넌트 관련 파일들 관리
│   ├── Login/          // 로그인 페이지 컴포넌트 관련 파일들 관리
│   └── Dashboard/      // 대시보드 페이지 컴포넌트 관련 파일들 관리
├── hooks/              // React 커스텀 훅을 관리하는 디렉토리
│   ├── useAuth.ts      // 인증 관련 커스텀 훅
│   └── useForm.ts      // 폼 처리 관련 커스텀 훅
├── apis/                // 서버와의 API 통신 로직을 관리하는 디렉토리
│   ├── authApi.ts         // 인증 API 관련 함수들 정의
│   └── userApi.ts         // 사용자 관련 API 함수들 정의
├── utils/              // 유틸리티 함수들을 관리하는 디렉토리
│   ├── format.ts       // 데이터 형식 관련 유틸리티 함수들 정의
│   ├── validation.ts   // 입력값 검증 관련 유틸리티 함수들 정의
|   └── paths.ts        // React Router 경로를 Enum으로 관리
├── types/              // TypeScript 타입 정의를 관리하는 디렉토리
│   ├── user.ts         // 사용자 관련 타입 정의
│   └── common.ts       // 공통적으로 사용하는 타입 정의
├── styles/             // 스타일 관련 파일들을 관리하는 디렉토리
│   ├── global.ts       // 전역 스타일 정의
│   └── theme.ts        // 프로젝트의 테마 설정 정의
└── store/              // 상태 관리(store)와 관련된 파일들을 관리하는 디렉토리
    ├── auth/           // 인증 관련 상태 관리 파일들 관리
    └── user/           // 사용자 관련 상태 관리 파일들 관리

package.json           # Project configuration
tsconfig.json          # TypeScript configuration
vite.config.ts         # Vite configuration
eslint.config.js       # ESLint configuration
index.html             # Main HTML file with `div#root` for React mounting.
---

## **`src/`**
애플리케이션의 모든 소스 코드가 포함된 최상위 폴더입니다. 디렉터리별로 역할과 사용 목적을 분리하여 관리합니다.

---

### **1. `assets/`**
애플리케이션에서 사용되는 정적 리소스(이미지, 폰트 등)를 저장하는 폴더입니다.

- **`images/`**:  
  PNG, JPG, SVG 등 이미지 파일을 저장합니다. 로고, 배경 이미지, 아이콘 등 정적 이미지 리소스가 여기에 위치합니다.  
  예: `logo.png`, `background.jpg`
  
- **`fonts/`**:  
  웹폰트를 저장합니다. Google Fonts나 외부 리소스를 다운로드하거나 커스텀 폰트를 포함할 수 있습니다.  
  예: `Roboto.woff`, `OpenSans.ttf`

---

### **2. `components/`**
애플리케이션의 재사용 가능한 UI 컴포넌트를 저장합니다. 역할에 따라 `common/`, `layout/`, `feature/`로 세분화됩니다.

- **`common/`**:  
  모든 화면에서 공통으로 사용되는 작은 단위의 UI 컴포넌트들을 포함합니다.
  - **`Button/`**: 버튼 컴포넌트.
    - `Button.tsx`: 버튼의 동작과 이벤트를 정의하는 메인 파일.
    - `Button.styles.ts`: 스타일 관련 코드(CSS-in-JS 방식).
    - `index.ts`: 버튼을 export하여 외부에서 쉽게 접근 가능하게 함.
  - **`Input/`**: 입력 필드 관련 컴포넌트. 텍스트 박스, 체크박스 등이 포함될 수 있음.
  
- **`layout/`**:  
  페이지의 레이아웃을 구성하는 컴포넌트들.
  - **`Header/`**: 헤더 영역(로고, 네비게이션 메뉴 등).
  - **`Footer/`**: 푸터 영역(저작권, 링크 등).
  - **`Sidebar/`**: 사이드바(메뉴, 설정 등).
  
- **`feature/`**:  
  특정 기능에 종속적인 컴포넌트들.  
  - **`Auth/`**: 로그인, 회원가입과 관련된 UI.
  - **`Dashboard/`**: 대시보드와 관련된 UI.

---

### **3. `pages/`**
라우팅 구조를 담당하며, 각각의 페이지에 해당하는 컴포넌트를 포함합니다.

- **`Home/`**:  
  메인 홈 페이지. 예: 랜딩 페이지, 소개 페이지.
  
- **`Login/`**:  
  로그인 페이지. 예: 로그인 폼, 소셜 로그인 버튼.

- **`Dashboard/`**:  
  대시보드 페이지. 관리자 페이지 또는 사용자 통계를 보여주는 화면.

---

### **4. `hooks/`**
React의 **Custom Hooks**를 저장하는 폴더로, 상태 관리나 재사용 가능한 로직을 처리합니다.

- **`useAuth.ts`**:  
  인증 관련 로직을 처리하는 커스텀 훅.  
  예: 로그인 상태 확인, 사용자 정보 가져오기.
  
- **`useForm.ts`**:  
  폼 데이터를 관리하는 훅.  
  예: 입력 값 유효성 검사, 상태 업데이트.

---

### **5. `api/`**
서버와의 통신을 담당하는 함수와 설정 파일을 포함합니다.

- **`auth.ts`**:  
  인증 관련 API 요청(로그인, 로그아웃, 회원가입 등).  
  예: `POST /login`, `POST /register`.

- **`user.ts`**:  
  사용자 정보 관련 API 요청.  
  예: `GET /user/:id`, `PUT /user/:id`.

---

### **6. `utils/`**
애플리케이션 전반에서 재사용 가능한 **유틸리티 함수**를 포함합니다.

- **`format.ts`**:  
  데이터 형식 변환 함수.  
  예: 날짜 포맷팅, 통화 변환, 전화번호 포맷.

- **`validation.ts`**:  
  데이터 유효성 검사 함수.  
  예: 이메일 형식 검증, 비밀번호 강도 확인.

---

### **7. `types/`**
TypeScript에서 사용하는 **타입 정의 파일**을 포함합니다.

- **`user.ts`**:  
  사용자 관련 타입 정의.  
  예: `User`, `UserProfile`.

- **`common.ts`**:  
  공통적으로 사용되는 타입 정의.  
  예: `APIResponse`, `Error`.

---

### **8. `styles/`**
애플리케이션의 전역 스타일과 테마 설정을 포함합니다.

- **`global.ts`**:  
  전역 스타일 정의.  
  예: `body`, `html`, 공통 클래스.
  
- **`theme.ts`**:  
  테마 관련 설정.  
  예: 색상 팔레트, 폰트 크기, 간격.

---

### **9. `store/`**
상태 관리와 관련된 파일을 저장하는 폴더입니다.

- **`auth/`**:  
  인증 상태와 관련된 Redux 또는 상태 관리 파일.
  
- **`user/`**:  
  사용자 상태와 관련된 Redux 또는 상태 관리 파일.

---

`README.md` 파일에 포함할 수 있는 내용을 작성해드리겠습니다. 기본적으로 프로젝트 소개, 설치 방법, 사용법, 개발 명령어 등을 포함하는 형식으로 작성할 수 있습니다.

```markdown

## Features

- React 18
- TypeScript
- Vite for fast development and build
- Styled Components for styling
- ESLint for linting
- Axios for HTTP requests
- React Router for navigation

## Installation

To get started with the project, clone this repository and install the dependencies.

### Clone the repository

```bash
git clone https://github.com/your-username/web_template.git
cd web_template
```

### Install dependencies

If you're using Yarn as your package manager (recommended for this project), run:

```bash
yarn install
```

Or, if you're using npm:

```bash
npm install
```

## Development

After installing the dependencies, you can start the development server using the following command:

```bash
yarn dev
```

This will start the Vite development server, and you can view your application at [http://localhost:3000](http://localhost:3000).

## Build

To build the project for production, use the following command:

```bash
yarn build
```

This will compile the TypeScript files and create an optimized build in the `dist/` directory.

## Linting

To run the ESLint checker for code quality, use:

```bash
yarn lint
```

## Preview

To preview the production build locally, use the following command:

```bash
yarn preview
```

This will serve the production build on a local server.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### 설명:

- **프로젝트 소개**: 이 템플릿은 React, Vite, TypeScript 등을 사용하여 빠르고 현대적인 웹 애플리케이션을 개발할 수 있도록 설정된 기본 템플릿입니다.
- **설치 및 실행 방법**: 의존성 설치 및 개발 서버 실행 방법을 설명합니다.
- **빌드 및 배포**: 프로젝트를 빌드하고 배포하는 방법을 설명합니다.
- **폴더 구조**: 프로젝트의 디렉터리 구조를 설명하여, 각 폴더의 용도와 내용을 명확히 합니다.
- **라이센스**: 사용자가 프로젝트를 사용하는 조건을 명시합니다.
