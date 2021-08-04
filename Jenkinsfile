properties([parameters([choice(choices: ['main', 'feature', 'hostfix'], description: 'Select branch to build', name: 'branch')])])

node{
  stage('SCM Checkout'){
    echo "Pulling changes from branch ${params.branch}"
    git branch: "${params.branch}", url: 'https://github.com/ashishtkumar/my-app'
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
