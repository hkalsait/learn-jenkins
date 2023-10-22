pipeline {
  agent any
  environment {
    NEW_VERSION = '1.0.0'
  }
    stages {

      stage ("INITIAL") {
        steps {
          echo "Initialize steps..."
        }
      }
      
      stage ("BUILD") {
      when {
        expression {
          BRANCH_NAME == "main" || BRANCH_NAME == "master"
        }
      }
        steps {
          script {
          echo "Building the app..."
          echo "Building the Newer Version ${NEW_VERSION}"
          }
        }
      }
      
      stage ("TEST") {
        steps {
          echo "Testing the app..."
        }
      }

      stage ("DEPLOY") {
        steps {
          echo "deploying the app..."
        }
      }

      stage ("CLEANUP") {
        steps {
          echo "Cleaning up the app..."
        }
      }
    }
}  
