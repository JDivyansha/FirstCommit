pipeline {  
    agent any  
    stages {  
        stage('Clone Git Repository') {  
            steps {  
                git branch: 'master', url: 'https://github.com/JDivyansha/FirstCommit.git'
  
            }  
        }  
        stage('Upload to Azure File Share') {  
            steps {  
                withCredentials([string(credentialsId: '0d8e2e24-bc95-45c8-9cf3-92765b4120d0', variable: 'ACCOUNT_KEY')]) {  
                    script {  
                        sh '''  
                            ls
                            az storage file upload-batch --destination-path https://ssissg.file.core.windows.net/ssisfs --destination-share ssisfs --source . --account-name ssissg --account-key $ACCOUNT_KEY  
                        '''  
                    }  

            }  
        }  
    }  
}  
}
