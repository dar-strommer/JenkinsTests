pipeline {
    agent {
        kubernetes {
            label "main-${podLabel}"
            yamlFile 'base-agent.yaml'
            //nodeSelector "kubernetes.io/track=knomi"
        }
    }

    stages {
         stage('Compile') {
            steps {
                echo "Compiling..."
//                 sh "${tool name: 'mySbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt compile"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
//                 sh "${tool name: 'mySbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt test"
            }
        }
    }

}
