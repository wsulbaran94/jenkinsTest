import groovy.json.JsonSlurperClassic

def jsonParse(def json) {
  new groovy.json.JsonSlurperClassic().parseText(json)
}

pipeline {
  agent {
    label 'main'
  }
  evironment {
    appName = 'variable'
  }
  stages {
    stages("paso 1") {
      steps{
        script {
          sh "echo 'Hola mundo'"
        }
      }
    }
  }
  post {
    always {
      deleteDir()
      sh "echo 'fase always'"
    }
    success {
      sh "echo 'fase success'"
    }
    failure {
      sh "echo 'fase failure'"
    }
  }
}