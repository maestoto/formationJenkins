pipeline {
    agent any

    environment {
        URL = 'https://github.com/maestoto/formationJenkins.git' 
        CREDENTIAL_ID = "maestoto_formJenkins"
    }

    stages {
        stage('recuperation rgit') {
            steps {
                checkout scm: scmGit(branches: [[name: 'main']],
                userRemoteConfigs: [
                         [ 
                            credentialsId: "${CREDENTIAL_ID}"
                           url: "${URL}" ]
                     ]) 
                     // affiche les variables de jenkins
                     sh "printenv"
            }
        }
        stage('test') {
            steps {
                sh 'ls -al '
                
            }
        }
        stage('deploy') {
            steps {
                echo "deploy "
            }
        }
    }
}
