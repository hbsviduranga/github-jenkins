pipeline {
  agent any
  environment {
    NEW_VERSION = '1.2.5'
  }
  tools {
    maven 'Maven'
  }
  stages {
    stage("checkout") {
      steps {
        echo "Checkout source from the SCM"
        echo "Current version is ${NEW_VERSION}"
        sh "mvn clean install"
      }
    }
    
    stage("build") {
      steps {
        echo "Build the artifact"
      }
    }
    
    stage("test") {
      when {
        expression { 
          env.BRANCH_NAME == 'main'
        }
      }
      steps {
        echo "Testing...."
      }
    }
    
    stage("deploy") {
      steps {
        echo "Deploying..."
      }
    }
  }
}
