node{
   stage('SCM Checkout'){
     git 'https://github.com/nagarajuchallagulla/my-app.git'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'Maven 3.5.2', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      Hari''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'nagarajuchallagulla@gmail.com'
   }
   stage('Slack Notification'){
       slackSend baseUrl: 'https://hooks.slack.com/services/',
       channel: '#jenkins-pipeline-demo',
       color: 'good', 
       message: 'Welcome to Jenkins, Slack!', 
       teamDomain: 'javahomecloud',
       tokenCredentialId: 'slack-demo'
   }
}
