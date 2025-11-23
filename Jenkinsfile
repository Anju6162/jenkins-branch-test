pipeline {
    agent any

    parameters {
        choice(name: 'STAGE_TO_RUN', choices: ['all', 'testA', 'testB', 'deploy'], description: 'Select stage to run')
    }

    stages {

        stage('testA') {
            when {
                expression { params.STAGE_TO_RUN == 'testA' || params.STAGE_TO_RUN == 'all' }
            }
            steps {
                echo "Running testA..."
                // sh './run-testA.sh'
            }
        }

        stage('testB') {
            when {
                expression { params.STAGE_TO_RUN == 'testB' || params.STAGE_TO_RUN == 'all' }
            }
            steps {
                echo "Running testB..."
                // sh './run-testB.sh'
            }
        }

        stage('deploy') {
            when {
                expression { params.STAGE_TO_RUN == 'deploy' }
            }
            steps {
                echo "Running deploy..."
                // sh './deploy.sh'
            }
        }
    }
}
