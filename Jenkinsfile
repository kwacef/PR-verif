pipeline {
  agent any
	stages {
		stage ("hello") {
			steps {
				script {
          	sh """ curl \"https://api.GitHub.com/repos/kwacef/PR-verif/statuses/$GIT_COMMIT?access_token=127d15b286aea8d68310fe6e83b0b5804d61bdff\"  -H \"Content-Type: application/json\" -X POST  -d \"{\\"state\\": \\"pending\\",\\"context\\": \\"continuous-integration/jenkins\\", \\"description\\": \\"Jenkins\\", \\"target_url\\": \\"https://13.57.9.107/job/luqi-PR-verif/$BUILD_NUMBER/console\\"}\" """ 
				currentBuild.displayName = BUILD_NUMBER + "//" + GIT_BRANCH    
        sleep(10)
					error()
					
				}      
			}    
		}

		
	}
	
	post {
		failure {
      
			// Send email on failure

			script {
				sh """ curl \"https://api.GitHub.com/repos/kwacef/PR-verif/statuses/$GIT_COMMIT?access_token=127d15b286aea8d68310fe6e83b0b5804d61bdff\"  -H \"Content-Type: application/json\" -X POST  -d \"{\\"state\\": \\"failure\\",\\"context\\": \\"continuous-integration/jenkins\\", \\"description\\": \\"Jenkins\\", \\"target_url\\": \\"https://13.57.9.107/job/luqi-PR-verif/$BUILD_NUMBER/console\\"}\" """        
			}
		}
		success {
			// Send email on failure
			script {
				sh """ curl \"https://api.GitHub.com/repos/kwacef/PR-verif/statuses/$GIT_COMMIT?access_token=127d15b286aea8d68310fe6e83b0b5804d61bdff\"  -H \"Content-Type: application/json\" -X POST  -d \"{\\"state\\": \\"success\\",\\"context\\": \\"continuous-integration/jenkins\\", \\"description\\": \\"Jenkins\\", \\"target_url\\": \\"https://13.57.9.107/job/luqi-PR-verif/$BUILD_NUMBER/console\\"}\" """        
			}
		}
	}
  
}
