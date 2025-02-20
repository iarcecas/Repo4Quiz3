pipeline {
    agent any 
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/iarcecas/Repo4Quiz3.git'
            }
        }
        stage('Build') {
            steps {
                sh './mvnw clean install'
            }
        }
        stage('Test with Jacoco') {
            steps {
                sh './mvnw test'
            }
        }
        stage('Generate Jacoco Report') {
            steps {
                sh './mvnw jacoco:report'
            }
        }
    }
    triggers {
        cron('*/3 * * * 4')
    }
}
