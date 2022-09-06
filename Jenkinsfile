pipeline {
    agent any

       options {
        timeout(time: 10, unit: 'SECONDS') 
    }
     triggers {
        cron('2 18 * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Example') {
            steps {
                echo 'Hello World'
            }
    }
}


    

