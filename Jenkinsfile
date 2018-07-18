def notifySlack(String buildStatus = 'STARTED') {
    // Build status of null means success.
    buildStatus = buildStatus ?: 'SUCCESS'

    def msg = "Terraform job is completed"
    def username = "$(BUILD_USER_ID)"
    echo $(BUILD_USER_ID)
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
