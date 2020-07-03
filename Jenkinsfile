// Hello-world build pipeline
pipeline {
    agent any

    tools {
        maven "Maven 3.6.3"
    }
    options {
        parallelsAlwaysFailFast()
    }
    stages {
        stage('Build Conference App') {
            steps {
                // Run the maven build
                sh "mvn clean install package"
            }
        }
        stage('Parallel Stage') {
            parallel {
                stage('Build Conference App Checkstyle') {
                    steps {
                        // Run the maven build with checkstyle
                        sh "mvn clean package checkstyle:checkstyle"
                    }
                }
                stage('Build Conference App Sonarqube') {
                    steps {
                        withSonarQubeEnv('SonarQube') {
                            sh "mvn  clean package sonar:sonar -Dsonar.host_url=$SONAR_HOST_URL "
                            }
                        }
                    }
                }
            }
        }
    }