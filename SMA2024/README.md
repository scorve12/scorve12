# 🌏 SMA 2024 International Conference

> **라오스 국립대학교 주최 국제 학술대회 참가**<br>
> **오픈소스 기반 온라인 저지 시스템 연구 발표**

![SMA2024](./img/laos-conference.png)

---

## 📌 학술대회 개요

| 항목 | 내용 |
|------|------|
| **대회명** | SMA 2024 (Student Mobility in Asia) |
| **개최지** | 라오스 비엔티안 |
| **개최 기간** | 2024년 11월 |
| **참가 형태** | 연구 발표 (Oral Presentation) |
| **주관** | 조선대학교 LINC3.0 사업단 |

---

## 🎯 연구 주제

### 오픈소스 기반 코딩 보조 시스템 개발

**프로젝트명**: Qingdao Online Judge 마이그레이션 및 커스터마이징

#### 연구 배경문제 상황:

기존 온라인 저지 시스템의 낮은 버전 및 유지보수 어려움
교육 현장에 맞는 커스터마이징 필요성
최신 Django 버전 호환성 문제
해결 방안:

Qingdao University의 OnlineJudge 오픈소스 활용
Django 최신 버전(5.x)으로 마이그레이션
교육 환경에 맞는 기능 추가 및 UI/UX 개선


#### 핵심 기술 스택Backend
├── Django 5.1.x (Python 3.11+)
├── Django REST Framework
├── PostgreSQL
├── Celery (채점 작업 큐)
└── Docker (Judge Server)Infrastructure
├── Docker Compose
├── Nginx
└── Redis (캐싱 및 메시지 브로커)Security
├── JWT 인증
├── Sandbox 격리 실행 환경
└── 제출 코드 보안 검증

---

## 🔧 주요 개발 내용

### 1. 레거시 코드 마이그레이션
```pythonDjango 2.x → 5.x 주요 변경사항 대응1. URL 패턴 업데이트
Before (django.conf.urls)
from django.conf.urls import url, includeAfter (django.urls)
from django.urls import path, include2. 미들웨어 설정 변경
MIDDLEWARE = [
'django.middleware.security.SecurityMiddleware',
'django.contrib.sessions.middleware.SessionMiddleware',
# ...
]3. ORM 쿼리 최적화
select_related, prefetch_related 활용
problems = Problem.objects.select_related('created_by')
.prefetch_related('tags')

### 2. API 문서화 시스템 구축
```pythondrf-yasg를 통한 Swagger 문서 자동 생성
from drf_yasg.views import get_schema_view
from drf_yasg import openapischema_view = get_schema_view(
openapi.Info(
title="Online Judge API",
default_version='v1',
description="코딩 문제 제출 및 채점 API",
),
public=True,
permission_classes=(permissions.AllowAny,),
)

### 3. 교육 환경 최적화
- **실시간 채점 피드백**: Celery를 통한 비동기 채점 처리
- **다국어 지원**: 한국어 인터페이스 추가
- **통계 대시보드**: 학생별 문제 풀이 현황 시각화

---

## 📊 연구 성과

### 정량적 성과
| 지표 | 성과 |
|------|------|
| 코드 마이그레이션 | 🔄 Django 2.x → 5.x (300+ 파일) |
| 성능 개선 | ⚡ 채점 속도 **40% 향상** |
| API 엔드포인트 | 📡 **25+** 개 문서화 |
| 테스트 커버리지 | 🧪 **60%** 달성 |

### 정성적 성과
- ✅ **오픈소스 기여**: 업스트림 프로젝트에 이슈 리포팅 및 개선 제안
- ✅ **국제 교류**: 라오스 학생들과 기술 교류 및 네트워킹
- ✅ **실전 경험**: 대규모 레거시 코드베이스 리팩토링 경험

---

## 🎓 학습 및 인사이트

### 기술적 학습🔍 레거시 코드 분석

타인의 코드를 빠르게 이해하는 능력
의존성 관리 및 버전 호환성 해결
🛠 마이그레이션 전략

점진적 업그레이드 vs 완전 재작성 트레이드오프
테스트 코드의 중요성 (회귀 테스트)
📚 오픈소스 생태계

라이선스 이해 (BSD, MIT, GPL)
커뮤니티와의 소통 방식


### 연구 발표 경험
- 🎤 **영어 발표**: 기술 내용을 비전공자도 이해할 수 있게 설명
- 🤝 **질의응답**: 예상 질문 준비 및 즉석 대응 능력
- 🌐 **문화 교류**: 아시아 학생들과의 네트워킹

---

## 🔗 관련 링크

- **원본 프로젝트**: [QingdaoU/OnlineJudge](https://github.com/QingdaoU/OnlineJudge)
- **Swagger 문서**: [API Documentation](./swagger/)
- **발표 자료**: [Presentation Slides](./presentation/)

---

## 💡 향후 계획단기 목표 (3개월)
├── 다국어 지원 확대 (영어, 중국어, 일본어)
├── 경쟁 프로그래밍 모드 추가
└── AI 기반 코드 유사도 검사중기 목표 (6개월)
├── 모바일 앱 개발 (Flutter)
├── 실시간 협업 코딩 기능
└── 기업 코딩테스트 지원 기능
