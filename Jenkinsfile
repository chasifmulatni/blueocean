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
    stage('build-cq-search') {
      steps {
        build 'quals-build-cq-search'
      }
    }
    stage('build-cq-workflows') {
      steps {
        build 'quals-build-cq-workflows'
      }
    }
    stage('build-web-strategy') {
      steps {
        build 'quals-build-web-strategy'
      }
    }
  }
}