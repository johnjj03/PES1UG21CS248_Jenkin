pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/johnjj03/PES1UG21CS248_Jenkin.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ -o hello ./main/hello.cp'
            }
        }

        stage('Test') {
            steps {
                sh './hello'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying..."
            }
        }
    }

    post {
        failure {
            echo "Pipeline Failed"
        }
    }
}
