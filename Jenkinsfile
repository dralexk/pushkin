pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        success {
            githubNotify description: 'This is a shorted example',  
                status: 'SUCCESS', 
                credentialsId: '08ad1b4fa04b37ca9fe53edd49d74e943b6e4972', 
                repo: "pushkin", 
                account: "dralexk"
        }
    }
}
