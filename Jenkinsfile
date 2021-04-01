pipeline {
    agent {
        node {
            label "master"
        }
    }
    
    parameters {
        string defaultValue: '1719-IR4B', description: '5094-IA16', name: 'Modules', trim: true
        string defaultValue: 'V144', description: 'V142', name: 'Build_Version', trim: true
        choice choices: ['Offline', 'Online'], name: 'OnOffline'
        choice choices: ['no', 'yes'], name: 'Use_Exist_Image'
        choice choices: ['5', '10', '15', '20'], name: 'Max_Instance_Number'
    }
    
    stages {
		stage('Get case files') {
			steps {
				echo "Get case files"
			}    
		}
	
		stage('Get exe files') {
			steps {
				echo "Get exe files"
			}	
		}
		
		stage('STEX precondition'){
			failFast true
			parallel{
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
				echo "Testing"
			}          
		}
		
		stage('Report') {
			steps {
				echo "Report"
			}          
		}
	}    
}

