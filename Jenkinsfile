pipeline {
    // agent any
    agent{
        label 'agent'
    }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
    }
    environment { 
        CC = 'clang'
    }
    stages {
        stage('Example') {
            steps {
                echo 'Hello this devops - jenkinsosss'
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
                    echo "Service user is $CC"
                    env
                """
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Devops again!'
        }
        failure{
            echo 'If pipeline fails it will give this output'
        }
        success{
            echo 'If pipeline success it will give this output'
        }
    }
}