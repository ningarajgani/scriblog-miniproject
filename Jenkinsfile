pipeline {
    agent any

    stages {

        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    // credentialsId: 'git-cred',
                    url: 'https://github.com/ningarajgani/scriblog-miniproject.git'
            }
        }

        stage('Verify Text File') {
            steps {
                echo 'Listing files in repo...'
                sh 'ls -l'

                echo 'Displaying text file content'
                sh 'cat *.txt || echo "No text file found, but build will still succeed"'
            }
        }
    }

    post {
        success {
            echo 'Build SUCCESS ✅'
        }
        failure {
            echo 'Build FAILED ❌'
        }
    }
}

