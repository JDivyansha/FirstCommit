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
                azureUpload fileShareName: 'ssisfs', filesPath: '*.dtproj', storageCredentialId: 'ssisaccesskeys', storageType: 'filestorage'       
            }      
        }  
    }  
}  
