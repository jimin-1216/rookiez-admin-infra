# 릴리즈 (dev → main)

dev 브랜치를 main으로 릴리즈하는 PR을 생성한다.

## 절차

1. `dev` 브랜치 최신 상태 확인 (`git fetch && git log origin/dev --oneline -10`)
2. `main` 대비 변경사항 확인 (`git diff origin/main...origin/dev --stat`)
3. 버전 태그 결정

## 버전 태깅 규칙

형식: `vMAJOR.MINOR.PATCH`

- `MAJOR`: 호환성 깨지는 변경
- `MINOR`: 기능 추가
- `PATCH`: 버그 수정

최근 태그를 확인하고 (`git tag --sort=-v:refname | head -5`) 다음 버전을 제안한다.

## PR 생성

- base: `main`, head: `dev`
- 제목: `[RELEASE] dev -> main (v<version>)`
- 본문: dev에 포함된 커밋/PR 목록 요약

## 태그 생성

PR 병합 확인 후:
```
git checkout main
git pull origin main
git tag v<version>
git push origin v<version>
```

## 체크리스트 안내

- [ ] CI 통과
- [ ] 리뷰 승인 완료
- [ ] 변경 영향 범위 확인
- [ ] 롤백 방법 확인
- [ ] 배포 후 모니터링 계획

## 주의사항

- 태그는 immutable — `latest` 사용 금지
- 동일 이미지 태그를 환경 승격하는 방식 준수
