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
          environment {
            var = 'Hello World'
          }
          steps {
            writeFile(file: 'LogTextFile.txt', text: "This is the Automation Test File for Jenkins for Local Variable Value ${var}")
          }
        }

      }
    }

    stage('Deploy') {
      
      when {
        branch 'main'
      }
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying the app in the Server'
            input(message: 'Do you want To Deploy?', id: 'ok')
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogTextFile.txt'
          }
        }

      }
    }

  }
}
