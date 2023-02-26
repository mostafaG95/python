pipeline {
    agent any

    stages {
        stage('CI') {
            steps {
                git 'https://github.com/mostafaG95/node-js'
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                sh """
                docker login -u ${USERNAME} -p ${PASSWORD}
                docker build . -f dockerfile -t mostafag95/projectt --network host
                docker push mostafag95/projectt
                """
                }
            }
        }
         stage('CD') {
            steps {
                git 'https://github.com/mostafaG95/node-js'
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                sh """
   
                """
                }
            }
        }
    }
}
