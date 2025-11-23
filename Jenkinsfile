pipeline {
    agent any

    parameters {
        // This reflects your Active Choices parameter
        string(name: 'STAGES_TO_RUN', defaultValue: '', description: 'Selected stages to run (from Multiselect)')
    }

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
