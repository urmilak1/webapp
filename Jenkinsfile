pipeline {
    agent any
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
        stage("build & SonarQube analysis") {
            steps {
              withSonarQubeEnv('sonarqube-8.9.9.56886') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          stage("Quality Gate") {
            steps {
                             
                waitForQualityGate abortPipeline: true
               }
          }
        }
}
        


    

