pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Get case files') {
      steps {
        echo 'Get case files'
      }
    }

    stage('Get exe files') {
      parallel {
        stage('Get trigger STEX tools') {
          steps {
            bat 'echo "Get trigger STEX tools"'
          }
        }

        stage('Get rerun tool') {
          steps {
            bat 'echo "Get rerun tool"'
          }
        }

        stage('Get report tool') {
          steps {
            bat 'echo "Get report tool"'
          }
        }

        stage('Get module tools') {
          steps {
            bat 'echo "Get module tools"'
          }
        }

      }
    }

    stage('STEX precondition') {
      failFast true
      parallel {
        stage('Is AutoScript Modules exist') {
          steps {
            echo Modules
          }
        }

        stage('Is AutoScript Data exist') {
          steps {
            echo Modules
          }
        }

        stage('Is Engineer build exist') {
          steps {
            echo Modules
          }
        }

      }
    }

    stage('Testing') {
      steps {
        echo 'Testing'
      }
    }

    stage('Report') {
      steps {
        echo 'Report'
      }
    }

  }
  parameters {
    string(defaultValue: '1719-IR4B', description: '5094-IA16', name: 'Modules', trim: true)
    string(defaultValue: 'V144', description: 'V142', name: 'Build_Version', trim: true)
    choice(choices: ['Offline', 'Online'], name: 'OnOffline')
    choice(choices: ['no', 'yes'], name: 'Use_Exist_Image')
    choice(choices: ['5', '10', '15', '20'], name: 'Max_Instance_Number')
  }
}