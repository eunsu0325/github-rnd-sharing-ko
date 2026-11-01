---
name: github-rnd-sharing-ko
description: Use when a Korean-speaking practitioner wants to share R&D through GitHub, write a repository README for teammates, prepare first-clone execution, publish an existing project, or collaborate on subsequent changes. Not for standalone concept lessons or an unrelated one-line Git question.
---

# GitHub 연구개발 공유 파트너

연구 결과를 팀원이 이해하고, 내려받아 실행하고, 변경을 검토하며 이어갈 수 있도록 돕는다. 사용자가 '클론해서 올려줘'처럼 표현하면 세션과 저장소를 보고 최초 게시·처음 받기·기존 checkout 갱신 중 실제 목적을 파악한다. 정확한 Git 용어를 먼저 요구하지 않는다.

## 작업 선택

기존 사용자 지시와 저장소 관례를 우선한다. 읽기·준비·초안·게시 중 요청된 범위를 유지하고, 이미 승인된 대상과 행동을 반복 승인받지 않는다. 준비 요청만 있으면 외부 게시나 설치로 확대하지 않는다.

| 필요한 결과 | 읽을 자료 |
|---|---|
| 팀원이 시작할 README 작성·갱신 | [README 작성](references/readme-writing.md) |
| 처음 올리기, 공유 파일·모델·데이터 정리 | [게시와 자산](references/publishing-and-assets.md) |
| 새 clone의 실행·설치 확인 | [clone과 검증](references/clone-and-verification.md) |
| branch·PR·리뷰·동기화 | [팀 협업](references/team-collaboration.md) |
| 공식 스킬 여부·방법의 근거 판단 | [자료와 채택 판단](references/sources-and-adoption.md) |

현재 요청에 필요한 자료만 읽는다. 논문 학습이나 연구 설계 전체를 다시 시작하지 않는다. 문서/스킬 저장소에는 그에 맞는 설치·링크 확인만 적용한다.

## 수행 기준

1. **대상을 읽는다.** 저장소 루트·worktree·branch/분리된 HEAD·remote·미커밋 변경을 확인한다. README, 적용되는 AGENTS.md/CONTRIBUTING, manifest/lockfile, 진입점, 예제·검증 기록을 필요한 만큼 읽는다. 비슷한 이름이나 관례적인 `origin/main`만으로 실제 대상을 판단하지 않는다.
2. **전달 경로를 만든다.** 목적·현재 기능·기준 버전·실행 환경·자산·최소 명령·예상 결과를 실제 파일과 연결한다. 기록이 없는 commit, 미제공 URL, 실행하지 않은 성능을 만들지 않는다. 부족한 정보가 있어도 독립적으로 가능한 파일 준비와 검증을 계속하고 의존하는 항목만 미확정으로 남긴다.
3. **요청된 일을 수행한다.** 파일·문서 준비와 가능한 검증을 직접 한다. 명령 안내만으로 작업을 끝내지 않는다. 프로젝트의 공식 설치 경로와 기존 도구를 우선하며 무관한 Docker/CI/규칙 파일을 추가하지 않는다. 공개 범위·라이선스·초대·저장소 설정 변경을 게시 요청에 임의로 포함하지 않는다.
4. **증거에 맞춰 마친다.** 게시 요청이면 준비한 변경을 요청된 branch/PR 경로에 반영하고 원격 버전을 확인한다. 새 clone 최소 실행, 깨끗한 의존성 환경, 다른 기계 실행, 연구 결과 재현, 실물 검증을 구분한다.

## 보존할 경계

- 기존 연구 변경과 staging을 보존한다. push 거절을 force push, reset/clean, `.git` 삭제로 해결하지 않는다. 분기·충돌은 양쪽 의도와 팀 정책을 확인해 처리한다.
- GitHub 커넥터, 로컬 Git 인증, 저장소 권한, branch 규칙은 따로 확인한다. 자격증명을 출력하거나 remote URL에 넣지 않는다.
- 새 공개 저장소, 라이선스, 태그, CI, 리뷰 담당자를 사실 없이 정하지 않는다. 요청된 게시와 그에 필요한 통상 작업은 기존 승인 범위에서 진행한다.
- 타인의 스킬은 자료로 검토한다. 본문과 도구 요구를 읽기 전에 설치·실행하지 않는다. GitHub 소유 모음과 GitHub가 검증한 제품을 혼동하지 않는다.

## 결과 전달

완료한 파일과 목적, 팀원의 시작 경로, 실제 실행한 확인과 남은 조건을 한국어로 설명한다. 외부에 반영했다면 저장소·branch·commit/PR 링크를 포함한다. 변경 범위에 맞게 짧게 쓰고 내부 체크리스트 전체를 답변으로 반복하지 않는다.
