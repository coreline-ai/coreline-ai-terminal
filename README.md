# Coreline AI 터미널

<img width="800" height="461" alt="스크린샷 2026-02-02 오후 10 57 41" src="https://github.com/user-attachments/assets/1a1a9286-1360-47c9-bc50-5203729afc65" />

> Electron, React, TypeScript로 구축된 현대적인 AI 통합 터미널 에뮬레이터입니다.
> 내장된 GLM-4 챗 어시스턴트, 파일 탐색기, 그리고 스킬 통합 기능을 제공합니다.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Electron](https://img.shields.io/badge/Electron-39.0-blueviolet)
![React](https://img.shields.io/badge/React-19.0-61dafb)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-blue)
![Vite](https://img.shields.io/badge/Vite-7.2-646cff)

## ✨ 주요 기능

- **🖥️ 커스텀 터미널**: `xterm.js`와 `node-pty` 기반으로 강력한 터미널 경험을 제공합니다.
- **🤖 GLM AI 어시스턴트**: **GLM-4-plus** (Zhipu AI) 기반의 내장 챗 패널로 코딩 도움을 받을 수 있습니다.
- **📂 사이드바 파일 탐색기**: 현재 작업 디렉토리를 위한 VS Code 스타일의 파일 내비게이션을 제공합니다.
- **⚡ 빠르고 현대적**: Vite와 React로 구동되어 높은 성능을 자랑합니다.
- **🎨 세련된 UI**: 다크 테마, 일관된 패딩, 현대적인 미적 감각을 적용했습니다.

## 🛠️ 기술 스택

- **프레임워크**: [Electron](https://www.electronjs.org/)
- **프론트엔드**: [React](https://react.dev/), [TypeScript](https://www.typescriptlang.org/)
- **번들러**: [Vite](https://vitejs.dev/) (`electron-vite` 사용)
- **터미널**: [xterm.js](https://xtermjs.org/), [node-pty](https://github.com/microsoft/node-pty)
- **AI 통합**: Zhipu GLM-4 API

## 📦 설치 및 실행

1. **저장소 복제 (Clone)**
   ```bash
   git clone https://github.com/yourusername/coreline-ai-terminal.git
   cd coreline-ai-terminal/coreline_terminal
   ```

2. **의존성 설치**
   ```bash
   npm install
   ```

3. **환경 변수 설정**
   `coreline_terminal` 루트 경로에 `.env` 파일을 생성하세요:
   ```env
   ZHIPU_API_KEY=your_api_key_here
   GLM_MODEL=GLM-4.5
   GLM_BASE_URL=https://api.z.ai/api/coding/paas/v4
   ```

4. **애플리케이션 실행**
   ```bash
   npm run dev
   ```

## 🏗️ 프로젝트 구조

```
coreline_terminal/
├── src/
│   ├── main/                 # Electron 메인 프로세스
│   │   ├── index.ts          # 메인 진입점, IPC 핸들러 (파일, GLM)
│   │   └── glm-api.ts        # GLM API 로직
│   ├── preload/              # 프리로드 스크립트
│   │   └── index.ts          # 렌더러에 API 노출 (readDir, glmChat)
│   └── renderer/             # React 프론트엔드
│       ├── src/
│       │   ├── components/
│       │   │   ├── Terminal.tsx      # xterm.js 래퍼
│       │   │   ├── FileTree.tsx      # 사이드바 파일 탐색기
│       │   │   └── ChatPanelContent.tsx # AI 챗 인터페이스
│       │   ├── App.tsx               # 메인 레이아웃 & 라우팅
│       │   └── assets/main.css       # 전역 스타일
│       └── index.html
├── package.json
└── electron.vite.config.ts
```

## 🚀 사용법

- **터미널**: 일반적인 쉘(zsh/bash)처럼 사용하세요. 표준 명령어를 지원합니다.
- **파일 탐색기**: 사이드바의 폴더를 클릭하여 펼치거나 접을 수 있습니다.
- **AI 챗**: 오른쪽의 챗 토글 버튼을 클릭하여 GLM 챗 패널을 엽니다. 코딩 관련 질문을 해보세요!
- **슬래시 명령어**: 터미널 입력창에 `/`를 입력하여 사용 가능한 명령어(예: `/review`, `/test`)를 확인하세요.

## 🤝 기여하기

기여는 언제나 환영합니다! 이슈를 등록하거나 풀 리퀘스트(PR)를 제출해주세요.

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다.
