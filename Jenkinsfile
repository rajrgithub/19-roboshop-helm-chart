pipeline {

  agent any

  options {
    ansiColor('xterm')
  }
  parameters {
    string(name: 'COMPONENT', defaultValue: '', description: 'Component')
    string(name: 'APP_VERSION', defaultValue: '', description: 'App Version')
  }

  stages {

    stage('Get Values file') {
      steps {
        dir('APP') {
          git branch: 'main', url: 'https://github.com/rajrgithub/${COMPONENT}.git'
        }
      }
    }

    stage('Helm Deploy') {
      steps {
        sh 'find .'
        //sh 'helm upgrade -i ${COMPONENT} ./HELM -f APP/values.yaml --set-string image.tag="${APP_VERSION},ENV=prod,COMPONENT=${COMPONENT}"'
      }

    }


  }

 // post {
  //  always {
      //cleanWs()
   // }
 // }



}