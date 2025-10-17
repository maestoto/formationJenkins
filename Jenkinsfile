pipeline {
    agent any

    stages {
        stage('recuperation rgit') {
            steps {
                checkout scm: scmGit(branches: [[name: 'main']],
                userRemoteConfigs: [
                         [ 
                            credentialsId: 'maestoto_formJenkins',
                           url: 'https://github.com/maestoto/formationJenkins.git' ]
                     ]) 
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
