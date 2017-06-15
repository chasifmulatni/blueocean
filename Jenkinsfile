pipeline {
  agent none
  stages {
    stage('sonar') {
      steps {
        build 'quals-sonar-cq-search'
      }
    }
  }
}