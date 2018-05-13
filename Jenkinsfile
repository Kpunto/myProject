pipeline {
  agent { label 'slave1' }
  tools {
    maven 'Maven 3.5.0'
    jdk 'Java 8'
  }
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/Kpunto/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
