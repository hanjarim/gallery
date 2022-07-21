pipeline {
    agent any
stages {
    stage ('Compile Stage') {

        steps {
        with Maven(maven :'moses_3.8.6'){
            sh 'mvn clean compile'
        }
        }
    }
}

stage ('Testing Stage') {

        steps {
        with Maven(maven :'moses_3.8.6'){
            sh 'mvn test'
        }
    }
 }

stage ('Deployment Stage') {

        steps {
        with Maven(maven :'moses_3.8.6'){
            sh 'mvn deploy'
        }
    }
 }
}