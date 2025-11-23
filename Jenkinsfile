pipeline {
    agent any

    stages {

        stage('Test A') {
            when {
                expression { return params.STAGES_TO_RUN.contains("testA") }
            }
            steps {
                echo "Running Test A..."
            }
        }

        stage('Test B') {
            when {
                expression { return params.STAGES_TO_RUN.contains("testB") }
            }
            steps {
                echo "Running Test B..."
            }
        }

        stage('Deploy') {
            when {
                expression { return params.STAGES_TO_RUN.contains("deploy") }
            }
            steps {
                echo "Running Deploy..."
            }
        }
    }
}
