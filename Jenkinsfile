pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile'
            dir '.'
        }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    // Install project dependencies
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run Jest tests
                    sh 'npm test'
                }
            }
        }
    }
    post {
        always {
            junit 'reports/test-results.xml' // Ensure this path matches your Jest configuration
        }
    }
}
