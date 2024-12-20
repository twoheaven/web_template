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

# Project Structure

This is the project directory structure, which organizes the code and assets in a maintainable way:

```
src/                      # Root source directory of the project
├── assets/               # Manages static assets (images, fonts, etc.)
│   ├── images/           # Stores image files used throughout the project
│   └── fonts/            # Stores font files used throughout the project
├── components/           # Manages reusable UI components
│   ├── common/           # Common components used across the project
│   │   ├── Button/       # Button component related files
│   │   │   ├── Button.tsx    # Button component implementation
│   │   │   ├── Button.styles.ts  # Styles for the Button component
│   │   │   └── index.ts  # Exports Button component module
│   │   └── Input/        # Input component related files
│   ├── layout/           # Layout components (Header, Footer, Sidebar, etc.)
│   │   ├── Header/       # Header component files
│   │   ├── Footer/       # Footer component files
│   │   └── Sidebar/      # Sidebar component files
│   └── feature/          # Feature-specific components
│       ├── Auth/         # Authentication-related components
│       └── Dashboard/    # Dashboard-related components
├── pages/                # Page-level components
│   ├── Home/             # Home page components
│   ├── Login/            # Login page components
│   └── Dashboard/        # Dashboard page components
├── hooks/                # Custom React hooks
│   ├── useAuth.ts        # Custom hook for authentication logic
│   └── useForm.ts        # Custom hook for form handling
├── apis/                 # API communication logic
│   ├── authApi.ts        # Functions for authentication-related APIs
│   └── userApi.ts        # Functions for user-related APIs
├── utils/                # Utility functions
│   ├── format.ts         # Utility functions for data formatting
│   ├── validation.ts     # Utility functions for input validation
│   └── paths.ts          # Enum for React Router paths management
├── types/                # TypeScript types definitions
│   ├── user.ts           # User-related types
│   └── common.ts         # Commonly used types
├── styles/               # Styling-related files
│   ├── global.ts         # Global style definitions
│   └── theme.ts          # Project's theme settings
└── store/                # State management files
    ├── auth/             # Authentication-related state management
    └── user/             # User-related state management

package.json             # Project configuration
tsconfig.json            # TypeScript configuration
vite.config.ts           # Vite configuration
eslint.config.js         # ESLint configuration
index.html               # Main HTML file for React mounting with `div#root`
```

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

markdown

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
