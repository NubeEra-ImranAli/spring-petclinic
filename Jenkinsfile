pipeline {
    agent any

    environment {
        SONAR_TOKEN = credentials('sonar-token')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://oauth: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@github.com/NubeEra-ImranAli/spring-petclinic.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('SonarCloud Analysis') {
            steps {
                withEnv(["SONAR_TOKEN=${SONAR_TOKEN}"]) {
                    sh """
                      mvn sonar:sonar \
                        -Dsonar.projectKey=NubeEra-ImranAli_spring-petclinic \
                        -Dsonar.organization=nubeera-imran-sonar \
                        -Dsonar.host.url=https://sonarcloud.io \
                        -Dsonar.login=${SONAR_TOKEN}
                    """
                }
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
