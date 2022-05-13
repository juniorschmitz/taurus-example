pipeline {
    agent {
        docker {
            image "blazemeter/taurus"
        }
    }
    stages {
        stage("Tests") {
            steps {
              script{
                try {
                  sh "bzt example.yml"
                } finally {
                  junit 'report.xml'
                  cleanWs()
                }
              }
            }
        }
    }
}