pipeline {
    agent any
   
    parameters {
        
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    }
    stages {
        stage('Dev') {
            steps {
                echo 'Dev Environment'
                sh 'echo "The person name is.........${name}"'
            }
        }
        stage('Test') {
            environment{
                city= "bangalore"
            }
            steps {
                
                echo 'Test Environment'
                sh 'echo "${name}"'
                sh 'echo "${city}"'
            }
        }
          stage('Terraform Infrastrcuture creating') {
              input {
                message "Should we continue?"
                ok "Yes, we should."
            }
            steps {
                echo 'Executing terraform code'
                
                
            }
        }
        stage('Prod') {
         
            steps {
                echo 'Prod Environment'
                sh 'echo "${name}"'
                echo "Choice: ${params.CHOICE}"
            }
        }
        stage('parameters') {
            steps {
                echo 'Prod Environment'
                sh 'echo "${name}"'
                
            }
        }
        stage('Environment variables') {
            steps {
                sh 'echo "${BUILD_DISPLAY_NAME}"'
                sh 'echo "${name}"'
                sh 'pwdd'
            }
        }
        
    }
    post { 
            always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'I will always say Hello again when it is falure!'
        }
        }
}
