# UV코팅판 2편 작업기록

- 기록 상태: 최종 산출물 정리 기록 (Git 작업 없음)
- 최종 전체본: `public/previews/final/uv-coating-episode2-full-final.mp4`
- 최종 길이: 34.944초
- 화면 규격: 1080×1920, 9:16

## Scene별 최종 채택 파일

| Scene | 최종 파일 | 길이 | 주요 자산 |
|---|---|---:|---|
| Scene1 | `public/previews/final/scene01-final.mp4` | 5.184초 | `episode2-scene01-veo-v3.mp4`, 분리 생성·0.18초 결합 TTS |
| Scene2 | `public/previews/final/scene02-final.mp4` | 2.048초 | `episode2-scene02-startframe-v1.png`, 정지 이미지 |
| Scene3 | `public/previews/final/scene03-final.mp4` | 6.528초 | `episode2-scene03-veo-v2.mp4`, SSML break 350ms TTS, 마지막 프레임 freeze |
| Scene4 | `public/previews/final/scene04-final.mp4` | 4.544초 | `episode2-scene04-veo-v1.mp4` |
| Scene5 | `public/previews/final/scene05-final.mp4` | 6.059초 | Scene5 Veo 안정 구간 채택, 마지막 프레임 freeze |
| Scene6 | `public/previews/final/scene06-final.mp4` | 5.184초 | `episode2-scene06-veo-v1.mp4`, 자막 `새로 생긴 면입니다` 최종 반영 |
| Scene7 | `public/previews/final/scene07-final.mp4` | 5.717초 | `scene07-daesan-ending-final.mp4`, 1편 최종본에서 추출한 엔딩 음성 별도 연결 |

## 주요 시행착오와 개선

### 이미지·Veo

- 판재가 유리처럼 보이거나 실제보다 두껍게 생성된 시도가 있어, 밝은 우드톤의 불투명 패널과 6~18mm 두께를 반복 명시했다.
- 절단면이 정면에서 보이지 않는 문제는 판재를 30~40도 회전해 코팅된 넓은 면과 무광 절단면이 동시에 보이도록 개선했다.
- 과장된 별 모양 광택은 제거하고 부드러운 대각선 하이라이트만 남겼다.
- 드릴홀이 스피커 우퍼처럼 커지는 문제는 판재 폭의 5% 이하, 1개, 옅은 원목 내부 톤으로 제한했다.
- Veo에서 레터박스, 입·눈 왜곡, 후반 손·얼굴 변형이 발생했다. 9:16 출력 명시, 고정 카메라, 얼굴 특징 고정 프롬프트를 적용하고 불안정한 후반부는 트림·freeze 처리했다.

### TTS·오디오

- 쉼표만으로 의미 단위가 붙거나 SSML 구간에서 필러음이 생기는 문제가 있어 Scene1·6은 두 발화로 나눠 생성한 뒤 0.18초 무음으로 결합했다.
- Scene3는 속도를 높여 4초 영상에 맞추는 방식이 부자연스러워 speakingRate 1.00으로 복원하고, 영상 종료 후 마지막 프레임을 freeze하는 방식으로 전환했다.
- Scene3의 문장 끝 질문조·상승 억양과 여러 대사 후보를 검토했다. 최종 대사는 `원래 UV코팅된 표면과 달리, 절단면은 원재료가 노출됩니다.`이며 쉼표 위치에 SSML break 350ms를 적용했다.
- Scene7 원본 영상에는 음성 트랙이 없어, `uv-coating-episode1-full-final.mp4`의 엔딩 구간에서 실제 확정 음성을 추출해 Remotion `Audio` 트랙으로 명시 연결했다.

## 커버 후보

- `public/covers/episode2-cover-a-v1.png`
- `public/covers/episode2-cover-b-v1.png`
- 규격: 1080×1920 PNG
- 제작 방식: Vertex AI `gemini-2.5-flash-image`가 제품·캐릭터·환경 비주얼을 생성하고, Codex/Remotion이 한글 타이포그래피와 승인 브랜드 로고를 후처리했다.
- 주제: UV코팅판의 광택 표면과 무광 절단면 차이
- 디자인: MAIN Notion / SECONDARY Apple
