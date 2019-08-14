pipeline{
    agent any
    stages {
        stage('test') {
            steps {
                echo "smee"
            }
        }
        stage ('Send UMB message'){
            steps{
                 sendCIMessage failOnError: false, \
                 messageContent: '''{ "msg" : "Hello from smee-job!" }''', \
                 messageProperties: 'testProp = SMEE_PROPERTY', \
                 messageType: 'ComponentBuildDone', \
                 overrides: [topic: 'VirtualTopic.qe.ci.jenkins'], \
                 providerName: 'Red Hat UMB'               
            }
        }
    }
}
