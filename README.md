## 항해 플러스 9주차 - 인프라 성능 개선

### 배포 파이프라인

<img width="308" alt="화면 캡처 2024-11-19 225337" src="https://github.com/YouHaveToDo/front_3rd_chapter4-1/blob/main/aws.jpg">

### 개요

1. 워크플로우 트리거
    - main 브랜치에 코드가 푸시될 때 자동으로 워크플로우 실행.
2. Job 정의
    - 배포를 위한 Job을 정의.
    - 최신 버전의 ubuntu를 사용.
3. GitHub 레포지토리 코드 체크아웃
    - 빌드 및 배포 작업을 위 GitHub 레포지토리의 소스 준비.
4. 프로젝트 의존성 설치
    - npm ci를 사용하여 lock 파일에 명시된 정확한 버전의 패키지를 설치.
5. 프로젝트 빌드
    - npm run build를 사용하여 프로젝트 빌드.
    - out/ 디렉토리에 빌드 결과물 저장.
6. AWS 자격 증명 설정
    - GitHub Secrets에 저장된 AWS 자격 증명을 사용해 AWS CLI를 설정.
7. CloudFront 캐시 무효화


---

### 주요 링크
- S3 버킷 웹사이트 엔드포인트: http://kobe-hanghae-plus.s3-website.us-east-2.amazonaws.com
- CloudFrount 배포 도메인 이름: https://d3aye62uqtawvn.cloudfront.net

---

### 주요 개념
- CI/CD: 소프트웨어 개발에서 코드 변경을 자동으로 빌드, 테스트, 배포하는 프로세스를 포함하는 개발 방법론.
- GitHub Actions: GitHub에서 제공하는 CI/CD 도구로, 코드를 자동으로 빌드, 테스트, 배포하거나 기타 작업을 수행할 수 있는 워크플로우 제공.
- AWS S3와 스토리지: AWS에서 제공하는 객체 스토리지 서비스로, 웹 사이트 호스팅, 백업 및 아카이브, 애플리케이션 호스팅 등 다양한 용도로 사용 가능.
- CludFront와 CDN: CloudFront는 AWS의 CDN(Content Delivery Network) 서비스로, 전 세계의 엣지 로케이션을 통해 콘텐츠를 빠르게 전송하고, 보안 및 DDoS 공격 방어 기능을 제공.
- 캐시 무효화(Cache Invalidation): 캐시된 데이터를 무효화하여 새로운 데이터로 교체하는 작업으로, 새로운 데이터를 즉시 반영할 수 있도록 함.
- Repository Secret과 환경변수: GitHub Actions에서 사용하는 보안 정보를 저장하는 저장소 레벨의 시크릿과 환경변수를 설정할 수 있음.
