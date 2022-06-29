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
                
                withSonarQubeEnv('Sonarqube-9.5') {
                    sh """
               
                    /opt/Sonarqube-9.5/bin/sonar-scanner
                    
                    """
                }
            }
        }
       
    }
}
