pipeline {
    agent any
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
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