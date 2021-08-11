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

}
