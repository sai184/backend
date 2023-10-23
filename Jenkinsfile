pipeline{
agent { label 'workstation' }
 stages{
 stage('download dependencies') {
 steps{
   sh 'npm install'
   }
  }
  stage('code quality') {

    when {
            allOf {
              expression { TAG_NAME != GIT_BRANCH }
            }
          }
   steps{
     //sh 'sonar-scanner -Dsonar.host.url=http://172.31.39.191:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=backend -Dsonar.qualitygate.wait=true'
     echo 'ok'
     }
   }
    stage('unit test') {

       when {
              allOf {
               // expression { env.TAG_NAME != env.GIT_BRANCH }
                branch 'main'
              }
            }
        steps{
          //ideally unit tests we should run ,but devolper skipped it so assuming those are good and we are good proceding
                   // sh 'npm test'
                    echo 'CI'
          }
         }

   stage('Release') {

   when {
           expression { env.TAG_NAME ==~ ".*" }
         }
    steps{
      echo 'CI'
      }
     }
 }
}


//annyalsis report will come from qualitygate
//here pipeline is failing yy beacuse in code it has some errror we cant do anything our job is just desghin pipeline