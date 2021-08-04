node{
  stage('SCM Checkout'){
    git branch: 'main', url: 'https://github.com/ashishtkumar/my-app'
  }
  stage('Compile Package'){
    def mvnHome=tool name: 'maven3', type: 'maven'
    sh "${mvnHome}/bin/mvn package" 
  }
  stage('Email Notificaion'){
    mail bcc: '', body: '''Hi, Welcome to Jenkins email address.
          Thanks
          Jenkins''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'ashishvkumar7@gmail.com'
  }
  stage('Slack Notificaion'){
    slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#test', color: 'good', message: 'Hi! Welcome to Jenkins', 
      teamDomain: 'AppDev', tokenCredentialId: 'slack'
  }
}
