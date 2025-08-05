pipeline {
    agent any

    parameters {
        choice(
            name: 'branch',
            choices: ['main', 'dev', 'bug_fixes'],
            description: 'Select the Git branch to build'
        )
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: "${params.branch}", git credentialsId: 'Github', url: 'git@github.com:takopachi/jenkins-test.git'
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

    post {
        success {
            echo 'Build was successful! (^_^)'
            bat 'echo Success! > success.txt'
        }

        failure {
            echo 'Build failed. (X_X)'
            bat 'echo Failed! > failed.txt'
        }

        always {
            echo 'This runs regardless of success or failure. (-_-)'
            bat 'echo %DATE% %TIME% > always.txt'
        }
    }
}
