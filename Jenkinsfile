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
        withMaven() {
          bat "mvn org.cyclonedx:cyclonedx-maven-plugin:1.6.4:makeAggregateBom"
        }
        dependencyTrackPublisher artifact: 'target/bom.xml', projectName: "${env.JOB_NAME}", synchronous: true, projectVersion: "${env.BRANCH_NAME}"
      }
    }
    stage('Last') {
      steps {
        echo 'Done'
        //publishEvent simpleEvent('helloWorld')
      }
    }
  }
}
