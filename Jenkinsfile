pipeline {
    agent any

    stages {
        stage('Stage 1') {
            steps {
                echo 'Running Stage 1...'
                sh 'echo "Stage 1 process completed"'
            }
        }

        stage('Stage 2') {
            steps {
                echo 'Running Stage 2...'
                sh 'echo "Stage 2 process completed"'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }
    }
}