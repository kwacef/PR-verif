pipeline {
  agent any
  stages {
        stage ("hello") {
      steps {
        script {
          currentBuild.displayName = BUILD_NUMBER + "/" + GIT_BRANCH          sh """            echo "he00"          """        }      }    }
      stage ("hi") {
      steps {
        script {
          sh """ curl \"https://api.GitHub.com/repos/kwacef/PR-verif/statuses/$GIT_COMMIT?access_token=127d15b286aea8d68310fe6e83b0b5804d61bdff\" \ -H \"Content-Type: application/json\" \ -X POST \ -d \"{\"state\": \"failure\",\"context\": \"continuous-integration/jenkins\", \"description\": \"Jenkins\", \"target_url\": \"18.144.45.118/job/luqi-PR-verif/$BUILD_NUMBER/console\"}\" """        }      }    }
     }
     }
