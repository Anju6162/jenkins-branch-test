pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Build stage running..."
            }
        }

        stage('Tests Only On Master') {
            when {
                branch 'master'
            }
            stages {

                stage('Unit Test') {
                    steps {
                        echo "Running Unit Tests..."
                    }
                }

                stage('Integration Test') {
                    steps {
                        echo "Running Integration Tests..."
                    }
                }

            }
        }

    }
}
