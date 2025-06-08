pipeline {
    agent any
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
                        echo "this is a Deply stage"
                    """
                }
            }
        }
    }
}