pipeline{
  agent any
   stages{
     stage('codeCommit'){
       steps{
         git credentialsId: 'Github_account_3rdServer', branch: 'master', url: 'https://github.com/maheshgowdan-hub/Amazon.git'
       }
     }
     stage('buildAmazon'){
       steps{
         dir('Amazon'){
         sh 'mvn clean install'
         }
       }
     }
     stage('buildSKY'){
       steps{
         dir('SKY'){
         sh 'mvn clean install'
         }
       }
     }
     stage('buildSpringCore'){
       steps{
         dir('SpringCore'){
           sh 'mvn clean install'
         }
       }
     }
     stage('buildSpringDemo'){
       steps{
         dir('SpringDemo'){
         sh 'mvn clean install'
         }
       }
     }
     stage('buildSpringNew'){
       steps{
         dir('SpringNew'){
         sh 'mvn clean install'
         }
       }
     }
     stage('buildTest'){
       steps{
         dir('Test'){
           sh 'mvn clean install'
         }
       }
     }
   }
    /* stage('buildtest'){
       steps{
         dir('test'){
           sh 'mvn clean install'
         }
         }
       }
     }
   } */
  post{
    success{
      echo "all builds over"
    }
    failure{
      echo "build Failed"
    }
  }
}
 
