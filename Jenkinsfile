pipeline {
  agent any
  stages {
    stage('BUILD') {
      steps {
        echo 'BUILDING'
      }
    }
    stage('TEST_JUNIT') {
      steps {
        parallel(
          "TEST_JUNIT": {
            echo 'testing JUNIT'
            
          },
          "TEST_IHM": {
            echo 'testing IHM'
            
          },
          "TEST_SONAR": {
            echo 'testing Sonar'
            
          }
        )
      }
    }
    stage('DEPLOY') {
      steps {
        echo 'Deploy in INTEGRATION'
      }
    }
    stage('TEST_N_REG') {
      steps {
        parallel(
          "TEST_N_REG": {
            echo 'test de non regresssion'
            
          },
          "TEST_PERF": {
            echo 'testing performence'
            
          }
        )
      }
    }
    stage('TAG') {
      steps {
        echo 'taginn delivery'
      }
    }
  }
}