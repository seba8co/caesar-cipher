pipeline {
    agent any

    stages {
        stage('GitHub Auth') {
            steps {
                echo 'Building..'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'b3224e54-6d87-4431-aeb6-3038968a9eeb', url: 'git@github.com:seba8co/caesar-cipher.git']]])
            }
        }
        stage('Test') {
            steps {
                echo 'Test the test'
		        sh './gradlew tasks --all'
            }
        }
        stage('Build') {
            steps {
                echo 'Build the Jar artifact'
		        sh './gradlew clean build'
            }
        }
        }
    }

