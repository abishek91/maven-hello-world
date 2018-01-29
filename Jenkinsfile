pipeline {
  agent any
  stages {
    stage('Build ') {
      parallel {
        stage('Build') {
          steps {
            dir('my-app') {
                sh 'mvn clean package'
                archiveArtifacts(artifacts: 'target/*.jar')
            }
          }
        }
      }
    }
    stage('Clean Up') {
      steps {
        cleanWs(cleanWhenSuccess: true)
      }
    }
  }
}