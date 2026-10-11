# 원본 이벤트 코드 분석 메모

원본 배포 JavaScript에는 이벤트 데이터가 JSON 파일이 아니라 JavaScript 배열/객체 형태로 포함되어 있습니다. 코드에서 다음 구조를 확인했습니다.

- 이벤트 필드 예: `id`, `age`, `ageEvery`, `regions`, `notRegions`, `repeat`, `cooldown`, `weight`, `chance`, `text`, `choices`, `outcomes`
- 선택지/결과 필드 예: `label`, `text`, `effects`, `flagsAdd`, `flagsRemove`
- 이벤트 필터 함수: `Br(e, t, o)`
- 이벤트 가중치/확률 처리 함수: `Ay(e, t, o, n)`
- 연도별 이벤트 구성 함수: `Hd(n, e)`
- 선택 결과 적용 함수: `Tt(e, t, o, n, r={})`
- 이벤트 데이터 묶음을 검사하고 정리하는 함수: `Qw(...)`

`Qw(...)`는 이벤트 ID 중복을 검사합니다. 사용자 이벤트에는 원본과 겹치지 않는 고유 ID(예: `custom_my_event_001`)를 사용해야 합니다.

현재 이 저장소에는 원본 이벤트를 수정하는 UI는 포함되어 있지 않습니다. 원본 이벤트는 번들에서 분석/추출할 수 있지만, 각 언어별 텍스트와 내부 조건을 안전하게 편집하려면 먼저 배열별 데이터 구조를 추출해 검증하는 별도 작업이 필요합니다.
