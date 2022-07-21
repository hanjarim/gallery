pipeline { 
  agent any

  
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
        sh 'echo "Here we Install"'
      }
    }
    stage('Tests') {
      steps { 
        sh 'echo "here we run tests"'
      }
    }
	stage('Deploy Application') {
      steps {
              sh 'echo "deploy an APP"'
              }
    }
  }
}