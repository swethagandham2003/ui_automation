pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/swethagandham2003/ui_automation.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh '''
                python3 -m pip install --upgrade pip
                python3 -m pip install -r requirements.txt
                '''
            }
        }

        stage('Run tests') {
            steps {
                sh 'pytest'
            }
        }
    }
}
