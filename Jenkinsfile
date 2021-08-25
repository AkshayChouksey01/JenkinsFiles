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

        stage('Test Log') {
          steps {
            writeFile(file: 'LogTextFile.txt', text: 'This is the Automation Test File')
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