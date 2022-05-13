pipeline {
  agent any
    stages {
        stage("Tests") {
            steps {
              script{
                try {
                  sh "docker run --rm -v /var/jenkins_home/workspace/TestTaurus:/bzt-configs -v /var/jenkins_home/workspace/TestTaurus/reports:/tmp/artifacts blazemeter/taurus example.yml"
                } finally {
                  junit 'reports/report.xml'
                  cleanWs()
                }
              }
            }
        }
    }
}