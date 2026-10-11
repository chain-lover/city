# 도시의 한 사람으로 태어나 — 개인용 편집 팩

## 들어 있는 파일
- `index.html`: 개인용 게임 시작 파일
- `assets/index-f1noWqaE.js`: 사용자가 제공한 배포용 JavaScript 번들에 사용자 이벤트 배열 연결 코드를 추가한 파일
- `assets/index-DhyEZMPO.css`: 사용자가 제공한 CSS
- `editor.html`: 이벤트/선택지 편집기
- `custom-events.js`: 게임이 읽는 사용자 이벤트 파일(처음에는 빈 배열)
- `custom-events.example.json`: 예시 이벤트 데이터

## 아주 간단한 사용법
1. ZIP 압축을 푸세요.
2. `editor.html`을 Chrome에서 여세요.
3. 이벤트와 선택지를 수정하세요.
4. **게임용 파일 내보내기**를 눌러 `custom-events.js`를 받으세요.
5. 받은 `custom-events.js`를 이 폴더의 기존 `custom-events.js`에 덮어쓰세요.
6. 로컬 웹 서버로 폴더를 실행한 뒤 `index.html`을 여세요.

## 로컬 서버 실행 (Windows)
이 폴더 안에서 주소창이 아닌 파일 탐색기 주소창에 `cmd`를 입력해 명령 프롬프트를 열고 다음을 실행하세요:

```bat
py -m http.server 8000
```

그다음 Chrome에서 `http://localhost:8000`을 여세요. Python이 없다면 VS Code의 Live Server 같은 로컬 서버 확장을 사용하세요.

## 지원하는 데이터
- 이벤트: `id`, `age`, `weight`, `chance`, `text`, `regions`, `requires`, `forbids`, `jobs`, `cooldown`, `choices`
- 선택지: `label`, `text`, `effects`, `flagsAdd`, `flagsRemove`
- 능력치 키: `health`, `sanity`, `wealth`, `network`, `rep`

## 알아둘 점
- 이벤트 ID는 원본 이벤트 ID와 중복되면 안 됩니다. 편집기는 사용자 이벤트 사이의 중복을 검사하지만 원본 게임 이벤트와의 충돌을 완전히 검사하지는 못합니다. `custom_` 접두사를 권장합니다.
- 원본 JS/CSS는 사용자가 제공한 배포 파일을 바탕으로 했습니다. JS는 `window.CUSTOM_EVENTS` 배열을 원본 이벤트 배열에 합치도록 수정했습니다.
- 이 팩은 **사용자 이벤트를 추가**하는 초기 버전입니다. 기존 이벤트 편집/삭제, 새로운 게임 메커니즘 추가, 원본 코드 복원 기능은 포함하지 않습니다.
- 원본 사이트의 서버/배포 기능을 복제하지 않으며, 브라우저에서만 처리되는 로컬 복사본입니다.
- `file://`로 직접 여는 대신 로컬 웹 서버를 사용하세요.
- 원본 파일은 백업해 두고 개인용으로만 사용하세요.
