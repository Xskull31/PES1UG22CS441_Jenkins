pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '/main']],
                    userRemoteConfigs: [[url: 'https://github.com/JatinSharma159/Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG19CS5159-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
