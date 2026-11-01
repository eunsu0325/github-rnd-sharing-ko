# GitHub 연구개발 공유 파트너 · 한국어 Codex 스킬

**연구개발 결과를 GitHub에 정리해 올리고, 팀원이 내려받아 실행하며, 이후 함께 수정할 수 있도록 돕는 스킬입니다.**

게시·관리: [eunsu0325](https://github.com/eunsu0325) · 스킬 이름: `github-rnd-sharing-ko`

Git 명령을 미리 완성할 필요 없이 “팀원이 받아서 돌릴 수 있게 정리해줘”라고 시작할 수 있습니다. AI가 실제 코드·문서·환경을 확인해 공유 자료를 작성하고 요청된 범위의 검증·게시를 수행하도록 안내합니다. Physical AI뿐 아니라 다른 연구·개발 저장소에도 사용할 수 있습니다.

## 빠른 설치와 사용

Codex에서 다음 메시지를 입력합니다.

```text
$skill-installer
https://github.com/eunsu0325/github-rnd-sharing-ko/tree/main/skills/github-rnd-sharing-ko
이 경로의 스킬을 설치해줘.
```

설치 후 다음 메시지부터 다음처럼 사용합니다.

```text
$github-rnd-sharing-ko
이 프로젝트를 팀원이 내려받아 실행할 수 있게 정리해줘.
실제 코드와 명령을 확인해서 README와 필요한 안내를 작성하고
가능한 최소 실행까지 확인해줘. 오늘은 게시 전 준비까지만 해줘.
```

GitHub에 올라가 있거나 clone한 상태와 Codex에 설치된 상태는 별개입니다. 팀원도 자신의 환경에 한 번 설치해야 합니다. 설치 목록에 보이지 않으면 위치·중첩 폴더·비활성화 여부를 확인하고 Codex를 다시 시작하세요.

## 무엇을 도와주나요?

| 상황 | 수행 방향 |
|---|---|
| 연구 코드를 처음 게시 | 실제 저장소·원격·이력 확인, 공유 파일 선별, 문서 준비와 요청된 게시 |
| README 작성·갱신 | 목적, 현재 기능, 환경, 실제 명령, 정상 출력, 한계를 연결 |
| 팀원의 첫 실행 | 코드·모델·데이터 취득, 설정·배치, 최소 실행과 성공 기준 안내 |
| 변경 검토·협업 | 기존 기여 규칙과 PR 양식에 맞춰 branch/fork·PR·리뷰 흐름 구성 |
| 기존 clone 갱신 | 미커밋 작업 보존, 원격 조회와 실제 통합을 구분 |
| 큰 자산 공유 | 일반 Git/LFS/Release/외부 저장소의 적합성과 버전·접근 조건 검토 |

준비 요청을 외부 게시로 확대하지 않으며, 이미 승인된 게시를 불필요하게 다시 승인받지 않도록 했습니다. 기존 연구 변경·이력을 보존하고 새 공개 범위·라이선스·초대·CI 설정을 임의로 정하지 않습니다.

## README는 어떻게 작성하나요?

팀원이 프로젝트를 판단하고 첫 실행까지 갈 수 있는 흐름을 만듭니다.

1. 개발 목적과 현재 사용할 수 있는 기능.
2. 기준 버전, 실제 검증 환경과 중요한 제한.
3. 코드와 모델·데이터의 취득·배치 방법.
4. 가장 작은 실행의 선행 조건과 정확한 명령.
5. 실제 확인한 정상 출력·생성 파일·값과 확인 방법.
6. 상세 사용·기여·도움·출처 문서로 이어지는 경로.

실제 코드에 없는 CLI·다운로드 주소·성능을 만들지 않습니다. 지원 조건과 실제 시험한 환경, 의사코드와 실행 가능한 예제를 구분합니다. 문서 크기와 저장소 관례에 맞춰 구성하며 고정 목차나 문서 묶음을 강제하지 않습니다. [README 작성 지침](skills/github-rnd-sharing-ko/references/readme-writing.md)

## 요청 예시

```text
$github-rnd-sharing-ko
README의 실행 명령이 실제 코드와 맞는지 확인해서 수정해줘.
회사 GPU 서버 실행과 결과 회수 방법을 설명하고 미확인 조건을 남겨줘.
```

```text
$github-rnd-sharing-ko
eunsu0325 계정에 이 프로젝트 전용 저장소를 새로 만들어 올려줘.
README·설치 안내·검증 범위를 정리하고 게시된 내용을 확인해줘.
```

```text
$github-rnd-sharing-ko
지정한 기존 저장소에 이 변경을 올리고 PR을 만들어줘.
기여 규칙과 PR 양식을 읽고 문제·달라진 행동·실제 검증·남은 조건을 적어줘.
```

## 수동 설치·업데이트

스킬 자체는 텍스트 지침과 참고문서여서 GPU·ROS·모델 가중치가 필요하지 않습니다. 실제 프로젝트 실행 환경과 권한은 별도로 확인합니다.

Git과 POSIX 셸이 있는 macOS/Linux의 개인 수동 설치 예시입니다.

```bash
git clone https://github.com/eunsu0325/github-rnd-sharing-ko.git
cd github-rnd-sharing-ko
mkdir -p "$HOME/.agents/skills"
if [ -e "$HOME/.agents/skills/github-rnd-sharing-ko" ]; then
  echo "기존 설치 위치와 개인 수정을 확인한 뒤 업데이트하세요."
else
  cp -R skills/github-rnd-sharing-ko "$HOME/.agents/skills/"
fi
```

내장 설치기는 환경에 따라 `~/.codex/skills` 등을 사용할 수 있습니다. 기존 위치를 먼저 확인해 중복 설치를 피하세요. 프로젝트 전용 설치는 `.agents/skills/github-rnd-sharing-ko/` 아래에 폴더 전체를 둡니다. `SKILL.md`만 복사하면 참고문서가 빠집니다. [Codex 공식 문서](https://learn.chatgpt.com/docs/build-skills)

이미 clone한 소스는 현재 branch·추적 관계·미커밋 변경을 확인한 뒤 갱신합니다. 깨끗한 tracking branch가 뒤처지기만 했다면 `git pull --ff-only`를 사용할 수 있습니다. 분기·충돌이 있으면 상태에 맞게 처리해야 합니다. 소스를 갱신해도 별도로 복사한 설치 사본은 자동 갱신되지 않으므로 기존 위치와 개인 수정을 확인한 뒤 전체 스킬의 업데이트를 요청하세요.

Windows에서는 같은 폴더 구조를 사용하되 위 POSIX 명령을 PowerShell에서 그대로 실행하는 방법은 검증하지 않았습니다.

## 구성

```text
github-rnd-sharing-ko/
├── README.md
└── skills/github-rnd-sharing-ko/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── readme-writing.md
        ├── publishing-and-assets.md
        ├── clone-and-verification.md
        ├── team-collaboration.md
        └── sources-and-adoption.md
```

| 문서 | 역할 |
|---|---|
| [SKILL.md](skills/github-rnd-sharing-ko/SKILL.md) | 적용 상황과 공통 수행 기준 |
| [README 작성](skills/github-rnd-sharing-ko/references/readme-writing.md) | 독자 흐름·명령·정상 출력·문서 역할 |
| [게시·자산](skills/github-rnd-sharing-ko/references/publishing-and-assets.md) | Git 이력·파일 선별·대형 자산·라이선스 |
| [clone·검증](skills/github-rnd-sharing-ko/references/clone-and-verification.md) | 자산·권한·환경·실행 근거 구분 |
| [팀 협업](skills/github-rnd-sharing-ko/references/team-collaboration.md) | branch/fork·issue/PR·리뷰·동기화 |
| [근거·채택 판단](skills/github-rnd-sharing-ko/references/sources-and-adoption.md) | 공식 문서·공개 스킬·실제 프로젝트 사례 |

공통 판단은 본문에 두고 참고문서는 작업에 필요한 것만 읽도록 구성했습니다. 다른 스킬은 필수 의존성이 아닙니다.

## 근거와 검증 범위

Git/GitHub 공식 문서, Google 변경 검토 지침, 문서 작성 방법과 LeRobot·mjlab의 실제 문서·PR을 참고했습니다. GitHub가 소개하는 커뮤니티 스킬 5개와 관련 템플릿 21개, OpenAI의 GitHub 작업용 스킬 3개도 검토해 수용·수정·제외 이유를 기록했습니다. 외부 원문을 패키지에 복제하지 않았습니다.

GitHub Skills 교육, 커뮤니티 Agent Skills, OpenAI의 공개 스킬은 작성 주체와 용도가 다릅니다. 이 저장소는 개인 작성 스킬이며 GitHub·OpenAI의 공식 제품이나 인증을 뜻하지 않습니다.

형식·내부 참조 검사, 임시 코드의 README 작성·예제 실행, 서로 다른 PR 관례 두 가지에 대한 적용을 확인했습니다. 스킬 없는 비교 사례도 작업을 수행했으므로 생산성 향상이나 실패 교정 효과를 검증했다고 주장하지 않습니다. 실제 연구 프로젝트의 GPU·SIM·실물 검증은 별도입니다.

## 관련 스킬·기여

연구 설계·구현·실험·유지보수는 별도 [Physical AI R&D Partner](https://github.com/eunsu0325/Physical-AI_R-D_Partner_skill)에서 관리합니다. 이 저장소는 GitHub 공유 스킬 전용입니다.

수정은 구체적인 사용 사례·누락을 근거로 제안하고, 바뀐 행동과 실제 확인한 범위를 설명해 주세요. 관련 링크·메타데이터·README를 함께 확인하되 비공개 코드·로그·계정 정보는 공통 지침에 넣지 마세요.

## 라이선스

현재 별도의 `LICENSE`는 지정하지 않았습니다. 인용된 연구·문서·스킬의 권리는 원저작자에게 있으며 외부 자료의 라이선스가 이 스킬이나 사용자 연구 자산에 자동 적용되지 않습니다.
