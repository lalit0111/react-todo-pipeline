pipeline {
    agent {
        label 'jenkins-agent'
    }

    tools {
        nodejs 'Node21' // Replace 'NodeJS 14' with your configured Node.js tool name
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
                // Perform build steps here, e.g., for a Maven project
                script {
                    sh 'npm install'
                    sh 'npn start'
                }
            }
        }

        // Add more stages as needed, such as testing, deployment, etc.
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
