pipeline {  
    agent any  
    
    stages {  
        stage('Clone Git Repository') {  
            steps {  
                git branch: 'master', url: 'https://github.com/JDivyansha/FirstCommit.git'
  
            }  
        }  
        stage('Upload to Azure File Share') {  
            environment {  
                AZURE_STORAGE_ACCOUNT = 'ssissg'  
                AZURE_STORAGE_KEY = credentials('ssisaccesskeys')  
                AZURE_FILE_SHARE = 'ssisfs'  
                AZURE_FILE_DIRECTORY = 'ssisdir'  
         }  
            
            steps {  
                        script { 
                            sh 'curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash'  
                            sh 'az storage file upload-batch --account-name $AZURE_STORAGE_ACCOUNT --account-key $AZURE_STORAGE_KEY --destination $AZURE_FILE_SHARE --destination-path $AZURE_FILE_DIRECTORY --source .'  
                        }  
            }
            
        }  
    }  
}  

