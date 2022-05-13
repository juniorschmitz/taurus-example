pipeline {
    agent {
        docker {
            image "blazemeter/taurus"
        }
    }
    stages {
        stage("Build") {
            steps {
                //
            }
        }
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