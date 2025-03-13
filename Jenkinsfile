pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o output main.cpp'
                echo 'Build Stage Successful'
            }
        }
        stage('Test') {
            steps {
                sh './output'
                echo 'Test Stage Successful'
            }
        }
        stage('Deploy') {
            steps {
                sh 'git add main.cpp'
                sh 'git commit -m "Added working C++ file"'
                sh 'git push origin main'
                echo 'Deployment Successful'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
