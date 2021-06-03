pipeline{
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('tes'){
            steps{
                sh 'echo lagi tes'
            }
        }
        stage('Build-react'){
            steps{
                sh 'echo build react'
                sh 'npm run build'
            }
        }
        stage('Build-image'){
            steps {
                sh 'echo lagi build'
                sh 'docker build -t dino96112/react .'
            }
        }
        stage('Deliver'){
            steps{
                sh "docker container rm --force jc16-react"
                sh "docker run -d --name jc16-react -p 8181:80 dino96112/react"
            }
        }
    }
}