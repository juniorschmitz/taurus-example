pipeline {
    agent {
        docker {
            image "blazemeter/taurus"
            args '--entrypoint='
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