pipeline {
    agent {
        docker {
            image 'python:3.9'  // Runs inside a Python 3.9 container
        }
    }

    stages {
        stage('Step 1: Checkout Code from GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/python-jenkins-webapp.git'
            }
        }

        stage('Step 2: Install Dependencies') {
            steps {
                script {
                    sh 'pip install flask'
                }
            }
        }

        stage('Step 3: Run Flask App') {
            steps {
                script {
                    sh 'nohup python app.py > output.log 2>&1 &'
                }
            }
        }

        stage('Step 4: Verify App is Running') {
            steps {
                script {
                    sh 'curl -s http://localhost:5000'
                }
            }
        }
    }
}

