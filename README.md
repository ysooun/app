### app 배포 구성도
---
<img width="567" alt="스크린샷 2024-03-08 오전 4 05 02" src="https://github.com/ysooun/app/assets/154872496/d0c40d7d-6892-4e35-9a56-cb60551e8b87">

1. app 구성은 3가지로 나누어 관리됩니다. deployment. service, secret(시크릿 정보는 따로 관리되는게 맞습니다
2. Deployment의 replicas는 3개로 구성되어 있습니다. 파드가 항상 3개를 유지합니다. 예를들어 첫번째 파드가 죽으면 새로운 이름의 파드가 새로 생성됩니다.
3. Deployment의 1대1 롤링 업데이트는 한 번에 하나의 Pod만 업데이트하면서, 동시에 항상 하나 이상의 Pod가 사용 가능하도록 합니다.
4. Deployment는 일반적으로 환경변수를 사용하여 데이터베이스 정보를 읽고, Kubernetes의 Secret을 활용하여 해당 정보를 안전하게 가져와 데이터베이스와의 연결을 설정합니다.
5. Service는 TCP 프로토콜을 사용하여 80 포트로 접근할 수 있도록 ClusterIP를 제공합니다.
