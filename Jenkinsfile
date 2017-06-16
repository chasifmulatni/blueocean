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
        parallel(
          "build-jobs": {
            build 'quals-build-cq-search'
            
          },
          "build-cq-workflows": {
            build 'quals-build-cq-workflows'
            
          },
          "build-web-strategy": {
            build 'quals-build-cq-web-strategy'
            
          }
        )
      }
    }
    stage('	deploy-quals-cq-search-pre-dev') {
      steps {
        build '	deploy-quals-cq-search-pre-dev'
      }
    }
    stage('deploy-quals-cq-workflows-pre-dev') {
      steps {
        build 'deploy-quals-cq-workflows-pre-dev'
      }
    }
    stage('deploy-quals-web-stratgey-pre-dev') {
      steps {
        build 'deploy-quals-web-stratgey-pre-dev'
      }
    }
  }
}