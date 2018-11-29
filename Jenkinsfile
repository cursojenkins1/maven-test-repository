/*
pipeline {
  agent any
  stages {
    stage('Etapa 1') {
      steps {
        echo 'Hello World'
      }
    }
  }
}
*/

node {
  checkout scm
  stage('Compile') {
    echo 'Comienza la compilación'
    mvn compile
  }
  stage('Test') {
    echo 'Comienzan las pruebas' 
  }
  stage('Package') {
    echo 'Comienza el empaquetado' 
  }
}
