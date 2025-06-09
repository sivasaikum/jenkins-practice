pipeline {
    agent { label 'AGENT-1'}
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo "hello this is a build stage"
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
                        oydfgjkk
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