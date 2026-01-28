pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git', branch: 'main'
            }
        }
      stage("build & SonarQube analysis") {
        steps {
          withSonarQubeEnv('SonarQube') {
            sh 'mvn clean package org.sonarsource.scanner.maven:sonar-maven-plugin:sonar'
          }
        }
      }
    }
  }