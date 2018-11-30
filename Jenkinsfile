/*
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

node {
    try {
        stage('Test') {
            sh 'echo "Fallo!"; exit 0'
        }
        echo 'Se ejecuta si exito'
    } catch (e) {
        echo 'Se ejecuta si fallo'
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'FAILURE'
        if (currentResult == 'FAILURE') {
            echo 'Se ejecuta si unstable'
        }

        def previousResult = currentBuild.previousBuild?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'Se ejecuta si hay cambio de estado'
        }

        echo 'Se ejecuta siempre'
    }
}
