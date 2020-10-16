pipeline {
  agent any
  stages {
    stage('Example') {
      steps {
        echo 'sending helloWorld'
        //publishEvent simpleEvent('helloWorld')
      }
    }
    stage('OWASP Dependency Track') {
      steps {
        dependencyTrackPublisher artifact: 'target/bom.xml', projectName: "${env.JOB_NAME}", synchronous: true, projectVersion: "${env.BRANCH_NAME}"
      }
    }
  }
}
