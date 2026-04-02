pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Pre-commit hooks') {
            steps {
                sh '''
                    pip install pre-commit --quiet
                    pre-commit run npm-groovy-lint --all-files
                '''
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
