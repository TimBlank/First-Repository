pipeline{
  agent any  
  environment{
    NEW_VERSION = '1.3.0'
    SERVER_CREDENTIALS = credentials('global')
    CHANGE_AUTHOR = "TIM B."
    CHANGE_AUTHOR_EMAIL = "Test@Test.de"
  }
  tools {
    maven 'Maven'
  }
  parameter{
    string(name: 'VERSION_NAME', defaltValue: '', descriptio: 'Version to deploy on prod')
    choice(name: 'VERSION', choices: ['1.0.0', '0.14.1', '2.1.1'], desceiption:'')
    booleanParam(name: 'executeTest', defaultValue: true, description: 'execute the Testingphase')
    
  }
  stages {   
    stage("build"){
      when{
        expression{
          BRANCH_NAME == 'Dev' || BRANCH_NAME =='master'
        }
      }
        steps{
          echo 'building the application...'
          echo "building Version: ${NEW_VERSION}"
        }
     }
    stage("test"){
      
      when{
        expression{
          params.executeTests
        }
      }
      steps{
          echo 'testining the application...'
          //script
      }
     }
    stage("deploy"){
        
        steps{
          echo "deploying the application ${params.VERSION}"
          //echo "deploy with ${SERVER_CREDENTIALS}"
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
      echo "${CHANGE_AUTHOR}"
      echo "sending Failure to: ${CHANGE_AUTHOR_EMAIL}" 
      //send masage to CHANGE_AUTHOR_EMAIL withe fail satus 
    }
  }
}
