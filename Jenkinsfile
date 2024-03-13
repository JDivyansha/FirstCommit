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
                script {  
                    sh '''  
                          az storage file upload-batch --destination-path https://ssissg.file.core.windows.net/ssisfs --destination-share ssisfs --source . --account-name ssissg --account-key +ZhT4GQg3hEKI8J3RxVb4tAHKfv0zqpvNGPCevB6UUnmwT6/HAd5U72dnWxWxYMoD52dCj3n/V8S+ASt6QWtCw= 
                    '''  
                }  
            }  
        }  
    }  
}  
