pipeline { 
  agent any

tools{
	nodejs 'nodes_18'
  }
  
  stages { 
    stage('clone repository') {
      steps { 
        git 'https://github.com/hanjarim/gallery.git'
      }
    }
     stage('Build the project') {
      steps { 
        sh 'echo "here we will Build"'
      }
      
    }
    stage('Install Dependencies') {
      steps { 
        sh 'echo "npm install''
      }
    }
    stage('Tests') {
      steps { 
        sh 'echo "npm test"'
      }
    }
	stage('Deploy Application') {
      steps {
              sh 'echo "deploy an APP"'
              }
    }
  }
}