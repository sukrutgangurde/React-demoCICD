pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sukrutgangurde/React-demoCICD.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t react-project:dev .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 5173:5173 react-project:dev'
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
