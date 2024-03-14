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
                bat 'powershell.exe -Command "az storage file upload --account-name "ssissg" --account-key "" --share-name "ssisfs" --source "C:/Users/admin123/IntegrationServicesProject2.ispac" --path "ssisdir"'       
            }      
        }  
    }  
}  
