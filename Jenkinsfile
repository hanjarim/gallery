pipeline { 
  agent any

tools{
	nodejs 'nodejs_18'
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
        sh 'npm install'
      }
    }
    stage('Tests') {
      steps { 
        sh 'npm test'
      }
    }
	stage('Deploy Application') {
      steps {
            withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS' )]){
                    sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/powerful-springs-62769.git master'
              }
    }
  }
}
post {
  success {
    slacksend colors: "good", message:"Build ${env.BUILD_NUMBER} of ${env.JOB_NAME} Succeeded.Deployed at ${LIVE_SITE}"
  }
  failure {
    slacksend color "danger", message:"Build ${env.BUILD_NUMBER} of ${env.JOB_NAME} failed.See ${env.BUILD_URL} for details." 
  }
}
}