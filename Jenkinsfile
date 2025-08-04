pipeline {
    // 1. '임시 에이전트'를 만들지 않고, Jenkins 컨트롤러 자신을 에이전트로 사용
    agent any

    // 2. Docker 도구를 사용한다고 명시적으로 선언
    tools {
        dockerTool 'docker-tool' // Global Tool Configuration에 등록한 이름
    }

    stages {
        stage('Test Docker Command on Controller') {
            steps {
                script {
                    echo "This test runs directly on the main Jenkins container."
                    echo "This container has the Docker CLI and socket access."
                    
                    // 3. 플러그인의 고유 기능을 사용하여 호스트의 Docker와 통신
                    docker.image('hello-world').run()
                }
            }
        }
    }
}