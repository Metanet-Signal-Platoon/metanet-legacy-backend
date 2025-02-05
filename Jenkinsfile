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
                checkout([
                        $class: 'GitSCM',
                        branches: [[name: 'main']],
                        userRemoteConfigs: [[
                                                    credentialsId: 'github-app-jenkins',
                                                    url: 'https://github.com/Metanet-Signal-Platoon/metanet-legacy-backend.git'
                                            ]]
                ])
            }
        }
    }
}