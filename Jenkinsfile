pipeline {
    agent {
        label "AGENT-1"
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }    
    environment{
        DEPLOY_TO =  'production'
        GREETING = 'Good Morning'
    }
    stages {
        stage('Build') {
            steps {
                sh "echo this is build"
                sh 'env'
            }
        }
        stage('Test') {
            steps {
                sh "echo this is test"
                sh 'sleep 10'                
            }
        }
        stage('Deploy') {
            steps {
                sh "echo this is deploy"
            }
        }
        stage("print params"){
            steps{
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
                echo "Hello"
                --- fasdf



            }
        }        

    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'I will run when pipeline is success'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
    }    
}
