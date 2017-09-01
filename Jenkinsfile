pipeline {
    agent {label 'slave-w-docker-cromwell-60GB-ebs'}

    environment {
        QUAY_PASS = credentials('gabdank-quay')
            }

    stages {
        stage('Unit-tests') {
            steps { 
                echo "Running unit tests.."
            }
        }
    }
	post {
        success {
                echo 'Post build actions that run on success'
                // slackSend "Job ${env.JOB_NAME}, build number ${env.BUILD_NUMBER} on branch ${env.BRANCH_NAME} finished successfully."
        }
        failure {
                echo 'Post build actions that run on failure'
                // slackSend "Job ${env.JOB_NAME}, build number ${env.BUILD_NUMBER} on branch ${env.BRANCH_NAME} failed."
        }
        always {
                echo 'Post build actions that run always'
        }
	}
}