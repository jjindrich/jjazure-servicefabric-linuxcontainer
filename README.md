# jjazure-servicefabric-linuxcontainer

## Install ServiceFabric CLI
```powershell
pip3 install --user sfctl 
```
Connect to cluster
```powershell
sfctl cluster select --endpoint http://jjcluster.westeurope.cloudapp.azure.com:19080
```

## Aplication
You can create application manifest manually or use this <a href="https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-tutorial-package-containers">steps</a>.

## Deploy application
```powershell
sfctl application upload --path jjweb --show-progress
sfctl application provision --application-type-build-path jjweb
```

Then you can create new application instance in Service Fabric Explorer
or with this script
```
sfctl application create --app-name fabric:/jjweb --app-type jjwebType --app-version 1.0.0
```
