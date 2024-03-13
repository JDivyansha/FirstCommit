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
                withCredentials([string(credentialsId: '8ad80f86-7c4c-4a1d-a921-a8d9e5a87919', variable: 'ACCOUNT_KEY')]) {  
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
