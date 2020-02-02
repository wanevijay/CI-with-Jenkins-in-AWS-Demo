pipeline {
    agent any
    stages {

        stage ('Exec Maven') {
            steps {
   sh "./mvn package"
}

  }

        stage('Sonarqube') {
                environment {
                    scannerHome = tool 'sonarqube'
                }
            steps {
                withSonarQubeEnv('sonarqube') {
                sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }

}
}
