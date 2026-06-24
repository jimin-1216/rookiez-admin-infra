# Git Commit (Conventional Commits)

현재 변경사항을 Conventional Commits 규칙에 맞게 커밋한다.

## 절차

1. `git status`로 변경 파일 확인 (untracked 포함)
2. `git diff --staged`와 `git diff`로 변경 내용 분석
3. `git log --oneline -5`로 최근 커밋 스타일 확인
4. 현재 브랜치 확인 (`git branch --show-current`)

## 커밋 메시지 규칙

형식: `<type>(<scope>): <summary>`

### type 종류
- `feat`: 기능 추가
- `fix`: 버그 수정
- `refactor`: 동작 변경 없는 구조 개선
- `docs`: 문서 변경
- `test`: 테스트 추가/수정
- `chore`: 빌드/설정/기타 유지보수
- `ci`: CI/CD 설정 변경
- `hotfix`: 운영 긴급 수정 (hotfix/* 브랜치에서만)

### 규칙
- 한 커밋에는 하나의 논리적 변경만 담는다
- `WIP`, `final`, `test` 같은 의미 없는 커밋 메시지 금지
- summary는 한글 또는 영문 (팀 스타일에 맞춤)

## 브랜치별 주의사항

- `main`, `dev` 브랜치에서는 직접 커밋 금지 — 경고를 출력하고 중단
- `feature/*` 브랜치: 일반 커밋 진행
- `hotfix/*` 브랜치: type은 `fix` 또는 `hotfix` 사용 권장

## 실행

- 변경 내용을 분석하여 적절한 type, scope, summary를 자동 판단
- 사용자에게 커밋 메시지 초안을 보여주고 확인받은 뒤 커밋
- `git add`는 관련 파일만 선택적으로 staging (민감 파일 .env 등 제외)
- Co-Authored-By 트레일러 포함
