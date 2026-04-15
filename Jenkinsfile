pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'JDK21'
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
    post {
        success {
            echo 'Build thành công'
        }
        failure {
            echo 'Build thất bại'
        }
    }
}
