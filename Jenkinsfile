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
//        stage('Checkout') {
//            steps {
//                git branch: 'main',
//                        credentialsId: 'github-app-jenkins',
//                        url: 'https://github.com/Metanet-Signal-Platoon/metanet-legacy-backend'
//            }
//        }
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
//                    cd /home/user/legacy
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
//        stage('Deploy to k8s') {
//            steps {
//                script {
//                    sh """
//                    ssh -o StrictHostKeyChecking=no root@192.168.0.13 '
//                    echo "SSH Connection Successful"
//
//                    echo "Applying Kubernetes Deployment"
//                    export KUBECONFIG=/root/admin.conf
//
//                    # 권한 파악
//                    kubectl config view
//                    kubectl get nodes
//
//                    # 기존 배포물 삭제
//                    kubectl delete -f ~/kubernetes-cicd/1_backend_server_deployment.yaml --ignore-not-found=true
//                    kubectl delete -f ~/kubernetes-cicd/1_backend_server_service.yaml --ignore-not-found=true
//
//                    # 새로운 배포물물 적용
//                    kubectl apply -f ~/kubernetes-cicd/1_backend_server_deployment.yaml
//                    kubectl apply -f ~/kubernetes-cicd/1_backend_server_service.yaml
//                    '
//                    """
//                }
//            }
//        }
    }
}