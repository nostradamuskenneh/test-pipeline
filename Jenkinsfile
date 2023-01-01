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
                stage('Setup parameters') {
            steps {
                script {
                    properties([
                        parameters([ 
                        
                        choice(
                            choices: ['Dev', 'Sanbox', 'Prod'], 
                            name: 'Environment'
                                ),

                          string(
                            defaultValue: 's4oumar',
                            name: 'User',
			                description: 'Enter the image Tag to deploy',
                            trim: true
                            ),

                          string(
                            defaultValue: 's4oumar',
                            name: 'DB-Tag',
			                description: 'Enter the image Tag to deploy',
                            trim: true
                            ),

                          string(
                            defaultValue: 's4oumar',
                            name: 'UI-tag',
			                description: 'Enter the image Tag to deploy',
                            trim: true
                            ),
                
                          string(
                            defaultValue: 's4oumar',
                            name: 'WEATHER-Tag',
			                description: 'Enter the image Tag to deploy',
                            trim: true
                            ),

                          string(
                            defaultValue: 's4oumar',
                            name: 'AUTH-tag',
			                description: 'Enter the image Tag to deploy',
                            trim: true
                            ),
                
                        ])
                    ])
                }
            }
        }
        stage('Hello') {

       
            steps {
                sh '''
               
                ls 
		uname -a
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
