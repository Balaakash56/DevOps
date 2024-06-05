pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    def mvnHome = tool 'maven' // Assumes Maven is installed and configured in Jenkins
                    sh "'${mvnHome}/bin/mvn' clean install"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    def mvnHome = tool 'maven'
                    sh "'${mvnHome}/bin/mvn' test"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the application...'
                    // Add deployment steps here
                }
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
