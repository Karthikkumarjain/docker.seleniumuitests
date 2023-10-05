pipeline{

    agent any

    stages{
     tools {
            maven 'Maven 3.8.6'
            jdk 'Java 17.0.4.1'
        }

        stage('Build Jar'){
            steps{
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Build Image'){
            steps{
                sh 'docker build -t=karthikkumarjain/seleniumondocker .'
            }
        }

        stage('Push Image'){
            environment{
                // assuming you have stored the credentials with this name
                DOCKER_HUB = credentials('dockerhub-credentials')
            }
            steps{
                // There might be a warning.
                sh 'docker login -u ${DOCKER_HUB_USR} -p ${DOCKER_HUB_PSW}'
                sh 'docker push karthikkumarjain/seleniumondocker'
            }
        }

    }

    post {
        always {
            sh 'docker logout'
        }
    }

}