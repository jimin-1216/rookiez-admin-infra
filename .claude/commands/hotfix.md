# Hotfix 브랜치 생성

운영 긴급 수정을 위한 hotfix 브랜치를 생성한다.

## 절차

1. 현재 브랜치 확인
2. `main` 브랜치로 이동 후 최신 pull
3. `hotfix/<branch-name>` 브랜치 생성

## 네이밍 규칙

형식: `hotfix/<short-description>` 또는 `hotfix/<issue-number>-<short-description>`

규칙:
- 소문자만 사용
- 단어 구분은 하이픈(-)
- 운영 이슈를 명확히 설명하는 이름 사용

## 입력

사용자에게 이슈 내용을 물어본 뒤 브랜치명을 제안한다.

## 실행

```
git checkout main
git pull origin main
git checkout -b hotfix/<name>
```

## 주의사항

- hotfix 완료 후 반드시 `main` + `dev` 모두 반영해야 함을 안내
- 커밋 type은 `fix` 또는 `hotfix` 사용
