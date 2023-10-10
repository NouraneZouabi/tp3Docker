pipeline {
  agent any 
  tools {
    Maven 'Maven'
  }
  stages {
    stage ("clean up"){
      steps {
        deleteDir()
      }
    }
    stage ("clone repo"){
      steps {
        sh " git clone https://github.com/NouraneZouabi/tp3Docker"
          }
    }
    stage ("Generate backend image"){
      steps {
        dir("backend") {
          sh "mvn clean install"
          sh "docker build -t backend ."
        }
    }
    }
    stage ("Run docker compose"){
      steps {
        dir ("backend"){
          sh "docker compose up -d "
        }
      }
    }
  }
}
