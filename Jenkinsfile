pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo "Building on branch: ${env.BRANCH_NAME}"
        // e.g. sh 'mvn -B -DskipTests package'
      }
    }

    stage('Unit Test (master only)') {
      when { branch 'master' }
      steps {
        echo 'Running Unit Tests (only on master)'
        // sh 'mvn test -Dtest=Unit*'
      }
    }

    stage('Integration Test (master only)') {
      when { branch 'master' }
      steps {
        echo 'Running Integration Tests (only on master)'
        // sh 'mvn verify -Pintegration'
      }
    }

    stage('Publish / Archive') {
      steps {
        echo 'Publish artifacts or results'
      }
    }
  }

  post {
    always {
      echo "Finished build for ${env.BRANCH_NAME}"
    }
  }
}

