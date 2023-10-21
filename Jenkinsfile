pipeline{
agent { label 'workstation' }
 stages{
 stage(Compile code) {
 steps{
   sh 'npm install'
   }
  }
  stage(Unit test code) {
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
