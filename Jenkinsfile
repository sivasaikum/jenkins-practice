pipeline {
    agent { label 'AGENT-1'}
    environment {
        PROJECT = 'EXPENSE'
        COMPONENT = 'BACKEND'
    }
    options {
        disableConcurentBuilds()
        timeout(time: 10 , unit: 'SECONDS')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo "hello this is a build stage"
                        echo " This is a $PROJECT project"
                        sleep 15
                    """
                }
            }
        }

        stage ('Test') {
            steps {
                script {
                    sh """
                        echo "this is a Test stage"
                    """
                }
            }
        }

        stage ('Deploy') {
            steps {
                script {
                    sh """
                        echo "this is a Deploy stage"
                        
                    """
                }
            }
        }
        
    }
    post {
        always {
           echo " This is a hello-pipeline build "
        }
        failure {
            echo " This is a hello-pipeline build is failed for some reason"
        }
        success {
            echo " This is a hello-pipeline build is Successed . Thanks ! "
        }
    }
}