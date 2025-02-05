pipeline {
    agent any
    tools {
        gradle("gradle")
    }
    environment {
        CONTAINER_IMAGE = "docker.io/metanet-legacy/backend:latest"
    }
    stages {
        stage('Jenkinsfile') {
            steps {
                echo "hello jenkins?"
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'main',
                        credentialsId: 'github-app-jenkins',
                        url: 'https://github.com/Metanet-Signal-Platoon/metanet-legacy-backend'
            }
        }
        stage('test') {
            steps {
                echo "hello?"
            }
        }

        stage('Build Gradle'){
            steps{
                sh 'chmod +x gradlew'
                sh './gradlew clean build -x test'
            }
        }
        
//        stage('Build Image') {
//            steps {
//                script {
//                    withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASSWORD')]) {
//                        sh """
//                    ssh -o StrictHostKeyChecking=no root@192.168.0.13 '
//                    echo "SSH Connection Successful"
//
//                    export CONTAINER_IMAGE="${CONTAINER_IMAGE}"
//                    export DOCKER_USER="${DOCKER_USER}"
//                    export DOCKER_PASSWORD="${DOCKER_PASSWORD}"
//
//                    cd /home/user/legacy/toon_metanet-legacy-backend_main
//                    sudo chmod +x gradlew
//                    sudo podman build -t $CONTAINER_IMAGE .
//                    echo $DOCKER_PASSWORD | sudo podman login -u $DOCKER_USER --password-stdin docker.io  # 안전한 로그인 방식
//                    sudo podman push $CONTAINER_IMAGE
//                    sudo podman rmi $CONTAINER_IMAGE # 기존 이미지 삭제
//                    '
//                    """
//                    }
//                }
//            }
//        }

    }
}