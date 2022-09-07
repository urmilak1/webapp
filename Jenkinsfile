pipeline {
    agent any
    stages {

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
        


    

