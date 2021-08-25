pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the DotNet Core application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the Application'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the app in the Server'
      }
    }

  }
}