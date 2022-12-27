pipeline {
  agent any
  stages {
    stage("checkout") {
      steps {
        echo "Checkout source from the SCM"
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
