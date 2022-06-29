pipeline {
    agent any
    stages {
        stage('Clone sources') {
            steps {
                git url: 'https://github.com/Rupeshb0310/python-tutorial.git'
            }
        }
        stage('SonarQube analysis') {
            steps {
                ScannerHome = tool 'Sonarqube-9.5'
                withSonarQubeEnv('Sonarqube-9.5') {
                    sh """
               
                    ${scannerHome}/bin/sonar-scanner
                    
                    """
                }
            }
        }
       
    }
}
