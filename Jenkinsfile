pipeline {  
    agent any  
    
    stages {  
        stage('Clone Git Repository') {  
            steps {  
                git branch: 'master', url: 'https://github.com/JDivyansha/FirstCommit.git'
            }  
        }  
        stage('DEV: Upload to Azure File Share') {  
            environment {  
                AZURE_STORAGE_ACCOUNT = 'ssissg'  
                AZURE_STORAGE_KEY = credentials('ssisaccesskeys')  
                AZURE_FILE_SHARE = 'ssisfs'  
                AZURE_FILE_DIRECTORY = 'ssisdir' 
                SOURCE_PATH = 'C:/Users/admin123/IntegrationServicesProject2.ispac'
             }    
            steps {
                withCredentials([usernamePassword(credentialsId: 'ssisaccesskeys', usernameVariable: 'AZURE_STORAGE_KEY_USERNAME', passwordVariable: 'AZURE_STORAGE_KEY_PASSWORD')]) {
                bat 'powershell.exe -Command "az storage file upload --account-name %AZURE_STORAGE_ACCOUNT% --account-key %AZURE_STORAGE_KEY_PASSWORD% --share-name %AZURE_FILE_SHARE% --source %SOURCE_PATH% --path %AZURE_FILE_DIRECTORY%'       
            }  
        }
        }
        stage('Non-Prod - Upload to Azure File Share') {  
            steps {  
                bat 'powershell.exe -Command write-host "Non-Prod Upload packege to Azure File Share"'
            }  
        }
    }  
}  
