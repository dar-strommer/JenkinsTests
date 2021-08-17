library 'library@master'

pipeline {
    agent {
        kubernetes {
            label "main-es-dispatcher"
            yamlFile 'base-agent.yaml'
        }
    }

    stages {
       stage('Clone') {
            steps {
                echo "Not implemented Clone..."
            }
        }
       stage('Checkout') {
            steps {
                echo "Not implemented Checkout..."
            }
        }
       stage('Build') {
            steps {
                container("sbt"){
                    echo "Running command: \"sbt \'all clean compile test:compile it:compile\'\""
                    sh label: 'Compiling', script: 'sbt \'all clean compile test:compile it:compile\''
                }

            }
        }
       stage('Test') {
            steps {
                echo "Not implemented Test..."
            }
        }
       stage('Stryker') {
            steps {
                echo "Not implemented Stryker..."
            }
        }
       stage('Publish') {
            steps {
                echo "Not implemented Publish..."
            }
        }
       stage('Deploy') {
            steps {
                echo "Not implemented Deploy..."
            }
        }
    }
    post {
        always {
            sendSlackNotification(slackUserId: "#h3-core")
        }
    }

}
