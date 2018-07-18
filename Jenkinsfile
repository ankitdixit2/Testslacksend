def notify(text) {  
  slackSend (channel: jenkinsbuilds, message: "Terraform testing", teamDomain: "eiaconsultingsandbox", token: "ckQriaqQoctcd7RiNdbjCu8U")  
}

node {
    stage("Post to Slack") {
        notify('testgg')
    }
}
