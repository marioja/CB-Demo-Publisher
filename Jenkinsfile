pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        echo 'sending helloWorld'
        publishEvent jsonEvent('{"eventName":"helloWorld"}')
      }
    }
  }
}