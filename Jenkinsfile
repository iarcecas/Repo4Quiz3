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
                bat './mvnw clean install'
            }
        }
        stage('Test with Jacoco') {
            steps {
                bat './mvnw test'
            }
        }
        stage('Generate Jacoco Report') {
            steps {
                bat './mvnw jacoco:report'
            }
        }
    }
    triggers {
        cron('*/3 * * * 4')
    }
}
