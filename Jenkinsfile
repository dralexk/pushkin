pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {
                    def fileContents = readFile "feeling.txt"
                    echo fileContents
                    assert fileContents.contains("better")
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
