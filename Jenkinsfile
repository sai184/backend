pipeline{
agent { label 'workstation' }
 stages{
 stage(download dependencies) {
 steps{
   sh 'npm install'
   }
  }
  stage(code quality) {
   steps{
     sh 'sonar-scanner -Dsonar.host.url=http://172.31.39.191:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=backend -Dsonar.qualitygate.wait=true'
     echo 'ok'
     }
    }
    stage(unit testing) {
        steps{
          echo 'CI'
          }
         }

   stage(deploy to production) {
    steps{
      echo 'CI'
      }
     }
 }
}
