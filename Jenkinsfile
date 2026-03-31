pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                ech 'Building the application...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
    }
    
    // This post block runs at the very end of the pipeline
    post {
        always {
            echo 'This will always run, regardless of success or failure.'
            // Example: archiveArtifacts artifacts: 'target/*.jar'
        }
        success {
            echo 'The pipeline succeeded! Time to celebrate.'
        }
        failure {
            echo 'The pipeline failed. Sending alert...'
            // Example: mail to: 'dev-team@example.com', subject: 'Build Failed'
        }
        changed {
            echo 'The pipeline state has changed since the last run.'
        }
        cleanup {
            echo 'Cleaning up the workspace...'
            cleanWs() // Requires the Workspace Cleanup plugin
        }
    }
}
