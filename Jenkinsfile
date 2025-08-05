pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', credentialsId: 'your-creds-id', url: 'git@github.com:takopachi/jenkins-test.git'
            }
        }

        stage('Read File') {
            steps {
                bat 'type file.txt'
            }
        }

        stage('Run Python Script') {
            steps {
                bat 'python main.py'
            }
        }
    }
}
