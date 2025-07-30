## 블로그 포스트 작성하는 방법

이 가이드는 우리 아이티메세지 기술 블로그에 새로운 포스트를 작성하는 방법을 설명합니다.

## 1. 새로운 포스트 생성하기

### 명령어로 생성
```bash
# 한국어 포스트
hugo new posts/포스트제목.md

# 영어 포스트  
hugo new posts/포스트제목.en.md

# 예시
hugo new posts/react-hooks-tutorial.md
hugo new posts/react-hooks-tutorial.en.md
```

### 수동으로 생성
`content/posts/` 폴더에 직접 `.md` 파일을 생성할 수도 있습니다.

## 2. Front Matter 설정

모든 포스트는 YAML front matter로 시작해야 합니다:

```yaml
---
title: "포스트 제목"
date: 2025-07-30
author: "작성자명"
draft: false  # true면 초안, false면 게시
tags: ["태그1", "태그2", "태그3"]
categories: ["카테고리1", "카테고리2"]
description: "포스트 요약 (선택사항)"
---
```

### Front Matter 항목 설명

| 항목 | 필수 | 설명 | 예시 |
|------|------|------|------|
| `title` | ✅ | 포스트 제목 | "React Hooks 완벽 가이드" |
| `date` | ✅ | 작성 날짜 (YYYY-MM-DD) | 2025-07-30 |
| `author` | ✅ | 작성자명 | "김개발자" |
| `draft` | ✅ | 초안 여부 | false |
| `tags` | ❌ | 태그 목록 | ["react", "hooks", "frontend"] |
| `categories` | ❌ | 카테고리 | ["프론트엔드", "React"] |
| `description` | ❌ | 포스트 요약 | "React Hooks 사용법을 알아봅시다" |

## 3. 마크다운 문법 활용하기

### 제목 (Headers)
```markdown
# 큰 제목 (H1)
## 중간 제목 (H2)  
### 작은 제목 (H3)
```

### 코드 블록
````markdown
```javascript
function HelloWorld() {
  return <h1>Hello, World!</h1>;
}
```

```bash
npm install react
```
````

### 링크와 이미지
```markdown
[링크 텍스트](https://example.com)
![이미지 설명](/images/screenshot.png)
```

### 리스트
```markdown
- 순서 없는 리스트
- 두 번째 항목

1. 순서 있는 리스트
2. 두 번째 항목
```

### 강조
```markdown
**굵게** 또는 __굵게__
*기울임* 또는 _기울임_
`인라인 코드`
```

## 4. 파일 위치와 구조

### 디렉토리 구조
```
content/
├── posts/
│   ├── my-post.md          # 한국어 포스트
│   ├── my-post.en.md       # 영어 포스트
│   └── another-post.md
├── archives.md
├── archives.en.md
├── search.md
└── search.en.md
```

### 파일명 규칙
- **한국어**: `포스트명.md`
- **영어**: `포스트명.en.md`
- 파일명은 영어로 작성 (URL에 사용됨)
- 공백 대신 하이픈(-) 사용

## 5. 카테고리와 태그 가이드

### 권장 카테고리
- **프론트엔드**: React, Vue, JavaScript 관련
- **백엔드**: Node.js, Python, 데이터베이스 관련
- **DevOps**: Docker, 배포, CI/CD 관련
- **가이드**: 튜토리얼, 사용법 설명
- **리뷰**: 도구, 라이브러리 리뷰
- **일상**: 개발 경험, 회고

### 태그 작성 팁
- 구체적이고 검색 가능한 키워드 사용
- 3-5개 정도의 태그 권장
- 기술명, 도구명, 개념명 등을 포함

## 6. 로컬에서 미리보기

포스트를 작성한 후 로컬에서 확인:

```bash
# 개발 서버 실행 (초안도 포함)
hugo server -D

# 브라우저에서 확인
http://localhost:1313/tech-blog/
```

## 7. 배포하기

### GitHub에 푸시
```bash
git add .
git commit -m "새 포스트 추가: 포스트 제목"
git push origin gh-pages
```

### 자동 배포
- GitHub에 푸시하면 GitHub Actions가 자동으로 빌드 및 배포
- 보통 2-5분 후 https://itmsgdev.github.io/tech-blog/ 에서 확인 가능

## 8. 포스트 작성 체크리스트

작성 완료 전 다음 사항들을 확인해주세요:

- [ ] Front matter가 올바르게 설정되었는가?
- [ ] `draft: false`로 설정되었는가?
- [ ] 적절한 태그와 카테고리가 설정되었는가?
- [ ] 코드 블록에 언어가 명시되었는가?
- [ ] 이미지가 있다면 올바른 경로인가?
- [ ] 로컬에서 미리보기가 정상인가?
- [ ] 영어 버전도 함께 작성했는가? (선택사항)

## 9. 유용한 팁

### 날짜 자동 설정
Hugo 명령어로 생성하면 현재 날짜가 자동으로 설정됩니다.

### 이미지 관리
- `static/images/` 폴더에 이미지 저장
- 마크다운에서 `/images/파일명.png`로 참조

### 초안 관리
- `draft: true`로 설정하면 개발 서버에서만 보임
- 배포 시에는 초안이 제외됨

### SEO 최적화
- `description` 필드로 포스트 요약 제공
- 적절한 제목과 헤더 구조 사용
- 관련 태그 설정으로 검색 최적화

