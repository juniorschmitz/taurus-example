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
              sh "mv example.yml /home"
              dir(path: '/home') {
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
}