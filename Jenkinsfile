pipeline {
    agent { label 'AGENT-1'}
    stages {
        stage("Hello") {
            steps {
                script {
                    sh """
                        echo " Hello world "
                        echo "Testing"

                    """
                }
            }
        }
    }
}