pipeline {
    agent any

       options {
        timeout(time: 10, unit: 'SECONDS') 
    }
     triggers {
        cron('59 17 * * *')
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
    }
}


    

