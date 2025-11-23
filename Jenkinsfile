pipeline {
    agent any

    stages {

        stage('A') {
            steps {
                script {
                    // catchError prevents the pipeline from aborting when A fails.
                    // stageResult: 'FAILURE' makes the stage shown as failed, but pipeline continues.
                    catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                        echo ">>> Running Stage A ..."
                        // Replace the next line with your real steps.
                        // To test behavior, set exit 0 or exit 1:
                        sh 'exit 1' // simulate failure; change to 'exit 0' to simulate success
                    }

                    // Record final status for Stage A.
                    // currentBuild.currentResult is 'SUCCESS' or 'FAILURE'
                    if (currentBuild.currentResult == 'SUCCESS') {
                        env.A_STATUS = 'SUCCESS'
                    } else {
                        env.A_STATUS = 'FAILURE'
                    }
                    echo "A_STATUS = ${env.A_STATUS}"
                }
            }
        }

        stage('B - run if A success') {
            when {
                expression { return env.A_STATUS == 'SUCCESS' }
            }
            steps {
                echo ">>> Stage B: running because A succeeded"
                // sh './run-B.sh'
            }
        }

        stage('C - run if A failed') {
            when {
                expression { return env.A_STATUS == 'FAILURE' }
            }
            steps {
                echo ">>> Stage C: running because A failed"
                // sh './run-C.sh'
            }
        }
    }

    post {
        always {
            echo "Final recorded A_STATUS = ${env.A_STATUS}"
        }
    }
}
