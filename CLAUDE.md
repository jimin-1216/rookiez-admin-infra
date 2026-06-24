# Project: rookiez-admin-infra

루키즈 통합 운영 엔진 — Notion 자동화 인프라

## Git Convention

### Branch Strategy
- `main`: 운영 기준 (직접 push 금지)
- `dev`: 개발 통합 (직접 push 금지)
- `feature/*`: 기능 개발 (`dev`에서 분기 → `dev`로 PR)
- `hotfix/*`: 운영 긴급 수정 (`main`에서 분기 → `main` + `dev` 반영)

### Commit Message (Conventional Commits)
형식: `<type>(<scope>): <summary>`

type: feat, fix, refactor, docs, test, chore, ci, hotfix

금지: WIP, final, test 같은 의미 없는 메시지

### PR Rules
- `feature/*` → `dev`: Squash merge, 제목 `[FEAT] ...`
- `hotfix/*` → `main`: Merge commit, 제목 `[HOTFIX] ...`
- `dev` → `main`: Merge commit, 제목 `[RELEASE] dev -> main (vX.Y.Z)`
- hotfix 후 반드시 `dev` 역반영

### Custom Commands
- `/commit` — Conventional Commits 기반 커밋
- `/feature` — feature 브랜치 생성 (dev에서 분기)
- `/hotfix` — hotfix 브랜치 생성 (main에서 분기)
- `/pr` — 브랜치에 맞는 PR 생성
- `/release` — dev → main 릴리즈 PR + 태그
