pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building the app..."
            }
        }

        stage('Tests Only on Master') {
            when {
                branch 'master'
            }
            parallel {
                stage('Test-1') {
                    steps { 
                        echo "Running Test 1"
                        sh "sleep 3"
                    }
                }

                stage('Test-2') {
                    steps { 
                        echo "Running Test 2"
                        sh "sleep 3"
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying..."
            }
        }

    }
}
