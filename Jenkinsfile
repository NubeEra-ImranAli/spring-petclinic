pipeline {
    agent any
    tools {
        maven 'mvvn399' // Replace with your Maven installation name
    }
    stages {
        stage('giiiint') {
            steps {
                git branch: 'main', url: 'https://github.com/NubeEra-ImranAli/spring-petclinic.git'
            }
        }
        stage('mmkm') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('clean') {
            steps {
                sh 'mvn clean'    
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'    
            }
        }
    }
}
