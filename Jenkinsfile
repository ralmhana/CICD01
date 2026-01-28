pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Load Testing') {
            steps {
                sh 'k6 run loading_test.js'
            }
        }

    }

}