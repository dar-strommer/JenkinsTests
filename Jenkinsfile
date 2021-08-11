pipeline {
    agent any

    stages {
         stage('Compile') {
            steps {
                echo "Compiling..."
                sh "${tool name: 'mySbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt compile"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "${tool name: 'mySbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt test"
            }
        }
    }

    post {
        always {
            emailext
                subject: "${env.CHANGE_BRANCH ?: env.BRANCH_NAME}: ${currentBuild.currentResult}",
                body: "More details: ${env.BUILD_URL}",
                recipientProviders: [culprits()], // Send email to everyone who committed since the last successful build.
                replyTo: 'ilan.shochat@sparkbeyond.com'
        }
    }
}
