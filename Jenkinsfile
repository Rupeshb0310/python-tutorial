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
                    sonar.projectKey=sq
                    sonar.projectName=sq
                    sonar.projectVersion=1.0
                    sonar.sources=
                    sonar.language=py
                    sonar.sourceEncoding=UTF-8
                            
                     sonar.python.xunit.reportPath=nosetests.xml
                            
                    sonar.python.coverage.reportPath=coverage.xml
                   
                }
            }
        }
       
    }
}
