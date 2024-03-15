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
                bat 'powershell.exe -Command "az storage file upload --account-name %AZURE_STORAGE_ACCOUNT% --account-key %AZURE_STORAGE_KEY% --share-name %AZURE_FILE_SHARE% --source "C:/Users/admin123/IntegrationServicesProject2.ispac" --path %AZURE_FILE_DIRECTORY%'       
            }      
        }  
    }  
}  
