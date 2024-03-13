pipeline {  
    agent any  
  
    stages {  
        stage('Clone Git Repository') {  
            steps {  
                git branch: 'master', url: 'https://github.com/JDivyansha/FirstCommit.git'  
            }  
        }  
  
        stage('Upload SSIS Packages') {  
            steps {  
                script {  
                    def packagesDir = "."  
                    def fileShareUrl = "https://ssissg.file.core.windows.net/ssisfs"  
                    def storageAccountKey = credentials('8ad80f86-7c4c-4a1d-a921-a8d9e5a87919').password  
  
                    sh '''  
                        az storage file upload-batch --destination-path ''' + fileShareUrl + ''' --source ''' + packagesDir + ''' --account-name ssissg --account-key ''' + storageAccountKey  
                    '''  
                }  
            }  
        }  
    }  
}  
