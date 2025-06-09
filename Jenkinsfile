pipeline {
    agent { label 'AGENT-1'}
    environment {
        PROJECT = 'ROBOSHOP'
        COMPONENT = 'BACKEND'
        branch = 'production'
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 90 , unit: 'SECONDS')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        sleep 10
                        echo "hello this is a build stage"
                        echo " This is a $PROJECT project"
                        
                        echo "Hello ${params.PERSON}"

                        echo "Biography: ${params.BIOGRAPHY}"

                        echo "Toggle: ${params.TOGGLE}"

                        echo "Choice: ${params.CHOICE}"

                        echo "Password: ${params.PASSWORD}"
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
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            when {
                branch 'QA'
            }
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