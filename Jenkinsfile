pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {
                    def fileContents = new File('feeling.txt').text
                    echo fileContents
                }
            }
        }
    }
    post {
        success {
            githubNotify description: 'This is a Jenkins notification',  
                status: 'SUCCESS',  
                repo: "pushkin", 
                account: "dralexk",
                credentialsId: "GitHub-Creds",
                sha: GIT_COMMIT
        }
    }
}
