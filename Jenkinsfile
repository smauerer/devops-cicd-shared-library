@Library('my-shared-library@master') _

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    log.info 'checkout'
                }
                git credentialsId: 'GIT', url: 'https://gitlab.ballpark.altemista.cloud/aburkard/devops-cicd-demo-project'
            }
        }
        stage('Build') {
            steps {
                script {
                    log.warn 'Building with maven!'
                }
                sh 'mvn -B clean verify -DskipTests'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Results') {
            steps {
              junit '**/target/surefire-reports/TEST-*.xml'
              archive 'target/*.jar'
            }
        }
    }
}
