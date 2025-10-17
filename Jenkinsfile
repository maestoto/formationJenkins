pipeline {
    agent any

    environment {
        URL_GIT = 'https://github.com/maestoto/formationJenkins.git' 
        CREDENTIAL_ID = "maestoto_formJenkins"
    }

    parameters {
        string(name:"version", description: "version")
        choice(name:"environnement", choices:["test","dev", "prod"] , description: "environement")
    }

    stages {
        stage('recuperation git') {
            steps {
                // checkout ([
                //     $class: 'GitSCM',
                //     branches: [[name: 'main']],
                //     userRemoteConfigs: [
                //          [ 
                //             credentialsId: "${CREDENTIAL_ID}"
                //            url: "${URL_GIT}" ]
                //      ]
                //      ]) 
                git branch: 'main',
                    credentialsId: "${CREDENTIAL_ID}",
                    changelog: false,
                    url: "${URL_GIT}"
                
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
                echo "deploy ${params.environment} "
            }
        }
    }
}
