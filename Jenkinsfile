pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        echo 'Running build automation'
        sh './gradlew build --no-daemon'
        archiveArtifacts artifacts: 'dist/trainSchedule.zip'
      }
      
    }
    stage ('Slack Notification'){
      steps {
        slackSend channel: '#jenkins-pipeline-demo', 
          color: 'good', 
          iconEmoji: ':ghost:',
          message: 'This message is sent from Jenkins', 
          teamDomain: 'https://hooks.slack.com/services/', 
          tokenCredentialId: 'slack-demo', 
          username: 'webhookbot'
      }
    
    }
  }
}
