pipeline {
    agent any
    
    options {
      timeout(time: 1, unit: 'HOURS') 
      buildDiscarder(logRotator(numToKeepStr: '20'))
      disableConcurrentBuilds()
      timeout (time: 60, unit: 'MINUTES')
      timestamps()
  }  

    stages {
        stage('Hello') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }
     stage('clone') {
            steps {
                sh '''
                ls 
                pwd
                uname -r
                hostname -I
                '''
            }
        }
    }
}
