pipeline {
    agent any
    parameters {
        choice(name: 'BRANCH_NAME', choices: ['stable', 'dev', 'release'], description: '')
        booleanParam(name: 'executeTest', defaultValue: true, description: '')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo 'building from branch ${params.BRANCH_NAME}'
            }
        }
        stage('Test') {
            when {
                expression {
                     params.executeTest == true
                }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
