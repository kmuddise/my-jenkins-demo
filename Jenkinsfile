pipeline {
    agent any

    environment {
        // Optional: Set python path or virtualenv
        PYTHONUNBUFFERED = 1
    }

    stages {
        stage('Checkout') {
            steps {
                // Use HTTPS if you're not using SSH keys properly
                git url: 'https://github.com/kmuddise/my-jenkins-demo.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install --upgrade pip'
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                sh 'nohup python3 app.py > app.log 2>&1 &'
            }
        }
    }
}


