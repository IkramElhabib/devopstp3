pipeline {
  agent any
  tools {
    maven 'maven'
  }
  stages {
    stage ("Clean up"){
      steps {
        deleteDir()
      }
    }
    stage ("Clone repo"){
      steps {
        sh "git clone https://github.com/IkramElhabib/devopstp3.git"
      }
    }
    stage("Generate backend image") {
    steps {
        dir("devopstp3") {
            sh "mvn clean install"
            sh "docker build -t backend ."
        }
    }
}
stage("Run docker compose") {
    steps {
        dir("devopstp3") {
            sh "docker-compose up -d"
        }
    }
}
}
}
