pipeline {
  agent any
  environment {
    NEW_VERSION = '1.2.5'
  }
  tools {
    maven 'Maven'
  }
  parameters {
    string(name: 'VERSION', defaultValue: '', description: 'version to deploy on prod')
    choice(name: 'PRODUCT_TYPE', choices: ['All', 'Product-1', 'Product-2'], description: 'Select required product type to be built')
    booleanParam(name: 'SERVER_ONLY', defaultValue: false, description: 'Select "True", if you only need to build server component')
  }
  stages {
    stage("checkout") {
      steps {
        echo "Checkout source from the SCM"
        echo "Current version is ${NEW_VERSION}"
        echo "Product type is ${PRODUCT_TYPE} and entered version is ${VERSION}"
        bat "mvn clean install"
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
          env.BRANCH_NAME == 'main' && params.SERVER_ONLY
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
