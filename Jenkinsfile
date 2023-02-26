pipeline {
    agent any

    stages {
        stage('CI') {
            steps {
                git url: 'https://github.com/mostafaG95/python.git', branch: 'main'
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
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                sh """
   
                """
                }
            }
        }
    }
}
