pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Get testing data') {
      parallel {
        stage('Get modules') {
          steps {
            echo 'Get modules'
          }
        }

        stage('Get automation data') {
          steps {
            echo 'Get automation data'
          }
        }

      }
    }

    stage('Get exe files') {
      parallel {
        stage('Get trigger STEX tool') {
          steps {
            bat 'echo "Get trigger STEX tool"'
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
      parallel {
        stage('API test') {
          steps {
            echo 'API test'
          }
        }

        stage('Smoke test') {
          steps {
            echo 'Smoke test'
          }
        }

        stage('Intergration test') {
          steps {
            echo 'Intergration test'
          }
        }

        stage('End to End test') {
          steps {
            echo 'End to End test'
          }
        }

        stage('System test') {
          steps {
            echo 'System test'
          }
        }

      }
    }

    stage('Report') {
      parallel {
        stage('Web report') {
          steps {
            echo 'Web report'
          }
        }

        stage('Xlsx report') {
          steps {
            echo 'Xlsx report'
          }
        }

      }
    }

    stage('CM release build trigger') {
      steps {
        echo 'CM release build trigger'
      }
    }

    stage('TBD') {
      steps {
        echo 'TBD'
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