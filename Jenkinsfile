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
           slackSend color: "good", message: "New Message from Jenkins Pipeline"
        }
    }
  }