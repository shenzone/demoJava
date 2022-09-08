pipeline {
    agent {
        docker { image 'shenzone/javabuilder:1.0.1' }
    }
    stages {
        stage('Initial/Prepare') {
            steps {
                sh 'java --version'
                sh 'bash ./gradlew --version'
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'http://192.168.1.111:8080/DSQA/GitlabTest.git'
            }
        }
        stage('Version Bumper') {
            steps {
                sh 'java --version'

            }
        }
        stage('Build') {
            steps {
                sh 'bash gradlew build'
            }
        }
        stage('Sequential Test') {
            steps {
                sh 'bash gradlew test'

            }
        }
        stage('Parallel test') {
            steps {
                sh 'bash gradlew test'

            }
        }
        stage('Publish Test Result') {
            steps {
				junit '**/*.xml'
            }
        }
        stage('Publish Installer Package') {
            steps {
                sh 'echo ###Execute publish Stage.'

            }
        }
        stage('Clean') {
            steps {
                sh 'echo ###Execute Clean Stage.'

            }
        }
    }
}