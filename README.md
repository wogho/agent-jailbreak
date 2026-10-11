# agent-jailbreak

에이전트(Agent) 대상 프롬프트 우회(jailbreak) 텍스트 및 설정 모음.

각 모델별로 검증된 텍스트와 가이드를 폴더 단위로 보관하며, 모델 특성에 따라 파일을 통째로 복사(`copy raw file`)하거나 전역 설정 파일로 등록해서 사용한다.

## 지원 현황

| 제공사 | 모델 | 가이드 / 파일 | 상태 | 비고 |
| --- | --- | --- | --- | --- |
| DeepSeek | DeepSeek-V4.1-Flash | [`deepseek/DeepSeek-V4.1-Flash.md`](deepseek/DeepSeek-V4.1-Flash.md) | ✅ 작동 | 프롬프트 복사 후 입력 (`opencode` 및 기타 환경 미작동) |
| Google | gemini 3.6-flash | [`gemini/3.6-flash.md`](gemini/3.6-flash.md) | ✅ 작동 | **Antigravity IDE** 전용 ([`GEMINI.md`](gemini/GEMINI.md) 전역 설정 추가) |
| Google | gemini 3.1-pro | [`gemini/3.6-flash.md`](gemini/3.6-flash.md) | ✅ 작동 | **Antigravity IDE** 전용 ([`GEMINI.md`](gemini/GEMINI.md) 전역 설정 추가) |
| Google | gemini 3.8-flash | [`gemini/3.6-flash.md`](gemini/3.6-flash.md) | ⚠️ 조건부 작동 | 전역 설정 + `.txt` 파일 우회 또는 컨텍스트 워밍업 필요 |
| OpenAI | gpt6-astra | [`gpt/gpt6-astra.md`](gpt/gpt6-astra.md) | ❌ 미작동 | - |
| OpenAI | gpt5.6-sol | [`gpt/gpt5.6-sol.md`](gpt/gpt5.6-sol.md) | ❌ 미작동 | - |

> **참고**:
> - **DeepSeek 계열**: **DeepSeek-V4.1-Flash**에서 작동하며, **opencode**나 기타 외부 환경에서는 작동하지 않습니다.
> - **Gemini 계열**: **Antigravity IDE**에서 작동 확인되었으며, **Antigravity 2.0** 및 일반 웹 환경에서는 작동하지 않습니다. 자세한 설정 및 우회 방법은 [`gemini/3.6-flash.md`](gemini/3.6-flash.md)를 참고하세요.
> - **OpenAI (GPT) 계열**: 현재 미작동 상태입니다. 우회 텍스트 기여 환영합니다.

## 디렉토리 구조

```text
agent-jailbreak/
├── deepseek/
│   └── DeepSeek-V4.1-Flash.md  # DeepSeek-V4.1-Flash 프롬프트 (작동 / opencode 등 미작동)
├── gemini/
│   ├── 3.6-flash.md            # Gemini 3.1 / 3.6 / 3.8 우회 설정 가이드 (작동)
│   ├── GEMINI.md               # Antigravity 전역 설정 파일 (%USERPROFILE%\.gemini\config)
│   └── images/                 # 가이드 참고 스크린샷
├── gpt/
│   ├── gpt5.6-sol.md           # (미작동)
│   ├── gpt5.6-sol_v2.md        # (미작동)
│   └── gpt6-astra.md           # (미작동)
└── README.md
```

## 사용법

### 1. 일반 프롬프트 방식 (DeepSeek 등)
1. 대상 모델에 해당하는 `.md` 파일을 연다.
2. 내용 전체를 복사해 프롬프트 입력창에 붙여넣는다.

### 2. 전역 설정 및 파일 우회 방식 (Gemini — Antigravity IDE)
1. [`gemini/GEMINI.md`](gemini/GEMINI.md) 파일을 다운로드하여 `%USERPROFILE%\.gemini\config` 경로에 복사한다.
2. Antigravity IDE를 재시작한 후 사용한다.
3. **Gemini 3.7 / 3.8** 모델의 경우 바탕화면에 `.txt` 파일을 생성해 프롬프트를 작성한 뒤, 채팅창에서 해당 파일 경로를 읽도록 지시한다. (상세 가이드는 [`gemini/3.6-flash.md`](gemini/3.6-flash.md) 참고)

## 출처

- [yougame.biz — 1444](https://yougame.biz/forums/1444/)
- GitHub Search

## 기여

- 미작동 모델(GPT 등) 및 신규 우회 텍스트 시도·제보 환영
- 새 모델 폴더는 `<provider>/<model>.md` 형식으로 추가
- `[작동 / 미작동]` 상태가 바뀌면 이슈나 PR로 제보 (`README.md` 상태표는 검증 결과 기준으로 갱신)
