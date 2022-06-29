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
                sh '''
                #!/bin/bash
                docker run --rm --net=host -v ${PWD}:/sq sonarsource/sonar-scanner-cli sonar-scanner -D sonar.projectBaseDir=/sq
                '''
                   
                
            }
        }
       
    }
}
