pipeline {
    agent {
        docker {
            image "blazemeter/taurus"
        }
    }
    stages {
        stage("Build") {
          echo "Rodando build..."
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