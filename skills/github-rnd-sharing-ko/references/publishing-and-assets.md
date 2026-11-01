# 게시와 연구 자산

## 최초 게시/기존 갱신

대상 폴더·Git 루트·remote·branch·미커밋 작업을 읽는다. 원격이 있으면 기본 branch와 이력을 확인한다. 기존 Git 프로젝트에 init을 반복하거나 `.git`을 제거해 시작하지 않는다.

빈 원격과 README commit 등이 있는 원격을 구분한다. 후자는 현재 프로젝트와 연결 관계를 확인하고 이력을 보존한다. non-fast-forward를 force push나 무조건 unrelated-history merge로 해결하지 않는다. 파일 갱신 API가 로컬 Git 이력 전체 게시와 같다고 표현하지 않는다.

공유 대상·공개 범위를 세션에서 파악한다. 이미 승인된 게시를 반복 승인받지 않는다. 팀 공유만으로 public 전환·라이선스·collaborator 초대·repo 이전/이름 변경·CI/ruleset 변경까지 추정하지 않는다. 현재 작업에 꼭 필요한 정보만 묻고 독립적인 파일 준비는 계속한다.

## 파일 선별

현재 파일·staging과 필요한 이력에 공유 제외 파일이 있는지 확인한다. 비밀값을 출력하지 않고 경로와 필요한 조치 범위를 설명한다. `.gitignore`는 tracked 파일이나 과거 commit을 지우지 않으므로 실제 추적 목록도 확인한다. 작은 예제·필수 설정이 제외되지 않았는지 본다.

내부 자료·로컬 결과를 무조건 게시하지 않는다. 용도를 모르는 파일을 정리라는 이유로 삭제하지도 않는다. 필요한 설정은 비밀값 없는 예시와 실제 주입 방법으로 전달한다.

노출된 자격증명은 철회/교체를 우선 검토한다. 현재 파일 삭제만으로 노출 해결을 주장하지 않는다. 이력 재작성은 다른 clone/fork에 영향을 주므로 자동 복구로 실행하지 않는다. mirror는 실제 이관 목적일 때만 검토한다.

## 모델·데이터·mesh·영상

| 경로 | 검토할 용도 |
|---|---|
| 일반 Git | 소스·작은 설정·작은 재현 입력 |
| LFS | 코드 버전과 함께 관리할 바이너리, quota/전송 부담이 허용될 때 |
| Release assets | 특정 배포 버전에 묶는 결과물·패키지 |
| 외부 모델/데이터 저장소 | 대규모 자산 또는 별도 접근·버전 관리 |

필수 자산의 역할, revision/해시, 취득 위치, 배치 경로, 크기와 접근 조건을 필요한 만큼 남긴다. 재배포 불가면 합법적 취득 절차와 현재 실행 제한을 설명한다. 모든 repo에 LFS/DVC/외부 허브를 추가하지 않는다. GitHub/LFS/Release 한도·요금은 필요할 때 현행 문서와 대상 계정 조건을 확인한다.

원본 코드·데이터·모델·CAD의 라이선스/NOTICE·출처·수정 범위를 보존한다. 자체 LICENSE/CITATION이 다른 자산 조건을 대체하지 않는다. 공개 repo라는 사실만으로 재사용·재배포 허가를 추정하지 않는다.

게시 후 요청된 파일·commit·branch를 원격에서 다시 확인한다. 배포 요청이면 기준 commit/tag와 자산을 연결하고 변경·호환 조건을 설명한다. 태그/Release 생성은 README 초안에 자동 포함하지 않는다. 파일·링크 존재와 push 성공은 실행·연구 결과 검증과 다른 증거다.

근거: [기존 코드 게시](https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github), [gitignore](https://git-scm.com/docs/gitignore), [LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-git-large-file-storage), [Release](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases), [민감정보 제거](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository).
