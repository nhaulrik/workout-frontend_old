pipeline {

  agent any

  stages {
    stage('INSTALL PACKAGES') {
      steps {
        sh "npm install"
      }
    }
    stage('BUILD APP') {
      steps {
        sh "node_modules/.bin/ng build --aot=false"
      }
    }
    stage("BUILD DOCKER") {
      steps {
        script {
          dockerImageBuild = docker.build "angularapp" + ":latest"
        }
      }
    }
  }
}
