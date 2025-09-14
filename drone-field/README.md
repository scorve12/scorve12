# 🚁 드론평야 (Dronefield) - 농업 방제 서비스 플랫폼

> **드론평야는 방제가 필요한 농민들에게 빠르게 농업용 드론조종사들과 매칭해주는 플랫폼 서비스입니다.\
초기창업패키지에 선정되어 단기간(3개월)간 MVP 모델 개발 후 배포까지 진행되는 프로젝트입니다.**

## 📋 프로젝트 개요

![기획이미지](./img/Figma(1).png)
- **개발 기간**: 2024년 12월 ~ 2025년 8월
- **담당 직무**: 백엔드 API 시스템 및 인프라 구축 및 Devops 담당
- **주요 성과**:  **🏆초기창업패키지 완료🏆**, AWS 배포, Google Play Store 출시

## 🛠 기술 스택

### Backend
- **Framework**: Django 5.1.5, Django REST Framework
- **Database**: PostgreSQL
- **Authentication**: JWT (django-rest-framework-simplejwt)
- **Storage**: AWS S3
- **Front-End**: React, Flutter

### Infrastructure & DevOps
- **Cloud**: AWS (EC2, RDS, S3, Elastic Beanstalk)
- **Containerization**: Docker
- **CI/CD**: AWS CodePipeline, CodeBuild

### 제3자 API 통합
- **본인인증**: NICE API
- **지도서비스**: Naver API, VWorld API  
- **SMS**: 알리고 SMS API
- **결제**: 토스페이먼츠

## 🎯 핵심 성과 및 학습 포인트

### 1. 비즈니스와 개발
대표님의 사업확장 방향성을 반영하여 확장 가능한 DB 스키마와 API를 설계했으며, 향후 AI 개발자와의 협업 가능성과 Python 개발자 채용의 용이성을 고려해 Django 프레임워크를 채택했습니다. Django의 강력한 마이그레이션 시스템과 AI 라이브러리 호환성이 기술 선택의 핵심 요인이었습니다. 

### 2. 도메인 지식과 개발
프로젝트 진행 중 드론 고유번호 체계, 농지의 법정동과 행정동 주소 간 차이점, 방제요청서의 다양한 상태 및 예외상황 등 복잡한 도메인 로직을 다루면서 대표님과 수차례 회의를 통해 요구사항을 명확히 해야 했습니다. 서로 다른 전문 영역에 대한 이해 부족으로 인한 소통 오류가 개발 지연을 초래했지만, 이를 통해 도메인 전문가와의 효과적인 소통 방법론과 기술적 결정에서 비즈니스 관점을 고려하는 것의 중요성을 깊이 체득할 수 있었습니다.

### 3. 크로스플랫폼 개발의 실질적 어려움 극복
Flutter와 React를 사용한 크로스플렛폼은 고려해야 할 점이 많았습니다. 기존에 세션방식이던 인증방식을 비교적 일정이 빠듯한 Flutter에 맞추기 위해 JWT 형식으로 변경했으며 Flutter 웹뷰에 사용할 API 또한 정리했습니다.


### 4. 제3자 API 통합을 통한 완성도 높은 서비스 구현
Nice, 알리고, Naver API, 토스페이먼츠등 실제 서비스를 위한 다양한 API를 정리하고 저희 양식에 맞추어 개발과 문서화를 하며 학습하는 것에 오랜 시간을 투자했습니다.

### 5. DevOps와 인력
4명의 개발인원으로 실 서비스가 가능한 수준의 서비스를 개발하는 것은 많은 인력이 필요합니다. 서로의 작업현황과 수정사항, 문서화, 일관성 유지를 모두 신경 쓰기에는 시간이 부족했습니다. 그래서 저희는 Figma, Notion, Postman같은 문서프로그램을 적극적 사용했으면 AI도구부터 깃허브 연동, Figma to Notion 연동, AWS CI/CD등 여러 도구를 사용하여 실질적으로 부족한 인력 문제를 보완할 수 있었습니다.