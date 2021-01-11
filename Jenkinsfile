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
         slackSend channel: '#﻿jenkins-pipeline-demo', 
           color: 'good', 
           message: 'Welcome to Jenkins Slack!', 
           teamDomain: 'https://hooks.slack.com/services/', 
           tokenCredentialId: 'slack-demo'
    
    }
  }
}
