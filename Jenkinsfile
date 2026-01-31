pipeline {
    agent any

    environment {
        APP_NAME = "CI Demo App"
    }

    parameters {
        string(name: 'VERSION', defaultValue: '1.0', description: 'App version')
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                ech "Building ${APP_NAME}"
                ech "Version: ${params.VERSION}"
                 'ls -la'
            }
        }

        stage('Package') {
            steps {
                sh 'tar -cvf app.tar index.html'
            }
        }

    }

    post {
        success {
            echo 'Build Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
        always {
            echo 'Pipeline Finished'
        }
    }
}
