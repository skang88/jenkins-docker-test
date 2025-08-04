pipeline {
    // 현재 폴더의 Dockerfile로 임시 에이전트를 만들고,
    // 그 안에서 아래 stage들을 실행합니다.
    // 이 설정은 'docker' 객체를 확실하게 활성화시킵니다.
    agent { dockerfile true }

    stages {
        stage('Test Docker Command from a Docker Agent') {
            steps {
                script {

                    sh "docker ps -a"
                    echo "This step is running inside a temporary agent container."
                    echo "Now, using the plugin's command to talk to the HOST's Docker daemon..."

                    // 이 명령어는 마운트된 docker.sock을 통해
                    // 호스트의 도커 엔진과 직접 통신합니다.
                    docker.image('hello-world').run()
                }
            }
        }
    }
}