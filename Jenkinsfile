pipeline {
  agent any
  environment {
    NEW_VERSION = '1.2.5'
  }
  stages {
    stage("checkout") {
      steps {
        echo "Checkout source from the SCM"
        echo "Current version is ${NEW_VERSION}"
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
