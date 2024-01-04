pipeline {
    agent any

    stages {
        stage('Check GitHub Access') {
            steps {
                script {
                    // GitHub repository details
                    def githubUser = 'oxblixxx'
                    def githubRepo = 'https://github.com/oxblixxx/snipe-it/'
                    def githubCredentialId = 'GIT_PAT'

                    // Checkout the GitHub repository
                    checkout([$class: 'GitSCM',
                              branches: [[name: '*/main']],
                              doGenerateSubmoduleConfigurations: false,
                              extensions: [[$class: 'CleanBeforeCheckout']],
                              userRemoteConfigs: [[credentialsId: githubCredentialId, url: "https://${githubUser}@github.com/${githubUser}/${githubRepo}.git"]]])

                    // Echo a message to confirm successful checkout
                    echo "Successfully checked out the GitHub repository."
                }
            }
        }
    }
}
