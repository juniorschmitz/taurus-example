pipeline {
  agent any
    // agent {
        // docker {
            // image "blazemeter/taurus"
        // }
    // }
    stages {
        stage("Tests") {
            steps {
              script{
                try {
                  // sh "bzt example.yml"
                  sh "docker run --rm -v /var/jenkins_home/workspace/TestTaurus:/bzt-configs -v /var/jenkins_home/workspace/TestTaurus:/tmp/artifacts blazemeter/taurus example.yml"
                } finally {
                  junit 'report.xml'
                  cleanWs()
                }
              }
            }
        }
    }
}