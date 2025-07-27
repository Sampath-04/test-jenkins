pipeline {
    agent any
    
    environment {
        NODE_VERSION = '18'
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Starting build stage...'
                
                echo 'Build completed successfully!'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Starting test stage...'
                
                echo 'Tests completed successfully!'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Starting deployment stage...'
                
                script {
                    if (env.BRANCH_NAME == 'master' || env.BRANCH_NAME == 'main') {
                        sh '''
                            # Production deployment
                            echo "Deploying to production..."
                            
                            # Example deployment commands:
                            # - Copy build files to server
                            # - Update container image
                            # - Deploy to cloud platform
                            
                            # For now, just echo the deployment
                            echo "Application deployed successfully to production!"
                        '''
                    } else {
                        sh '''
                            # Staging deployment for other branches
                            echo "Deploying to staging environment..."
                            echo "Staging deployment completed!"
                        '''
                    }
                }
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline execution completed.'
            
            // Clean up workspace
            cleanWs()
        }
        
        success {
            echo 'Pipeline executed successfully!'
            
            // Send success notifications (email, Slack, etc.)
            // emailext (
            //     subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
            //     body: "Good news everyone! The pipeline succeeded.",
            //     to: "${env.CHANGE_AUTHOR_EMAIL}"
            // )
        }
        
        failure {
            echo 'Pipeline failed!'
            
            // Send failure notifications
            // emailext (
            //     subject: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
            //     body: "Bad news everyone! The pipeline failed.",
            //     to: "${env.CHANGE_AUTHOR_EMAIL}"
            // )
        }
    }
}
