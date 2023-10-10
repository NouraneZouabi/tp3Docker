pipeline {
  agent any 
  tools {
    maven 'Maven'
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
        dir("tp3Docker") {
          sh "mvn clean install"
          sh "sudo docker build -t backend ."
        }
    }
    }
    stage ("Run docker compose"){
      steps {
        dir ("tp3Docker"){
          sh "docker compose up -d "
        }
      }
    }
  }
}
