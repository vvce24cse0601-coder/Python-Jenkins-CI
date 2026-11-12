
pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'javac -version'
                bat 'javac App.java Test.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java Test'
            }
        }
    }

    post {
        success {
            echo 'Build stable'
        }
        failure {
            echo 'Build failed'
        }
    }
}
