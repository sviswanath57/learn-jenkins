pipeline {
    agent any
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    // parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Viswanth S', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    // }
    environment { 
        CC = 'clang'
    }
    stages {
        stage('Example') {
            steps {
                echo 'Hello this devops'
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
        // stage("check parameters"){
        //     steps{
        //         sh """
        //         echo "Hello ${params.PERSON}"

        //         echo "Biography: ${params.BIOGRAPHY}"

        //         echo "Toggle: ${params.TOGGLE}"

        //         echo "Choice: ${params.CHOICE}"

        //         echo "Password: ${params.PASSWORD}"
        //         """
        //     }
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