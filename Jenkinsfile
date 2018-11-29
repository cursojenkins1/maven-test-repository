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
  stage('Compile') {
    echo 'Comienza la compilación'
    compile
  }
  stage('Test') {
    echo 'Comienzan las pruebas' 
  }
  stage('Package') {
    echo 'Comienza el empaquetado' 
  }
}
