pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        echo 'Comienza la compilación'
        withMaven(
          maven:'Maven por defecto (3.6.0)'  
        ) {
          sh 'mvn compile' 
        }
      }
    }
    stage('Test') {
      steps{
        echo 'Comienzan las pruebas'
        withMaven(
          maven:'Maven por defecto (3.6.0)'  
        ) {
          sh 'mvn test'
        }
      }
    }
    stage('Package') {
      steps {
        echo 'Comienza el empaquetado'
          withMaven(
            maven:'Maven por defecto (3.6.0)'  
          ) {
            sh 'mvn package'
          }
      }
    }
  }
  post {
    always {
      deleteDir() 
    }
    failure {
      echo 'Error'
    }
    success {
      echo 'Éxito'
    }
    changed {
      echo 'Cambio'
    }
  }
}

/*
node {
  checkout scm
  stage('Compile') {
    echo 'Comienza la compilación'
    //withMaven(
      //maven:'Maven por defecto (3.6.0)'  
    //) {
      sh 'mvn compile' 
    //}
  }
  stage('Test') {
    echo 'Comienzan las pruebas'
    //withMaven(
      //maven:'Maven por defecto (3.6.0)'  
    //) {
      sh 'mvn test'
    //}
  }
  stage('Package') {
    echo 'Comienza el empaquetado'
    //withMaven(
      //maven:'Maven por defecto (3.6.0)'  
    //) {
      sh 'mvn package'
    //}
  }
}
*/
