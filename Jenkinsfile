pipeline {
  agent any
     tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven 3.8.6"
        jdk "JDK11"
        }
  stages {
    stage('Run Tests') {
      steps {
        sh './mvnw clean test'
      }
      post {
        always {
          junit '**/surefire-reports/*.xml'
          cucumber buildStatus: 'null', customCssFiles: '', customJsFiles: '', failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: 'target/cucumber.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
        }
      }
    }
  }
}
