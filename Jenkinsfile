pipeline {
    agent {
        label 'jenkins-agent'
    }

    tools {
        nodejs 'Node21'
    }

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout') {
            steps {
                // Use the provided Git credentials for authentication
                script {
                    git branch: 'master', url: 'https://github.com/lalit0111/react-todo-pipeline', credentialsId: 'github-token'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'npm install -y'
                    sh "echo 'Build successful!'"
                }
            }
        }
    }
}
    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
