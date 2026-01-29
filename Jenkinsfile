pipeline {
    agent any

    tools {
        jdk 'jdk17'
    }


    stages {

        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    credentialsId: 'git-cred',
                    url: 'https://github.com/ningarajgani/scriblog-miniproject.git'
            }
        }


    post {
        success {
           
            echo 'successfully completed integration'
        }
        unstable {
            echo 'CI completed with Quality Gate warnings'
        }
        failure {
            echo 'CI Pipeline failed'
        }
       
    }
}