# 근거와 외부 스킬의 채택 판단

검토: 2026-11-01. 아래는 실제 읽은 자료에 근거한 설계 판단이다. 자료의 관례는 모든 저장소의 의무가 아니다. 원문이나 템플릿을 복제하지 않고 한국어 지침을 독자적으로 작성했다. 링크된 연구 프로젝트의 설치/실행/CI/실물 결과를 이번 검토에서 독립 재현한 것은 아니다.

## GitHub가 소개하는 스킬

[GitHub Agent Skills 문서](https://docs.github.com/en/copilot/concepts/customizations/agent-skills)는 형식·선택적 로딩·제품별 위치를 설명하고 awesome-copilot을 community-created collection으로 소개한다. [GitHub Skills 교육](https://learn.github.com/skills)은 사람이 Issues/Actions에서 GitHub를 익히는 과정이며 개인 Agent Skill이 아니다.

`github/awesome-copilot`은 GitHub 조직 아래 있지만 개별 스킬의 작성·검증·품질을 일괄 보증하지 않는다. 검토 commit은 `5269f7ea2d6c3a9bfda5ed878b6726cf509121fd`. 다섯 SKILL.md와 repo-standardizer의 21개 template을 읽었다.

| 자료 | 채택한 점 / 그대로 적용하지 않은 점 |
|---|---|
| [create-readme](https://github.com/github/awesome-copilot/blob/5269f7ea2d6c3a9bfda5ed878b6726cf509121fd/skills/create-readme/SKILL.md) | 간결한 시작·상세 링크. LICENSE/CONTRIBUTING 섹션을 항상 배제하는 규칙은 채택하지 않음 |
| [readme-blueprint-generator](https://github.com/github/awesome-copilot/blob/5269f7ea2d6c3a9bfda5ed878b6726cf509121fd/skills/readme-blueprint-generator/SKILL.md) | 기존 문서 연결. Copilot 전용 문서 구조 존재를 전제하지 않고 실제 코드·실행 근거를 확인 |
| [documentation-writer](https://github.com/github/awesome-copilot/blob/5269f7ea2d6c3a9bfda5ed878b6726cf509121fd/skills/documentation-writer/SKILL.md) | 독자와 문서 역할 구분. 모든 초안의 반복 질문·목차 승인은 강제하지 않음 |
| [git-commit](https://github.com/github/awesome-copilot/blob/5269f7ea2d6c3a9bfda5ed878b6726cf509121fd/skills/git-commit/SKILL.md) | 실제 diff와 논리 단위 staging. README 준비를 commit/push 허가로 확대하지 않음; 도구/버전 가정을 별도 확인 |
| [repo-standardizer](https://github.com/github/awesome-copilot/blob/5269f7ea2d6c3a9bfda5ed878b6726cf509121fd/skills/repo-standardizer/SKILL.md) | 기존 상태 보존·결과 재조회. labels/CI/rulesets/CODEOWNERS/운영 약속의 일괄 변경은 제외 |

해당 원문을 향후 복사·수정 배포한다면 [MIT 고지](https://github.com/github/awesome-copilot/blob/5269f7ea2d6c3a9bfda5ed878b6726cf509121fd/LICENSE)를 보존하고 외부 유래 자산 조건도 확인한다. 이 모음의 라이선스가 사용자의 연구 자산까지 정하지 않는다. Copilot의 allowed-tools·설치 경로·CLI 표기를 Codex에서 그대로 가정하지 않는다.

## OpenAI의 GitHub 작업용 스킬

GitHub 제작물과 별도로 `openai/skills`의 공식 공개 스킬 본문 3개를 commit `49f948faa9258a0c61caceaf225e179651397431`에서 읽었다. [gh-address-comments](https://github.com/openai/skills/blob/49f948faa9258a0c61caceaf225e179651397431/skills/.curated/gh-address-comments/SKILL.md)는 PR 리뷰 대응, [gh-fix-ci](https://github.com/openai/skills/blob/49f948faa9258a0c61caceaf225e179651397431/skills/.curated/gh-fix-ci/SKILL.md)는 Actions 실패 진단, [yeet](https://github.com/openai/skills/blob/49f948faa9258a0c61caceaf225e179651397431/skills/.curated/yeet/SKILL.md)는 명시적인 commit/push/PR 일괄 요청에 특화돼 있다. README·연구 자산·팀원 재현을 묶은 완제품과는 범위가 다르다.

기존 PR/검토 상태 보존과 최종 diff에 맞춘 설명은 참고했다. 전체 파일 staging, 누락 의존성 자동 설치, 고정 master pull 같은 조건 가정은 복사하지 않았다. 번들 스크립트 구현·실행을 검증한 것은 아니며 이 스킬들을 설치하거나 자동 의존성으로 두지 않았다.

## 실제 로봇 AI 프로젝트

LeRobot `3f797de5952432284a7c77ad2760218cb74e2f26`: [README](https://github.com/huggingface/lerobot/blob/3f797de5952432284a7c77ad2760218cb74e2f26/README.md), [CONTRIBUTING](https://github.com/huggingface/lerobot/blob/3f797de5952432284a7c77ad2760218cb74e2f26/CONTRIBUTING.md), [PR template](https://github.com/huggingface/lerobot/blob/3f797de5952432284a7c77ad2760218cb74e2f26/.github/PULL_REQUEST_TEMPLATE.md), 설치·AGENTS 등 본문을 읽었다. 간단한 시작과 모델/로봇/기여 환경을 분리한다. 인터페이스 예시는 실제 진단 CLI와 역할이 다르다. [자동 갱신 PR #5167](https://github.com/huggingface/lerobot/pull/5167)은 template이 있어도 실제 경로가 다를 수 있음을 보여준다.

mjlab `dcdf6ce519abfd2ea45e9503ae6fb650b75bb869`: [README](https://github.com/mujocolab/mjlab/blob/dcdf6ce519abfd2ea45e9503ae6fb650b75bb869/README.md), [CONTRIBUTING](https://github.com/mujocolab/mjlab/blob/dcdf6ce519abfd2ea45e9503ae6fb650b75bb869/CONTRIBUTING.md), [AGENTS](https://github.com/mujocolab/mjlab/blob/dcdf6ce519abfd2ea45e9503ae6fb650b75bb869/AGENTS.md), 설치문서를 읽었다. 간단 demo와 상세 경로를 나누고, PR은 제목·체크리스트 없는 짧은 prose를 요구한다. [PR #1218](https://github.com/mujocolab/mjlab/pull/1218)은 문제·변경·작성자가 보고한 CPU 검증을 짧게 연결한다. 보고된 수치를 독립 실행 검증으로 취급하지 않는다.

따라서 좋은 공유를 특정 문서 개수·체크박스·배지로 판단하지 않는다. 프로젝트의 독자와 실제 규칙에 맞추고 실행·주장의 근거를 연결한다.

## 재확인이 필요한 것

실제 설치·게시 시 default branch·권한·공개 범위·플랜, 자산 한도/요금, 도구 버전과 인증 경로를 확인한다. 조사 시점의 commit은 근거를 고정한 것이며 영구 최신이 아니다. 상세 본문 조사와 감사용 원문은 별도 준비 자료에 보관하며 실행 시 모두 로드할 필요는 없다.
