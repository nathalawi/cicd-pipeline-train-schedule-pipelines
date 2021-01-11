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
        slackSend channel: '#jenkins-pipeline-demo', color: 'good', iconEmoji: ':ghost:', message: 'This message is sent from Jenkins', teamDomain: 'https://hooks.slack.com/services/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', username: 'webhookbot'
      }
    
    }
  }
}
