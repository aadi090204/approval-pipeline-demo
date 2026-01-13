pipeline{
  agent any

  stages{
    stage('Checkout'){
      steps{
        echo 'puling code from github'
        checkout scm
      }
    }
    stage('Build'){
      steps{
          echo 'Building projectis going on'
          bat 'echo Build completed successfully!'
      }
    }
    stage('Validation'){
      steps{
        echo 'validating project readiness'
        bat '''
        findstr READ=true check.txt >nul
        if errorlevel 1 (
            echo validation failed
            exit 1
            ) else (
                    echo validation passed
            )
            '''
        
                    
                    
            
      }
    }
    stage('Manager approval') {
      steps{
        input message: 'Approve Deployement?',ok: 'Approve'
      }
    }
    stage('Ready for Deployement'){
      steps{
        echo 'Deployement approved and ready'
      }
    }
    
  }
}
