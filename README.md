# 📘 프로젝트 실행 가이드

## 📂 프로젝트 구성

- **백엔드**: NestJS 기반 API 서버 (`project_nest-deployment-repo`)
- **프론트엔드**: React 기반 웹 애플리케이션 (`project_react-deployment-repo`)
- **데이터베이스 초기화**: PostgreSQL 데이터베이스 백업 파일 (`db_backup`)
- **환경 설정**: Docker 및 Docker Compose 파일 (`docker-compose.yml`)

## ⚙️ 실행 전 준비사항

1. **리포지토리 클론**:

   - `project_env-setup-repo`, `project_nest-deployment-repo`, `project_react-deployment-repo` 각 리포지토리를 클론
   - 디렉토리 구조가 다음과 같이 설정:
     ```
     프로젝트 루트/
     ├── project_env-setup-repo/
     │   ├── db_backup/
     │   └── docker-compose.yml
     ├── project_nest-deployment-repo/
     └── project_react-deployment-repo/
     ```

## 🚀 프로젝트 실행 방법

1. **Docker Compose로 프로젝트 시작**:

   - `project_env-setup-repo` 디렉토리로 이동
   - 아래 명령어를 실행하여 모든 서비스를 시작
     ```bash
     docker-compose up -d (--build)
     ```

2. **Docker Compose 설정 설명**:
   - `docker-compose.yml` 파일에는 백엔드, 프론트엔드, 데이터베이스 서비스가 정의
   - 각 서비스는 다음 역할을 합니다:
     - **백엔드**: `project_nest-deployment-repo`의 `Dockerfile`을 빌드하고, API 서버를 `localhost:3001`에서 실행
     - **프론트엔드**: `project_react-deployment-repo`의 `Dockerfile`을 빌드하고, React 앱을 `localhost:8088`에서 실행
     - **데이터베이스**: PostgreSQL 컨테이너가 `db_backup` 폴더의 초기화 SQL 파일을 사용해 데이터베이스를 설정

## 🧪 서비스 확인 및 테스트 

1. **실행 중인 컨테이너 확인**:
   ```bash
   docker ps
   ```
