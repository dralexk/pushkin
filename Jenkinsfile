pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cat feeling.txt'
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
