pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Stage 1') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'staging') {
                        echo 'Running Stage 1 for Staging Environment...'
                        sh 'echo "Installing Staging dependencies / building Staging artifact"'
                    } else if (env.BRANCH_NAME == 'main') {
                        echo 'Running Stage 1 for Production (Main)...'
                        sh 'echo "Installing Production dependencies / building Production artifact"'
                    }
                }
            }
        }

        stage('Stage 2 - Staging Only') {
            when {
                branch 'staging'
            }
            steps {
                echo 'Running Stage 2 (Deploying to Staging Server)...'
                sh 'echo "Deploy to Staging completed"'
            }
        }

        stage('Stage 2 - Main Only') {
            when {
                branch 'main'
            }
            steps {
                echo 'Running Stage 2 (Deploying to Production Server)...'
                sh 'echo "Deploy to Main completed"'
            }
        }
    }

    post {
        always {
            echo "Pipeline completed for branch: ${env.BRANCH_NAME}"
        }
    }
}