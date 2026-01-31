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
                eho "Building ${APP_NAME}"
                eho "Version: ${params.VERSION}"
                h 'ls -la'
            }
        }

        stage('Package') {
            steps {
                 'tar -cvf app.tar index.html'
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
