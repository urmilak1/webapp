pipeline {
    agent any
    
       options {
        timeout(time: 50, unit: 'MINUTES') 
    }
     triggers {
        cron('25 18 * * *')
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
        stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('sonarqube-8.9.9.56886') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
          stage("Quality Gate") {
            steps {
                             
                waitForQualityGate abortPipeline: true
               }
          }
        post {
        always {
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}


    

