pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Fetching latest source code from GitHub...'
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling MatrixMultiplication.java...'
                sh 'javac MatrixMultiplication.java'
            }
        }

        stage('Execute') {
            steps {
                echo 'Running MatrixMultiplication...'
                sh 'java MatrixMultiplication'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCEEDED: MatrixMultiplication.java compiled and executed cleanly.'
        }
        failure {
            echo 'BUILD FAILED: Check the console output above for compilation or execution errors.'
        }
    }
}