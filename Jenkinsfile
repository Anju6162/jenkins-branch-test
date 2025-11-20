pipeline {
    agent any

    parameters {
        string(
            name: 'STAGES_TO_RUN',
            defaultValue: 'Build,Test,Deploy',
            description: 'Enter stages to run (comma-separated): Build, Test, Deploy'
        )
    }

    stages {

        stage('Build') {
            when {
                expression { 
                    return params.STAGES_TO_RUN.toLowerCase().contains('build')
                }
            }
            steps {
                echo "Running BUILD stage..."
            }
        }

        stage('Test') {
            when {
                expression { 
                    return params.STAGES_TO_RUN.toLowerCase().contains('test')
                }
            }
            steps {
                echo "Running TEST stage..."
            }
        }

        stage('Deploy') {
            when {
                expression { 
                    return params.STAGES_TO_RUN.toLowerCase().contains('deploy')
                }
            }
            steps {
                echo "Running DEPLOY stage..."
            }
        }
    }
}

