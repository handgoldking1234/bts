# 빅트리소프트 리뉴얼 시안 (bts) — 작업 안내서

## 한 줄 요약
교육 솔루션 기업 빅트리소프트(BigTreeSoft) 홈페이지 리뉴얼 퍼블리싱 시안. 해시 라우팅 원페이지.

## 확정된 결정
| 항목 | 결정 |
|---|---|
| 레퍼런스 | 거인소프트 사이트 레이아웃 |
| 단계 | 순수 HTML/CSS + 간단한 스크립트 (개발 소스 없음) |
| 아이콘·폰트 | Lucide(unpkg), Plus Jakarta Sans + Noto Sans KR |

## 파일
```
index.html   전체 페이지 (#home #reference #consulting #story #story-1~9 #solution #recruit #about)
img/         히어로·도입사례·스토리·솔루션·채용·회사소개 이미지
```
- 주요 함수: `route`·`go`·`nav`(해시 라우팅) · `filterRef`·`filterSt`(도입사례·스토리 필터) · `openModal`(상담 신청 팝업) · `setSol`(솔루션 탭)
- 같은 시안이 `iux-studio/samples/bigtreesoft/`에도 제작 사례로 들어 있음 → 고치면 같이 맞출 것

## 운영 전 할 일
AI 생성 이미지 중 실제 기업 로고·깨진 문자가 있는 것 교체, 샘플 콘텐츠(도입 사례·스토리·연혁) 실제 내용으로 교체.

---

## 공통 작업 원칙 (IUX 프로젝트 전체)
- **언어:** 화면 문구·문서·커밋 메시지는 한국어. 쉬운 말, 기술 용어 최소화.
- **퍼블리싱 시안:** 순수 HTML/CSS + 간단한 스크립트만 넣는다. 서버·DB 연동 코드는 개발 단계에서 따로 붙인다.
- **아이콘:** Lucide. 디자인 시스템을 따로 정하지 않았으면 스포티파이 스타일(다크/화이트 + 포인트 컬러)을 기본으로 쓴다.
- **배포:** GitHub `main` → Vercel 자동 배포. 도메인은 가비아 `iux.kr`의 서브도메인(`*.iux.kr` CNAME → Vercel)을 쓴다.
- **DB:** Supabase 무료 플랜은 활성 프로젝트 2개까지라, 새 프로젝트를 만들지 말고 기존 `iux-cloud`(studio) 프로젝트에 테이블을 얹는 것을 먼저 검토한다.
- **비밀값:** 공개 저장소다. 서비스 키·AI 키·비밀번호는 절대 커밋하지 않는다. 키는 Vercel 환경 변수나 Supabase secrets에 둔다. Supabase anon(public) 키만 코드에 넣을 수 있다.
- **확인:** 고친 뒤에는 브라우저 콘솔 오류 0개, 모바일(390px)과 PC 화면을 눈으로 확인하고 나서 완료라고 한다.
- **브랜치:** `main`은 배포 중인 상태. 큰 작업이나 검증 전 작업은 브랜치(`wip/…`, `claude/…`)에 올리고, `main`을 강제 푸시(-f)로 덮어쓰지 않는다.
- **전체 프로젝트 목록:** https://github.com/handgoldking1234/iux-app/blob/main/docs/PROJECTS.md
