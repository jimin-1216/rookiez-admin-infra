# Feature 브랜치 생성

새 기능 개발을 위한 feature 브랜치를 생성한다.

## 절차

1. 현재 브랜치 확인
2. `dev` 브랜치로 이동 후 최신 pull
3. `feature/<branch-name>` 브랜치 생성

## 네이밍 규칙

형식: `feature/<short-description>` 또는 `feature/<issue-number>-<short-description>`

규칙:
- 소문자만 사용
- 단어 구분은 하이픈(-)
- 의미 없는 이름 금지 (`feature/test`, `feature/tmp` 금지)

## 입력

사용자에게 브랜치 설명(또는 이슈 번호)을 물어본 뒤 브랜치명을 제안한다.

## 실행

```
git checkout dev
git pull origin dev
git checkout -b feature/<name>
```

생성 후 현재 브랜치를 출력하여 확인한다.
