pipeline {
    agent any
    stages {
        stage('Clone sources') {
            steps {
                git url: 'https://github.com/Rupeshb0310/python-tutorial.git'
            }
        }
        stage('SonarQube analysis') {
            def scannerHome = tool 'sonarqube';
            withSonarQubeEnv('sonarqube') {
              sh "${scannerHome}/bin/sonar-scanner \
              -D sonar.login=admin \
              -D sonar.password=0000 \
              -D sonar.projectKey=sq \
              
              -D sonar.host.url=http://localhost:9000/"
    }
  }
       
    }
}
