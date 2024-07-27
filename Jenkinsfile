pipeline {
    agent any
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
    }
    environment { 
        CC = 'clang'
    }
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
        stage("building"){
            steps {
                echo "building the app"
            }
        }
        stage("environemt variable check"){
            steps{
                sh """
                    echo "Service user is $CC"'
                    // sh 'echo "Service password is $SERVICE_CREDS_PSW"'
                    // sh 'curl -u $SERVICE_CREDS https://myservice.example.com'
                    env
                """
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'If pipeline fails it will give this output'
        }
        success{
            echo 'If pipeline success it will give this output'
        }
    }
}