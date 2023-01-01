pipeline {
   agent {
     label ("node1 || node2 || node3 || node4")
            }
    
    options {
      timeout(time: 1, unit: 'HOURS') 
     
      //buildDiscarder(logRotator(numToKeepStr: '20'))
      //disableConcurrentBuilds()
      //timeout (time: 60, unit: 'MINUTES')
      //timestamps()
  }
    stages {
        stage('Hello') {
            steps {
                sh '''
                ls 
                pwd
                echo get_current_time_date
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
