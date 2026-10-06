# agent-jailbreak

에이전트(Agent) 대상 프롬프트 우회(jailbreak) 텍스트 모음.

각 모델별로 검증된 텍스트를 폴더 단위로 보관하며, 파일을 통째로 복사(`copy row file`)해서 사용한다.

## 지원 현황

| 제공사 | 모델 | 파일 | 상태 |
| --- | --- | --- | --- |
| DeepSeek | v4-pro | [`deepseek/only V4-pro.md`](deepseek/only%20V4-pro.md) | ✅ 작동 |
| OpenAI | gpt6-astra | [`gpt/gpt6-astra.md`](gpt/gpt6-astra.md) | ✅ 작동 |
| OpenAI | gpt5.6-sol | [`gpt/gpt5.6-sol.md`](gpt/gpt5.6-sol.md) | ❌ 미작동 |
| Google | gemini 3.6-flash | [`gemini/3.6-flash.md`](gemini/3.6-flash.md) | ❌ 미작동 |
| Google | gemini 3.6-flash (v2) | [`gemini/3.6-flash_2.md`](gemini/3.6-flash_2.md) | ❌ 미작동 |
| Google | gemini 3.8-flash | [`gemini/3.8-flash.md`](gemini/3.8-flash.md) | ❌ 미작동 |
| Google | gemini 3.8-flash (v2) | [`gemini/3.8-flash_2.md`](gemini/3.8-flash_2.md) | ❌ 미작동 |

> Gemini 전 모델은 현재 미작동 상태. 우회 텍스트 기여 환영.

## 디렉토리 구조

```
agent-jailbreak/
├── deepseek/
│   └── only V4-pro.md      # DeepSeek v4-pro (작동)
├── gpt/
│   └── gpt5.6-sol.md       # GPT 5.6 Sol (작동)
├── gemini/                 # 전부 미작동
│   ├── 3.6-flash.md
│   ├── 3.6-flash_2.md
│   ├── 3.8-flash.md
│   └── 3.8-flash_2.md
└── README.md
```

## 사용법

1. 대상 모델에 해당하는 `.md` 파일을 연다.
2. 내용 전체를 복사해 프롬프트 입력창에 붙여넣는다.
3. `[작동 / 미작동]` 상태가 바뀌면 이슈나 PR로 알려주면 된다.

## 출처

- [yougame.biz — 1444](https://yougame.biz/forums/1444/)
- GitHub Search

## 기여

- Gemini 우회 텍스트 시도·제보 환영
- 새 모델 폴더는 `<provider>/<model>.md` 형식으로 추가
- 상태표(`README.md`)는 검증 결과 기준으로 갱신
