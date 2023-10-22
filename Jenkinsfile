pipeline {
  agent any
  environment {
    NEW_VERSION = '1.0.0'
    // SERVER_CREDENTIALS = credentials ('admin')
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
          withCredentials([
            usernamePassword(credentials: ('admin'), usernameVariable: USER, passwordVariable: PWD)
            {
              sh "Accepting from Username:${USER} Password: ${PWD}"
            }
          ])
        }
      }

      stage ("CLEANUP") {
        steps {
          echo "Cleaning up the app..."
        }
      }
    }
}  
