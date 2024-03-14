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
                bat 'powershell.exe -Command "az"'       
            }      
        }  
    }  
}  
