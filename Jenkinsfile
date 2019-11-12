pipeline {
   agent{
       docker { 
           image 'maven:3-alpine'
           args '-v /root/.m2:/root/.m2'
       }
   }

   stages {
      stage('build') {
         steps {
            sh 'mvn -B -DskipTests clean package'
         }
      }
      stage('test'){
          steps{
              echo 'Test'
          }
      }
      stage('deploy'){
          steps{
              echo 'deploy success'
          }
      }
   }
   post{
          always{
              echo 'always success or failed'
          }
          success{
              echo 'success'
          }
          failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
      }
}
