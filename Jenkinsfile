pipeline {
   agent {
     label ("node1 || node2 || node3 || node4 || node5 || branch || main || jenkins-node || docker-agent || jenkins-docker2 || preproduction || production")
            }
    
    options {
      //timeout(time: 1, unit: 'HOURS') 
     
      buildDiscarder(logRotator(numToKeepStr: '2'))
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
