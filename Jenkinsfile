pipeline {
    agent any
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }
    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url:'https://github.com/conormurph1/lbg-vat-calculator.git'
            }
        }
        stage('Build') {
            steps {
                withSonarQubeEnv('sonar-qube-1'){
                    sh 'mvn clean package sonar:sonar'
                }
            }
        }
    }
}
