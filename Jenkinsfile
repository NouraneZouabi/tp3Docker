pipeline {
  agent any 
  tools {
    maven 'maven 3.9.4'
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
          sh "mavn clean install"
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
