def notifySlack(String buildStatus = 'STARTED') {
    // Build status of null means success.
    buildStatus = buildStatus ?: 'SUCCESS'
    
    def msg = "${buildStatus}: AWS EC2 VMs are created"

    slackSend(message: msg)
}

node {
    
    try {
      
        notifySlack()

        // Existing build steps.
    } catch (e) {
        currentBuild.result = 'FAILURE'
        throw e
    } 
}
