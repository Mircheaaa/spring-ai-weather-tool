# 🔀 개발 규칙

## Branch 규칙

### 브랜치 네이밍
```
{type}/{scope}/{issue-number}
```

**예시**: `feat/be/12`, `fix/fe/23`, `docs/infra/5`

### 브랜치 종류
- `feat`: 새로운 기능 개발
- `fix`: 버그 수정
- `refactor`: 코드 리팩토링
- `docs`: 문서 작성/수정
- `chore`: 설정, 빌드 관련

### 범위
- `be`: Backend
- `fe`: Frontend
- `infra`: 인프라/배포/설정

---

## Commit 규칙

### 커밋 메시지 형식
```
{type}({scope}): {summary}

{description}
```

### 예시
```bash
git commit -m "feat(be): 사용자 인증 API 구현

- JWT 토큰 기반 인증 시스템 추가
- OAuth2 Google 연동 완료"
```

### Type 종류
- `feat`: 새 기능
- `fix`: 버그 수정
- `refactor`: 리팩토링
- `docs`: 문서
- `chore`: 기타

---

## PR 규칙

### PR 제목
```
{type}({scope}): {summary} (#{issue-number})
```

**예시**: `feat(be): 사용자 API 구현 (#12)`

### PR 템플릿
```markdown
## 변경사항
- 주요 변경 내용

## 테스트
- [ ] 로컬 테스트 완료
- [ ] ktlint 통과

## 체크리스트
- [ ] 코드 리뷰 요청
- [ ] 문서 업데이트
```

### 머지 조건
- **dev**: 기능 완성 + 리뷰 완료
- **main**: 배포 준비 완료

---

## 자동화 도구

### ktlint 설정
```bash
# 팀원 설정 (최초 1회)
./setup-git-hooks.sh    # Linux/Mac
setup-git-hooks.bat     # Windows

# 수동 실행
./gradlew ktlintCheck   # 검사
./gradlew ktlintFormat  # 자동 수정
```

### 커밋 전 체크리스트
1. `./gradlew ktlintCheck` 통과
2. 빌드 성공 확인
3. 테스트 실행