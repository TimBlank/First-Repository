pipeline{

  agent any
  
  stages {
    
    stage("build"){
        
        steps{
          echo 'building the application...'
        }
     }
    stage("test"){
        
        steps{
          echo 'testining the application...'
        }
     }
    stage("deploy"){
        
        steps{
          echo 'deploying the application...'
        }
     }
   }
  post{
    always{
      //
    }
    success{
      //send message to Team every Magaer build
    }
    failure{
      //send masage to admin withe fail satus 
    }
  
  }
  
}
