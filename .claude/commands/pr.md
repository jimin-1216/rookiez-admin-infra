# Pull Request 생성

현재 브랜치의 변경사항을 PR로 생성한다.

## 절차

1. 현재 브랜치 확인 (`git branch --show-current`)
2. `git status`로 커밋 안 된 변경 확인 — 있으면 먼저 커밋할지 물어보기
3. `git log`와 `git diff <base>...HEAD`로 전체 변경 내용 분석
4. 원격에 push 안 되어 있으면 `git push -u origin <branch>`

## 브랜치별 PR 대상

| 현재 브랜치 | PR 대상 (base) | 병합 방식 |
|---|---|---|
| `feature/*` | `dev` | Squash merge |
| `hotfix/*` | `main` | Merge commit |
| `dev` | `main` (릴리즈) | Merge commit |

## PR 제목 규칙

- `feature/*` → `[FEAT] <설명>`
- `hotfix/*` → `[HOTFIX] <설명>`
- `dev` → `main` → `[RELEASE] dev -> main (v<version>)`

## PR 본문 템플릿

```markdown
## 목적
- <왜 필요한가>

## 변경 내용
- <무엇이 바뀌는가>

## 영향 범위
- <API/DB/배포/운영 영향>

## 테스트
- [ ] 관련 테스트 통과
- [ ] 로컬 검증 완료

## 배포/롤백
- <배포 후 확인 사항>
- <문제 시 롤백 방법>
```

## 실행

- `gh pr create` 사용
- 변경 내용을 분석하여 제목과 본문 초안을 자동 생성
- 사용자에게 확인받은 뒤 PR 생성
- PR URL 출력

## 주의사항

- `main`, `dev` 브랜치에서 직접 PR 생성은 릴리즈 PR(`dev`→`main`)만 허용
- hotfix PR 생성 시 "dev 역반영 필요" 안내 포함
