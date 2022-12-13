# Git Action 이해

- 빌드, 테스트 및 배포 파이프라인을 자동화할 수 있는 CI/CD 플랫폼이다.
- 저장소에 대한 모든 풀 요청을 빌드 및 테스트하는 워크플로를 생성하거나 병합된 풀 요청을 프로덕션에 배포할 수 있다.
- Github은 Linux, Windows, macOS 가상 머신을 제공하여 워크플로를 실행하거나 자체 데이터 센터 또는 클라우드 인프라에서 자체 호스팅 러너를 구축할 수 있다.

## Github Actions 구성 요소

- PR이 열리거나 Issue를 생성하는 등 이벤트를 발생시킬 때 트리거가 되도록 Github Actions 워크플로를 구성할 수 있다.
- 워크플로는 순차적 또는 병렬적으로 실행할 수 잇는 하나 이상의 작업으로 포함되어 있다.

<image>

## Workflows(워크플로)

- 워크플로는 하나 이상의 작업을 실행하는 구성 가능한 자동화 프로세스이다.
- 저장소에 있는 YAML 파일에 의해 정의되며 저장소의 이벤트가 발생했을 때 또는 수동으로 또는 정의된 일정에 따라 트리거 될 수 있다.
- 저장소 디렉터리 내에 `.github/workflows` 에 각각 다른 작업의 집합을 수행할 수 있는 여러 워크플로 존재할 수 있다.

## Events(이벤트)

- 이벤트는 워크플로 실행을 트리거 하는 저장소의 특정 활동이다.
- 예를 들어 PR 요청, Issue 생성, 커밋을 푸쉬 등의 활동이 있다.

## Jobs(작업)

- 작업은 동일한 Runner에 실행되는 워크플로 단계의 집합을 말한다.
- 각 단계는 쉘 스크립트로 실행되며 각 단계는 순서대로 실행되며 의존적이다.
- 각 단계는 동일한 Runner에서 실행되므로, 하나의 작업이 다른 작업의 데이터를 공유할 수 있다.
- 기본적으로 작업에 종속성이 없으며 서로 병렬적으로 실행된다.
- 만약 한 작업이 다른 작업에 종속되면 해당 작업은 종속 작업이 완료될 때까지 기다렸다가 실행된다.

## Actions(행위)

- action은 복잡하고 반복되는 작업을 수행하는 custom application 이다.
- action은 워크플로 파일을 쓰는데 반복되는 코드의 상당 수를 줄이는데 도움을 준다.

## Runners(러너)

- 러너는 트리거될 때 워크플로를 실행하는 서버이다.
- 각 러너는 한 번에 하나의 작업을 실행할 수 있고 Github는 Linux, Windows, macOS 등 Runner를 제공하여 워크플로를 실행한다.

## References

- [https://docs.github.com/ko/actions/learn-github-actions/understanding-github-actions](https://docs.github.com/ko/actions/learn-github-actions/understanding-github-actions)