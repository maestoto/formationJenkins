pipeline {
    agent any

    environment {
        URL_GIT = 'https://github.com/maestoto/formationJenkins.git' 
        CREDENTIAL_ID = "maestoto_formJenkins"
    }

    stages {
        stage('recuperation git') {
            steps {
                checkout  scm: scmGit([
                    $class: 'GitSCM',
                    branches: [[name: 'main']],
                    userRemoteConfigs: [
                         [ 
                            credentialsId: "${CREDENTIAL_ID}"
                           url: "${URL}" ]
                     ]
                     ]) 
                // git branch: 'main',
                //     credentialsId: "${CREDENTIAL_ID}",
                //     changelog: false,
                //     url: "${URL_GIT}"
                
                // affiche les variables de jenkins
                sh "printenv"
                sh "chmod +x mvnw"
                sh "./mvnw clean package spring-boot:repackage -Dmavent.test.skip=true"
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
