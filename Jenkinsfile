pipeline {
    agent { label 'Jenkins-Agent'}
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage("Cleanup Workspace"){
            steps {
                cleanWs()
            }
        }
        stage("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'GitHub', url: 'https://github.com/vhskishore/register-app'
            }
        }
        stage("Build Application") {
            step {
                sh "mvn clean packag"
            }
        }
        stage("Test Application") {
            step {
                sh "mvn test"
            }
        }
    }
}
