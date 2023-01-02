pipeline {
   agent {
     label ("node1 || node2 || node3 || node4 || node5 || branch || main || jenkins-node || docker-agent || jenkins-docker2 || preproduction || production")
            }
    triggers {
        cron('* * * * *')
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
	    
        stage('permission') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('cleaning') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('sonarqube') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('build-dev') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('build-sanbox') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('build-pro') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('login') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('push-to-dockerhub-dev') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('push-to-dockerhub-sanbox') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('push-to-dockerhub-pro') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('update-helm-charts-dev') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('update-helm-charts-sanbox') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }

        stage('push-to-dockerhub-pro1') {
            steps {
                sh '''
                ls 
                pwd
                '''
            }
        }
	    
        stage('Hello2') {

       
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
		hostname
                '''
            }
        }
    }
       post {
   
   success {
      slackSend (channel: '#development-alerts', color: 'good', message: "SUCCESSFUL: Application S4-EKTSS  Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
    }

 
    unstable {
      slackSend (channel: '#development-alerts', color: 'warning', message: "UNSTABLE: Application S4-EKTSS  Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
    }

    failure {
      slackSend (channel: '#development-alerts', color: '#FF0000', message: "FAILURE: Application S4-EKTSS Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
    }
   
    cleanup {
      deleteDir()
    }
}
}
