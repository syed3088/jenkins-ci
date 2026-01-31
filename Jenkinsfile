pipeline {
    agent any

    environment {
        APP_NAME = "CI Demo App"
    }

    parameters {
        string(name: 'VERSION', defaulte: '1.0', description: 'App version')
    }

    stages {

        stage('Checkout') {
            steps {
                checkout
            }
        }

        stage('Build') {
            steps {
                echo "Buig ${APP_NAME}"
                echo "Vers: ${params.VERSION}"
                sh 'l'
            }
        }

        stage('Package') {
            steps {
                sh 'tar - app. index.html'
            }
        }

    }

    post {
        success {
            ec 'Build Succful!'
        }
        failure {
            ec 'Build Failed!'
        }
        always {
            ec 'Pipeline Finished'
        }
    }
}
