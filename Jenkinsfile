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
                withAzureFileCopy(credentialsId: '8ad80f86-7c4c-4a1d-a921-a8d9e5a87919', storageAccountName: 'ssissg', sourceFiles: '**/*.ispac', targetPath: 'https://ssissg.file.core.windows.net/ssisfs') {  
                    // Add any additional steps you need after the files are uploaded  
                }  
            }  
        }  
    }  
}  
	
            
