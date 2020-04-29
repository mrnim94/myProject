pipeline {
  agent { label 'worker1' }
  tools {
    maven 'M3'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/effectivejenkins/myProject.git'
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
