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
                azureUpload fileShareName: 'ssisfs', filesPath: '*.dtproj', storageCredentialId: '58e146ce-9120-4687-b4f0-241f6ffe0cd8', storageType: 'filestorage'       
            }      
        }  
    }  
}  
