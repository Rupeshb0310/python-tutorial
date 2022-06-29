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
                    sonar.projectKey=sq
                    sonar.projectName=sq
                    sonar.projectVersion=1.0
                    sonar.sources=
                    sonar.language=py
                    sonar.sourceEncoding=UTF-8
                     # Test Results
                    sonar.python.xunit.reportPath=nosetests.xml
                    # Coverage
                    sonar.python.coverage.reportPath=coverage.xml
                    # Linter (https://docs.sonarqube.org/display/PLUG/Pylint+Report)
                    #sonar.python.pylint=/usr/local/bin/pylint
                    #sonar.python.pylint_config=.pylintrc
                    #sonar.python.pylint.reportPath=pylint-report.txt
                    """
                }
            }
        }
       
    }
}
