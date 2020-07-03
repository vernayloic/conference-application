// Hello-world build pipeline
pipeline {
    agent any

    tools {
        maven "Maven 3.6.3"
    }
    stages
    {
        stage('Build Conference App') {
           steps{
              // Run the maven build
              sh "mvn clean install package"
           }
       }
       stage('Build Conference App SonarQube') {
                  steps{
                     withSonarQubeEnv('SonarQube') {
                     sh "mvn clean package sonar:sonar -Dsonar.host_url=$SONAR_HOST_URL"
                     }
                  }
               }
    }
}