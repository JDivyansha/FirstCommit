pipeline:  
  agent:  
    any  
  
  stages:  
    - stage: Checkout  
      steps:  
        - checkout: git  
  
    - stage: Upload  
      steps:  
        - script:  
            name: Upload File to Azure File Share  
            code: |  
              # Install Azure CLI  
              curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash  
  
              # Set the storage account and file share details  
              storageAccountName="ssissg"  
              storageAccountKey="+ZhT4GQg3hEKI8J3RxVb4tAHKfv0zqpvNGPCevB6UUnmwT6/HAd5U72dnWxWxYMoD52dCj3n/V8S+ASt6QWtCw=="  
              fileShareName="ssisfs"  
              localFilePath="Package.dtsx"  
              remoteFilePath="https://ssissg.file.core.windows.net/ssisfs"  
  
              # Mount the Azure File Share  
              sudo mkdir /mnt/azure  
              sudo mount -t cifs //$storageAccountName.file.core.windows.net/$fileShareName /mnt/azure -o vers=3.0,username=$storageAccountName,password=$storageAccountKey,dir_mode=0777,file_mode=0777,serverino  
  
              # Copy the file to Azure File Share  
              sudo cp $localFilePath /mnt/azure/$remoteFilePath  
  
              # Unmount the Azure File Share  
              sudo umount /mnt/azure  
  
    - stage: Cleanup  
      steps:  
        - script:  
            name: Clean Up  
            code: |  
              # Add any cleanup commands here  