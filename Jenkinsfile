pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        echo 'sending helloWorld'
        publishEvent simpleEvent('helloWorld')
      }
    }
  }
}