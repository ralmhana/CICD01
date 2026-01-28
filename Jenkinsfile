pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest --junitxml=results.xml'
            }
        }

        stage('Run load test') {
            steps {
                sh 'k6 run load_testing.js'
            }
        }
    }

    post {
        always {
            slackSend color: "good", message: "Message from Jenkins Pipeline"
        }
    }
}