# KETI & NXP S32G - AI 웹 컨트롤 센터

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/kimhyunwoo/terminal4)
[![Web Serial API](https://img.shields.io/badge/Web%20Serial%20API-Supported-blue?style=for-the-badge&logo=googlechrome)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Serial_API)
[![made with-HTML, CSS, JS](https://img.shields.io/badge/made%20with-HTML%2C%20CSS%2C%20JS-orange?style=for-the-badge)](https://developer.mozilla.org/)
[![AI Powered](https://img.shields.io/badge/AI%20Powered-Gemini%20%26%20Mistral-8a63d2?style=for-the-badge)](https://ai.google.dev/)

<br>

[![Live Demo](https://img.shields.io/badge/Live_Demo-►_Try_it_Now!-brightgreen?style=for-the-badge&logo=github-pages)](https://hwkim3330.github.io/web/)

<br>

NXP S32G GoldVIP 보드를 위한 올인원(All-in-One) 웹 기반 컨트롤 센터입니다. 임베디드 개발자, 테스트 엔지니어, 그리고 학생들을 위해 설계되었으며, 단일 `index.html` 파일만으로 시리얼 터미널, 원클릭 GUI, AI 기반 명령어 생성 및 파일 업로드 기능을 제공하여 임베디드 시스템 개발 및 테스트 생산성을 극대화합니다.

![Application Screenshot](https://github.com/user-attachments/assets/eaa36443-81b3-41ab-995a-faea06c5f5af)

---

## ✨ 주요 기능 (Key Features)

*   **🌐 웹 기반 터미널**: `Xterm.js`를 내장하여 별도 프로그램 설치 없이 브라우저에서 바로 시리얼 포트에 연결하고 상호작용할 수 있습니다.
*   **🤖 AI 어시스턴트**:
    *   **명령어 생성**: 자연어(예: "eth0의 TSN 트래픽 보여줘")를 입력하면 Gemini 또는 Mistral AI가 실행 가능한 쉘 명령어를 생성합니다.
    *   **명령어 설명**: 마지막으로 실행한 복잡한 명령어의 기능과 옵션을 AI가 알기 쉽게 설명해 줍니다.
*   **🖱️ 원클릭 명령어 GUI**:
    *   TSN, 가상화(Virsh), 컨테이너(Docker), 네트워크 등 복잡하고 긴 명령어들을 버튼 클릭 한 번으로 실행할 수 있습니다.
    *   `ls`, `pwd`, `ps`, `dmesg` 등 기본적인 리눅스 명령어도 버튼으로 제공하여 빠른 시스템 상태 확인이 가능합니다.
*   **📝 코드 & 스크립트 실행기**:
    *   웹 UI에 C 또는 Python 코드를 직접 작성하면, 디바이스에서 즉시 컴파일/실행하고 결과를 터미널에서 확인할 수 있습니다.
*   **📂 파일 업로드**:
    *   로컬 PC의 텍스트 파일(스크립트, 설정 파일 등)을 S32G 보드의 원하는 경로로 손쉽게 업로드할 수 있습니다.
*   **🔌 제로 설치 및 최고의 이식성**:
    *   모든 기능이 단일 HTML 파일에 포함되어 있어, 라이브 데모 링크를 클릭하거나 파일을 다운로드하여 브라우저에서 열기만 하면 바로 사용할 수 있습니다.

---

## 🚀 시작하기 (Getting Started)

### 1. 퀵 스타트 (Live Demo)
가장 빠른 방법입니다.

1.  **[Live Demo 바로가기](https://hwkim3330.github.io/web/)**를 클릭하세요.
2.  NXP S32G 보드를 PC에 USB 시리얼 케이블로 연결합니다.
3.  웹페이지 좌측 상단의 **`🔌 Connect`** 버튼을 클릭하고, 팝업 창에서 S32G 보드에 해당하는 시리얼 포트를 선택 후 연결합니다.

### 2. 로컬에서 실행하기
오프라인 환경에서 사용하거나 코드를 수정하고 싶을 때 사용합니다.

1.  이 저장소에서 `index.html` 파일을 다운로드합니다.
2.  다운로드한 `index.html` 파일을 최신 웹 브라우저(Chrome, Edge 권장)에서 엽니다.
3.  위 퀵 스타트 2~3단계를 진행합니다.

### 3. (선택) AI 기능 활성화
AI 기반 명령어 생성/설명 기능을 사용하려면 API 키가 필요합니다.
*   우측 상단의 **`🔑 API Keys`** 버튼을 눌러 Google Gemini 또는 Mistral API 키를 입력하고 저장합니다.
*   *참고: API 키는 외부로 전송되지 않으며, 사용자의 브라우저 내 로컬 스토리지에만 안전하게 저장됩니다.*

---

## 💡 동작 원리 (How it Works)
이 애플리케이션은 **Web Serial API**라는 최신 웹 기술을 핵심으로 사용합니다. 사용자의 모든 동작은 브라우저 내에서 직접 하드웨어와 통신하는 방식으로 이루어집니다.

`사용자 액션 (브라우저)` ➡️ `Web Serial API` ➡️ `S32G 보드 (USB)` ➡️ `쉘 명령어 실행` ➡️ `실행 결과 반환` ➡️ `Web Serial API` ➡️ `웹 터미널 출력 (브라우저)`

---

## 🖥️ 브라우저 요구사항 및 호환성 (Browser Requirements)

이 애플리케이션은 **Web Serial API**를 사용하며, 모든 브라우저에서 기본으로 지원되지는 않습니다.

*   ✅ **권장 브라우저**: **Chrome**, **Edge**, **Opera** (Windows, macOS, Linux, Android)
*   ⚠️ **Firefox**: 기본적으로 비활성화되어 있습니다. 사용하려면 다음 단계를 따르세요.
    1.  주소창에 `about:config`를 입력합니다.
    2.  `dom.webserial.enabled`를 검색합니다.
    3.  값을 `true`로 변경합니다.
*   🐧 **Linux 사용자**: 시리얼 포트 접근 시 `permission denied` 오류가 발생할 수 있습니다. 터미널에서 아래 명령어를 실행하여 현재 사용자를 `dialout` 그룹에 추가한 후, 로그아웃했다가 다시 로그인하세요.
    ```bash
    sudo usermod -a -G dialout $USER
    ```

---

## 🛠️ 기술 스택 (Tech Stack)

*   **Frontend**: HTML5, CSS3, Vanilla JavaScript (No frameworks)
*   **Terminal Emulator**: [Xterm.js](https://xtermjs.org/)
*   **Core API**: [Web Serial API](https://wicg.github.io/serial/)
*   **AI Integration**: [Google Gemini API](https://ai.google.dev/), [Mistral AI API](https://mistral.ai/)

---

## 📄 라이선스 (License)

이 프로젝트는 [MIT 라이선스](LICENSE)에 따라 배포됩니다.
