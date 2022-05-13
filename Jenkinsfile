pipeline {
    agent {
        dockerfile {
            image "blazemeter/taurus"
        }
    }
    stages {
        stage("Build") {
            steps {
                sh "nope"
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