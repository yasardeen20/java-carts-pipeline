pipeline {
    agent any

    tools {
        maven 'maven 3.6.1'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn clean compile' 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                echo 'Deploying....'
                sh 'mvn -DskipTests package' 
                 archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
    }
}