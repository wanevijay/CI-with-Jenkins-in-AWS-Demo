pipeline {
    agent any
    stages {

        stage ('Exec Maven') {
            steps {
   sh "mvn package sonar:sonar"
}

  }

        stage ("status to slack')  {
               steps{
                slackSend channel: 'jenkins-test', color: 'good', message: 'Message from Jenkins Pipeline'   
               }
               }
}
}
