pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {
                    def fileContents = readFile "feeling.txt"
                    echo fileContents
                    assert fileContents.contains("happy")
                }
            }
        }
    }
    post {
        success {
            githubNotify description: 'Jenkins reports success!',  
                status: 'SUCCESS',  
                repo: "pushkin", 
                account: "dralexk",
                credentialsId: "GitHub-Creds",
                sha: GIT_COMMIT
        }
        failure {
            githubNotify description: 'Jenkins reports failure!',  
                status: 'FAILURE',  
                repo: "pushkin", 
                account: "dralexk",
                credentialsId: "GitHub-Creds",
                sha: GIT_COMMIT
        }
            
    }
}
