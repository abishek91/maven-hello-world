pipeline {
  agent any
  stages {
    stage('Build ') {
      parallel {
        stage('Build') {
          steps {
            dir('task-1/grader') {
                sh 'mvn clean package'
                archiveArtifacts(artifacts: 'target/*.jar')
            }
          }
        }
      }
    }
    stage('Approval') {
      steps {
        input 'Continue?'
      }
    }
    stage('Clean Up') {
      steps {
        cleanWs(cleanWhenSuccess: true)
      }
    }
  }
}