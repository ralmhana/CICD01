pipeline {
    agent {
        docker {
            image 'grafana/k6'
        }
    }

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
        always {
            slackSend color: "good", message: "Message from Jenkins Pipeline"
        }
    }
}