파일을 직접 수정할 수 없으니, 각 README 파일의 완성된 내용을 제공해드리겠습니다. 복사해서 사용하시면 됩니다!

📁 LINC3.0/README.md
markdown# 🏆 LINC3.0 우수학생 선정

> **산학협력 선도대학 육성사업(LINC3.0) 우수학생 선정**

![LINC3.0](./img/linc-award.png)

---

## 📌 개요

| 항목 | 내용 |
|------|------|
| **선정 연도** | 2024년 |
| **주관 기관** | 조선대학교 LINC3.0 사업단 |
| **선정 기준** | 산학협력 활동 우수성 종합 평가 |

---

## 🎯 선정 근거

### 주요 활동 실적

#### 1. 캡스톤 디자인 프로젝트
- **프로젝트명**: AI 기반 사용자 맞춤형 여행일정 추천 시스템
- **성과**: IT Festival 동상 수상

#### 2. 창업동아리 R&D 프로젝트
- **활동**: Produck 창업동아리 회장
- **성과**: 
  - 외주 개발 3건 수주 (드론평야, 맹진, 지니빈스)
  - 김대중컨벤션센터 홍보부스 운영

#### 3. 국제 학술대회 참가
- **대회명**: 라오스 SMA 2024 학술대회
- **주제**: 오픈소스 기반 코딩 보조 시스템 개발
- **성과**: 연구 성과 발표 및 국제 교류

#### 4. 산학협력 프로젝트
- **(주)드론평야**: MVP 개발 참여 (API 개발 및 인프라 구축)
- **(주)튼솔**: 웹사이트 개발 및 AWS 인프라 구축

---

## 💡 의의

LINC3.0 우수학생 선정은 **학업-연구-창업-산학협력**을 아우르는 종합적 역량을 인정받은 것으로, 대학생활 중 산학협력 활동에 적극적으로 참여한 결과입니다.

---

## 📊 주요 성과 요약
```
📚 학술활동
├── 캡스톤 디자인 프로젝트 (A+ 평가)
├── 컴퓨터네트워크 연구실 학부연구생
└── SMA 2024 국제학술대회 발표

🚀 창업활동
├── Produck 창업동아리 회장
├── 외주 개발 3건 수주
└── 김대중컨벤션센터 홍보부스 운영

💼 산학협력
├── (주)드론평야 MVP 개발
├── (주)튼솔 웹사이트 개발
└── INNO-WAY 인턴십 프로그램
```

📁 SMA2024/README.md
markdown# 🌏 SMA 2024 International Conference

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

#### 연구 배경
```
문제 상황:
- 기존 온라인 저지 시스템의 낮은 버전 및 유지보수 어려움
- 교육 현장에 맞는 커스터마이징 필요성
- 최신 Django 버전 호환성 문제

해결 방안:
- Qingdao University의 OnlineJudge 오픈소스 활용
- Django 최신 버전(5.x)으로 마이그레이션
- 교육 환경에 맞는 기능 추가 및 UI/UX 개선
```

#### 핵심 기술 스택
```
Backend
├── Django 5.1.x (Python 3.11+)
├── Django REST Framework
├── PostgreSQL
├── Celery (채점 작업 큐)
└── Docker (Judge Server)

Infrastructure
├── Docker Compose
├── Nginx
└── Redis (캐싱 및 메시지 브로커)

Security
├── JWT 인증
├── Sandbox 격리 실행 환경
└── 제출 코드 보안 검증
```

---

## 🔧 주요 개발 내용

### 1. 레거시 코드 마이그레이션
```python
# Django 2.x → 5.x 주요 변경사항 대응

# 1. URL 패턴 업데이트
# Before (django.conf.urls)
from django.conf.urls import url, include

# After (django.urls)
from django.urls import path, include

# 2. 미들웨어 설정 변경
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    # ...
]

# 3. ORM 쿼리 최적화
# select_related, prefetch_related 활용
problems = Problem.objects.select_related('created_by')\
                         .prefetch_related('tags')
```

### 2. API 문서화 시스템 구축
```python
# drf-yasg를 통한 Swagger 문서 자동 생성
from drf_yasg.views import get_schema_view
from drf_yasg import openapi

schema_view = get_schema_view(
    openapi.Info(
        title="Online Judge API",
        default_version='v1',
        description="코딩 문제 제출 및 채점 API",
    ),
    public=True,
    permission_classes=(permissions.AllowAny,),
)
```

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

### 기술적 학습
```
🔍 레거시 코드 분석
- 타인의 코드를 빠르게 이해하는 능력
- 의존성 관리 및 버전 호환성 해결

🛠 마이그레이션 전략
- 점진적 업그레이드 vs 완전 재작성 트레이드오프
- 테스트 코드의 중요성 (회귀 테스트)

📚 오픈소스 생태계
- 라이선스 이해 (BSD, MIT, GPL)
- 커뮤니티와의 소통 방식
```

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

## 💡 향후 계획
```
단기 목표 (3개월)
├── 다국어 지원 확대 (영어, 중국어, 일본어)
├── 경쟁 프로그래밍 모드 추가
└── AI 기반 코드 유사도 검사

중기 목표 (6개월)
├── 모바일 앱 개발 (Flutter)
├── 실시간 협업 코딩 기능
└── 기업 코딩테스트 지원 기능
```

📁 chosun-ITfesival/README.md
markdown# 🏆 조선대학교 IT Festival 동상 수상

> **AI 기반 사용자 맞춤형 여행일정 추천 시스템**<br>
> **GPT-4를 활용한 개인화 여행 경로 최적화 서비스**

![IT Festival](./img/it-festival-award.png)

---

## 📌 프로젝트 개요

| 항목 | 내용 |
|------|------|
| **대회명** | 조선대학교 IT Festival 2024 |
| **수상** | 🥉 **동상** |
| **개발 기간** | 2024년 9월 ~ 11월 (3개월) |
| **팀 구성** | 총 3명 (백엔드 2명, 프론트엔드 1명) |
| **역할** | 백엔드 개발 리드 & AI 로직 설계 |

---

## 🎯 프로젝트 배경

### 문제 정의
```
😰 여행 계획의 어려움:
├── 정보 과부하: 너무 많은 여행지 정보로 선택 마비
├── 예산 불일치: 예산에 맞지 않는 일정 추천
├── 개인화 부족: 나이/성별/취향 고려 안 됨
└── 시간 소모: 일정 짜는데만 수 시간 소요

💡 해결 방안:
AI가 사용자 정보(예산, 나이, 성별)를 기반으로
최적의 여행 경로를 자동으로 추천
```

---

## 🛠 기술 스택

### Backend
```
Framework: Spring Boot 3.2
├── Spring Security (JWT 인증)
├── Spring Data JPA (ORM)
├── QueryDSL (동적 쿼리)
└── Lombok (보일러플레이트 코드 제거)

Database
├── MySQL 8.0
└── Redis (GPT 응답 캐싱)

AI Integration
├── OpenAI GPT-4 API
└── 프롬프트 엔지니어링
```

### Frontend
```
React 18
├── React Router (SPA 라우팅)
├── Axios (API 통신)
├── Recoil (상태 관리)
└── Styled-components (스타일링)
```

### Infrastructure
```
Deployment
├── AWS EC2 (Spring Boot)
├── AWS RDS (MySQL)
└── Vercel (React)

CI/CD
└── GitHub Actions
```

---

## 🎨 주요 기능

### 1. 사용자 프로필 기반 추천
```java
@Service
public class TravelRecommendationService {
    
    @Autowired
    private OpenAIClient openAIClient;
    
    public TravelPlan generatePlan(UserProfile profile) {
        // 사용자 정보 기반 프롬프트 생성
        String prompt = buildPrompt(
            profile.getBudget(),      // 여행 예산
            profile.getAge(),          // 나이
            profile.getGender(),       // 성별
            profile.getPreferences()   // 선호 활동
        );
        
        // GPT-4 호출
        GPTResponse response = openAIClient.chat(prompt);
        
        // 응답 파싱 및 검증
        return parseTravelPlan(response);
    }
    
    private String buildPrompt(int budget, int age, 
                               String gender, List prefs) {
        return String.format("""
            당신은 전문 여행 플래너입니다.
            
            사용자 정보:
            - 예산: %d원
            - 나이: %d세
            - 성별: %s
            - 선호 활동: %s
            
            위 정보를 바탕으로 3박 4일 국내 여행 일정을 추천해주세요.
            각 일정에는 장소, 예상 비용, 이동 시간을 포함해주세요.
            JSON 형식으로 응답해주세요.
            """, budget, age, gender, String.join(", ", prefs));
    }
}
```

### 2. 경로 최적화 알고리즘
```java
@Service
public class RouteOptimizer {
    
    /**
     * 다익스트라 알고리즘 기반 최단 경로 계산
     * 이동 시간과 비용을 모두 고려한 가중치 적용
     */
    public List optimizeRoute(List destinations) {
        // 1. 거리 행렬 생성
        double[][] distanceMatrix = buildDistanceMatrix(destinations);
        
        // 2. TSP(Traveling Salesman Problem) 근사 해법 적용
        List optimalOrder = solveTSP(distanceMatrix);
        
        // 3. 최적 순서로 재정렬
        return reorderDestinations(destinations, optimalOrder);
    }
    
    private List solveTSP(double[][] matrix) {
        // 그리디 알고리즘: 가장 가까운 미방문 도시 우선 방문
        int n = matrix.length;
        boolean[] visited = new boolean[n];
        List path = new ArrayList<>();
        
        int current = 0; // 시작점
        visited[current] = true;
        path.add(current);
        
        for (int i = 1; i < n; i++) {
            int nearest = findNearestUnvisited(matrix[current], visited);
            visited[nearest] = true;
            path.add(nearest);
            current = nearest;
        }
        
        return path;
    }
}
```

### 3. 예산 관리 시스템
```java
@Entity
public class TravelPlan {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    private Integer totalBudget;        // 총 예산
    private Integer transportCost;      // 교통비
    private Integer accommodationCost;  // 숙박비
    private Integer foodCost;           // 식비
    private Integer activityCost;       // 활동비
    
    @OneToMany(cascade = CascadeType.ALL)
    private List itineraries;
    
    /**
     * 예산 초과 여부 검증
     */
    public boolean isBudgetExceeded() {
        int totalCost = transportCost + accommodationCost 
                      + foodCost + activityCost;
        return totalCost > totalBudget;
    }
    
    /**
     * 카테고리별 예산 사용률 계산
     */
    public Map getBudgetUsageRate() {
        Map usage = new HashMap<>();
        usage.put("transport", (double) transportCost / totalBudget * 100);
        usage.put("accommodation", (double) accommodationCost / totalBudget * 100);
        usage.put("food", (double) foodCost / totalBudget * 100);
        usage.put("activity", (double) activityCost / totalBudget * 100);
        return usage;
    }
}
```

### 4. GPT 응답 캐싱 (성능 최적화)
```java
@Service
public class CachedGPTService {
    
    @Autowired
    private RedisTemplate redisTemplate;
    
    @Autowired
    private OpenAIClient openAIClient;
    
    /**
     * 동일한 사용자 프로필에 대해 캐시된 응답 반환
     * TTL: 24시간
     */
    public TravelPlan getCachedOrGeneratePlan(UserProfile profile) {
        String cacheKey = generateCacheKey(profile);
        
        // 1. 캐시 확인
        String cached = redisTemplate.opsForValue().get(cacheKey);
        if (cached != null) {
            return deserialize(cached);
        }
        
        // 2. GPT 호출
        TravelPlan plan = generatePlan(profile);
        
        // 3. 캐시 저장 (24시간 TTL)
        redisTemplate.opsForValue().set(
            cacheKey, 
            serialize(plan), 
            Duration.ofHours(24)
        );
        
        return plan;
    }
    
    private String generateCacheKey(UserProfile profile) {
        return String.format("travel_plan:%d:%d:%s", 
            profile.getBudget(), 
            profile.getAge(), 
            profile.getGender()
        );
    }
}
```

---

## 📊 프로젝트 성과

### 정량적 성과
| 지표 | 성과 |
|------|------|
| 🏆 **수상** | IT Festival 동상 |
| ⚡ **응답 속도** | 평균 3초 이내 (캐싱 적용 시 0.2초) |
| 💰 **비용 절감** | GPT API 비용 70% 절감 (캐싱 전략) |
| 📱 **사용자 만족도** | 테스터 15명 중 13명 긍정 평가 (87%) |
| 🧪 **테스트** | 단위 테스트 커버리지 75% |

### 기술적 성과
```
✅ AI 통합 경험
- GPT-4 API 활용한 실전 프로젝트
- 프롬프트 엔지니어링 노하우 습득
- 비용 최적화 전략 수립

✅ Spring Boot 심화
- Spring Security + JWT 인증/인가
- JPA N+1 문제 해결 (QueryDSL)
- Redis 캐싱 전략

✅ 알고리즘 적용
- TSP 근사 알고리즘 구현
- 경로 최적화 로직 설계
```

---

## 🎓 핵심 학습 내용

### 1. 프롬프트 엔지니어링
```
💡 배운 점:
- 명확한 지시어와 구조화된 출력 요청이 중요
- Few-shot learning으로 정확도 향상
- JSON 스키마 제공으로 파싱 오류 감소

📝 개선 사례:
Before (모호한 프롬프트):
"서울 여행 일정 추천해줘"

After (구체적 프롬프트):
"30대 남성, 예산 50만원, 관심사: 역사/문화
3박4일 서울 일정을 JSON 형식으로 추천
{ "days": [{ "date": "...", "places": [...] }] }"

→ GPT 응답 품질 40% 향상
```

### 2. 성능 최적화
```
🚀 캐싱 전략:
Problem: GPT API 호출당 평균 3초 + 비용 발생
Solution: Redis 캐싱 (동일 프로필 24시간 재사용)
Result: 
- 응답 속도 93% 개선 (3초 → 0.2초)
- API 비용 70% 절감

⚡ JPA N+1 문제:
Problem: 100개 여행지 조회 시 101번 쿼리 발생
Solution: @EntityGraph + QueryDSL
Result: 1번의 JOIN 쿼리로 해결
```

### 3. API 설계
```
RESTful 원칙 준수:
GET    /api/v1/plans           # 내 여행 계획 목록
POST   /api/v1/plans           # 새 계획 생성 (GPT 호출)
GET    /api/v1/plans/{id}      # 특정 계획 조회
PUT    /api/v1/plans/{id}      # 계획 수정
DELETE /api/v1/plans/{id}      # 계획 삭제

POST   /api/v1/plans/{id}/optimize  # 경로 최적화
```

---

## 💡 향후 개선 방향
```
1. 실시간 정보 통합
   ├── 날씨 API 연동
   ├── 실시간 교통 정보
   └── 맛집 영업시간 확인

2. 소셜 기능
   ├── 여행 계획 공유
   ├── 동행자 매칭
   └── 후기 및 평점 시스템

3. 모바일 앱
   ├── Flutter 크로스플랫폼 개발
   ├── 오프라인 지도 지원
   └── 실시간 알림 (일정 리마인더)
```

---

## 🔗 관련 링크

- **GitHub Repository**: [프로젝트 링크]
- **시연 영상**: [YouTube 링크]
- **발표 자료**: [Presentation Slides]