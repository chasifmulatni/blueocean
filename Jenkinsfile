pipeline {
  agent none
  stages {
    stage('sonar-cq-search') {
      steps {
        parallel(
          "sonar-cq-search": {
            build 'quals-sonar-cq-search'
            
          },
          "sonar-cq-workflows": {
            build 'quals-sonar-cq-workflows'
            
          },
          "sonar-web-strategy": {
            build 'quals-sonar-cq-web-strategy'
            
          }
        )
      }
    }
    stage('SonarQube Quality Gate') {
      steps {
        waitForQualityGate()
      }
    }
  }
}