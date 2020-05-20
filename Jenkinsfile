pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }

    stage('test') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true clean package'
      }
    }

    stage('Archive') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}