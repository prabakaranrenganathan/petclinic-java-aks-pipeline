pipeline {
    agent any

    tools {
        maven 'Maven 3.8.1' // make sure this Maven version is configured in Jenkins
    }
stages {
        stage('Checkout') {
            steps {
                git branch: 'prod', url: 'https://github.com/prabakaranrenganathan/my-petclinic-jenkins.git'
            }
        }
stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
stage('Archive') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
