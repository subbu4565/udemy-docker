/* groovylint-disable GStringExpressionWithinString */
pipeline {
    agent {
        docker {
            image 'maven:3.2.3-jdk-8-onbuild'
            args '--user root -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
            stage('maven-test') {
                steps {
                    sh 'mvn -version'
                }
            }

            stage('gitcheckout') {
            steps {
                git branch: 'main', url: 'https://github.com/subbu4565/udemy-docker.git'
                sh 'echo success'
            }
            }
            stage('build and test') {
            steps {
                sh 'ls -ltr'
                sh 'cd . && mvn clean package'
            }
            }
      
        }
}