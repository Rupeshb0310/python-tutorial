pipeline {
    agent any
    stages {
        stage('Clone sources') {
            steps {
                git url: 'https://github.com/Rupeshb0310/python-tutorial.git'
            }
        }
        stage('SonarQube analysis') {
            def scannerHome = tool 'Sonarqube-9.5';
            withSonarQubeEnv('Sonarqube-9.5') {
              sh "${scannerHome}/bin/sonar-scanner \
              -D sonar.login=admin \
              -D sonar.password=0000 \
              -D sonar.projectKey=sq \
              -D sonar.host.url=http://localhost:9000/"
    }
  }
       
    }
}
