pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run load test') {
            steps {
                sh 'k6 run load_testing.js'
            }
        }
    }

    post {
        success {
            slackSend color: "good", message: "Message from Jenkins Pipeline"
        }
    }
}