// This adds install and test stages before static code analysis
pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/d-wheatley/lbg-vat-calculator.git'
        }
    }
    stage('Install') {
        steps {
            // Install the ReactJS dependencies
            sh "npm install"
        }
    }
    stage('Test') {
        steps {
          // Run the ReactJS tests
          sh "npm test"
        }
    }
//    stage('SonarQube Analysis') {
//      environment {
//        scannerHome = tool 'sonarqube'
//        }
//        steps {
//            withSonarQubeEnv('sonar-qube-7') {        
//              sh "${scannerHome}/bin/sonar-scanner"
//        }
//      
//      //May need to comment this out 
//        timeout(time: 1, unit: 'MINUTES'){
//          waitForQualityGate abortPipeline: true
//         }
//        }
//    }
  }
}
