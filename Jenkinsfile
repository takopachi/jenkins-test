pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git credentialsId: 'Github', url: 'git@github.com:takopachi/jenkins-test.git'
            }
        }

        stage('Read File') {
            steps {
                bat 'type file.txt'
            }
        }

        stage('Run Python Script') {
            steps {
                bat '"C:\\Users\\Lim Song Lip\\AppData\\Local\\Programs\\Python\\Python311\\python.exe" main.py'
            }
        }
    }
}
