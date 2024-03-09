pipeline {
  agent any
    tools {nodejs "node"}
    stages {
      stage('Build') {
         steps {
		    git 'https://github.com/Hari20042002/simple-node-js-react-npm-app.git'
            sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
