pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Hello'
            }
        }
    }
    post {
        success {
           slackSend color: "good", message: "Message from Jenkins Pipeline"
        }
    }
  }