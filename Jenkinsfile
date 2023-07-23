pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'build'
                sh 'mvn clean package'
            }
        }
        stages {
          stage("build & SonarQube analysis") {
            steps {
              withSonarQubeEnv('My SonarQube Server') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
        /*stage('UAT') {
            steps {
                echo 'UAT'
            }
        }
        stage('staging') {
            steps {
                echo 'staging'*/
            }
        }
        stage('prod') {
            steps {
                echo 'production'
            }
        }
    }
    post { 
        success {
            echo 'success'
        }
        failure {
             echo 'failure'
        }
        always {
             echo 'King Suraj '
        }
    }
}