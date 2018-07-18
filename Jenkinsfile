def notifySlack(String buildStatus = 'STARTED') {
    // Build status of null means success.
    buildStatus = buildStatus ?: 'SUCCESS'
    
    def msg = "${buildStatus}: `${env.JOB_NAME}` #${env.BUILD_NUMBER}:\n${env.BUILD_USER_ID}"

    slackSend(message: msg)
}

node {
    
     def userr
        stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        userr = "$BUILD_USER_ID"
        sh "echo $userr"
    }
    try {
      
        notifySlack()

        // Existing build steps.
    } catch (e) {
        currentBuild.result = 'FAILURE'
        throw e
    } 
}
