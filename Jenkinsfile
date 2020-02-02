pipeline {
    agent any
    stages {

        stage ('Exec Maven') {
            steps {
                rtMavenRun (
                    tool: 'MAVEN_HOME', // Tool name from Jenkins configuration
                    pom: 'pom.xml',
                    goals: 'clean install',
                )
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
