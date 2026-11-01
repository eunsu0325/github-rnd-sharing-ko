# 팀 협업과 변경 공유

## 저장소 규칙과 협업 모델

적용되는 AGENTS.md/CONTRIBUTING, PR template, 기본 branch·규칙과 기존 commit 관례를 읽는다. conventional commits, fork, squash/rebase, 특정 PR 목차를 GitHub의 보편적 의무로 만들지 않는다.

| 상황 | 시작점 |
|---|---|
| 공유 repo에 팀원 write 권한 있음 | 작업 branch와 PR이 기본 후보 |
| 원본 write 권한 없고 fork 허용 | 자기 fork의 branch에서 upstream PR |
| private fork 제한 | 허용된 접근·기여 경로 확인; 공개 복사로 우회하지 않음 |
| 진행 중 방향을 논의 | 요청 범위에서 draft PR 또는 기존 논의 경로 |
| 최초 연구 코드 전체 게시 | 최초 도입 범위·한계 설명; 이후 변경처럼 억지로 분할하지 않음 |

새 branch 이름은 프로젝트/실행 환경의 규칙을 따른다. 현재 사용자가 공유할 branch를 확인하지 않고 무조건 `main`으로 바꾸지 않는다.

## Issue → 변경 → PR → 리뷰

Issue나 연구 기록에는 문제와 재현 조건을 남긴다. 모든 작은 수정에 새 issue를 요구하지 않는다. 복잡한 실험은 질문/가설·기준 버전·설정·관찰 결과를 기존 연구 기록에 두고 PR에서 연결한다.

Commit은 하나의 의미 있는 변경을 담는다. 고정 line 수나 파일 수가 기준은 아니다. staging을 읽고 관련 변경을 선택하며 다른 작업을 임의로 포함하거나 unstage하지 않는다. 메시지는 실제 diff의 변화와 이유를 담는다. 메시지만 요청받았다면 실제 commit하지 않는다.

PR은 기존 template이 있으면 맞춘다. 없으면 문제, 변경 후 행동, 실제 확인, 남은 조건을 필요한 길이의 문장으로 설명한다. 검토가 어려운 변화에는 볼 파일·설정·비교 결과를 짚는다. 수행하지 않은 검사에 완료 표시하지 않는다. 모든 PR에 고정된 제목/체크박스 묶음을 만들지 않는다.

관련 issue 참고와 해결 완료를 구분한다. `Fixes/Closes`는 default branch 대상 PR의 merge에서 issue를 종료할 수 있으므로 완료 의도가 있을 때만 사용한다. 중간 실험·부분 구현이면 관련 링크만 남긴다.

요청된 branch push/PR까지 수행하고 원격 대상을 확인한다. 특정인 mention·review 요청·merge·설정 변경은 작업 범위를 따로 판단한다. 기존 승인과 명확한 팀 규칙을 따르며 요청 없는 외부 연락을 추가하지 않는다. 리뷰 중 변경 범위가 달라지면 최종 diff에 맞춰 제목·설명·README·관련 검증을 갱신한다.

## 기존 clone 동기화

checkout·tracking 관계·미커밋 작업을 읽는다. 원격 조회는 fetch와 차이 확인으로 처리할 수 있다. pull은 현재 branch로 통합하므로 조회와 구분한다.

깨끗한 tracking branch가 뒤처지기만 했다면 명시적 fast-forward 갱신을 후보로 사용한다. 양쪽에 독립 commit이 있으면 팀 merge/rebase 정책과 양쪽 변경을 보고 결정한다. 공유 이력을 임의 재작성하거나 로컬 실험을 stash/reset해서 진행하지 않는다.

non-fast-forward는 원격 이력을 보존하며 진단한다. 충돌은 양쪽 코드·설정 의도를 읽어 최종 내용을 결정하고 관련 검증을 한다. 통째로 ours/theirs를 택한 뒤 해결됐다고 보고하지 않는다. 중단 시 진행 중인 merge/rebase와 보존할 작업에 맞는 복구 절차를 선택한다.

리뷰·검사 서버 강제는 실제 공개 범위·플랜·규칙에 달린다. 수동 PR 합의를 branch 보호와 같다고 설명하거나 공유를 위해 설정을 자동 변경하지 않는다.

근거: [협업 모델](https://docs.github.com/en/pull-requests/reference/pull-requests), [PR 검토 지원](https://docs.github.com/en/pull-requests/concepts/helping-others-review-your-changes), [Google 변경 설명](https://google.github.io/eng-practices/review/developer/cl-descriptions.html), [Git pull](https://git-scm.com/docs/git-pull).
