pipeline {
    agent any

    tools {
        nodejs 'node-latest' // Asegúrate de configurar esto en Jenkins -> Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        // Descomenta esto si tienes tests configurados
        // stage('Test') {
        //     steps {
        //         sh 'npm test'
        //     }
        // }
    }

    post {
        always {
            cleanWs()
        }
    }
}
