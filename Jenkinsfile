pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', git 'https://github.com/kmuddise/my-jenkins-demo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                sh 'chmod +x deploy.sh'
                sh './deploy.sh'
            }
        }
    }
}
