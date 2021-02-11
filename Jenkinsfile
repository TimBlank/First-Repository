pipeline{
  agent any  
  stages {   
    stage("build"){
        steps{
          echo 'building the application...'
        }
     }
    stage("test"){
      when{
        expression{
          BRANCH_NAME == 'Dev' || BRANCH_NAME =='master'
        }
      }
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
      echo 'I´m done Master'
      //
    }
    success{
      echo 'Team success!'
      //send message to Team every Magaer build
    }
    failure{
      echo CHANGE_AUTHOR
      //send masage to CHANGE_AUTHOR withe fail satus 
    }
  
  }
  
}
