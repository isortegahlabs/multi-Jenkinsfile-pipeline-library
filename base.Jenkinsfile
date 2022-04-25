@Library('sharedLibraryMultiJenkinsfile')_

pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh "pwd"
            }
        }
        stage('Test') { 
            steps {
                sh "pwd"
            }
        }
        stage('Deploy') { 
            steps {
                script {
                    sh "pwd"
                    log.info("Hola")
                }
            }
        }
        stage('SampleTryCatch') { 
            steps {
                script {
                    try {
                        sh "exit 0"
                    }catch (Exception e) {
                        
                        echo 'Exception occurred: ' + e.toString()  
                        currentBuild.result = 'ABORTED'
                        error('Quitting')
                    }
                }
            }
        }
    }

    post {
    always {
      echo 'always runs regardless of the completion status of the Pipeline run'
    }
    success {
      echo 'step will run only if the build is successful'
    }
    failure {
      echo 'only when the Pipeline is currently in a "failed" state run, usually expressed in the Web UI with the red indicator.'
    }
    unstable {
      echo 'current Pipeline has "unstable" state, usually by a failed test, code violations and other causes, in order to run. Usually represented in a web UI with a yellow indication.'
    }
    changed {
      echo 'can only be run if the current Pipeline is running at a different state than the previously completed Pipeline'
    }
  }
}
