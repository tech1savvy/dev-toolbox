pipeline {
    agent any
    stages {
        stage('Cleanup') {
            steps {
                script {
                    deleteDir()
                }
            }
        }
        stage('Git Clone') {
            steps {
                bat 'git clone https://github.com/tech1savvy/dev-toolbox.git .'
            }
        }
        stage('Clear previous Builds') {
            steps {
                bat 'docker compose down'
            }
        }
        stage('Docker Compose') {
            steps {
                bat 'docker compose up -d --build'
            }
        }
    }
}
