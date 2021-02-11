pipeline{
  agent any  
  environment{
    NEW_VERSION = '1.3.0'
    SERVER_CREDENTIALS = credentials('global')
  }
  stages {   
    stage("build"){
        steps{
          echo 'building the application...'
          echo "building Version: ${NEW_VERSION}"
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
          //script
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
      echo "sending Failure to: ${CHANGE_AUTHOR_EMAIL}" 
      //send masage to CHANGE_AUTHOR_EMAIL withe fail satus 
    }
  
  }
  
}
