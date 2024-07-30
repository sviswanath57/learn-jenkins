pipeline {
    agent any
    // agent{
    //     label 'agent'
    // }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
    }
    environment { 
        CC = 'clang'
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('parameters') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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