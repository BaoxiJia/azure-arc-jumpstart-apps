
To install VoE with Helm Chart, please refer to the document https://github.com/Azure-Samples/azure-intelligent-edge-patterns/blob/master/factory-ai-vision/Tutorial/K8s_helm_deploy.md. I usually use the following command - 

```
Helm install voe-k8s https://aka.ms/VoEHelm --set "azureIoT.hubConnectionString=<your IoTHub connection string>" --set "azureIoT.edgeConnectionString=<your IoT Edge device connection string>" --set "customVision.endPoint=<your custom vision service endpoint string>" --set "customVision.key=<your custom vision service key"
```

To Install VoE with a deployment yaml, you can refer to the sample file - voe.yaml, which contains my test parameters (IoT Hub, IoT edge device, etc.). To use your own IoT Hub/Edge device, you need to generate the base64 format of your connection strings with the following command in WSL/linux and replace the existing ones in voe.yaml.

```
echo -n '<your IoT Hub/Edge connection string>' | base64
```