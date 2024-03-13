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
                withCredentials([string(credentialsId: 'f265adde-ee4f-4a59-922d-cce6f708202d0', variable: 'ACCOUNT_KEY')]) {  
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
