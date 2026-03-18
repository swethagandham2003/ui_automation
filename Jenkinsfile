pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/swethagandham2003/ui_automation.git', branch: 'main'
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
                sh 'pytest tests/ --junitxml=report.xml'
            }
        }

        stage('Archive reports') {
            steps {
                junit 'report.xml'
            }
        }
    }
}
