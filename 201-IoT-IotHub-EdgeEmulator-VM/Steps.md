need to run the following cmd before running arm template: (need to confirm the Powershell equivalent)
to find the urn do this:

az vm image list --all --publisher "microsoft_iot_edge"

to accept the terms do this:
az vm image accept-terms --urn "microsoft_iot_edge:iot_edge_vm_ubuntu:ubuntu_1604_edgeruntimeonly:1.0.1"

az vm image accept-terms --urn microsoft_iot_edge:iot_edge_vm_ubuntu:ubuntu_1604_edgeruntimeonly:latest


need to create a device identity onthe hub for the device. If you has never created one before, visit the [doc](https://docs.microsoft.com/en-us/azure/iot-edge/how-to-register-device) to look for some prerequisites.
az iot hub device-identity create --hub-name {hub_name} --device-id myEdgeDevice --edge-enabled
az iot hub device-identity create --hub-name IoThubIoTEdgeResources --device-id myEdgeDevice --edge-enabled

need to run the following command after to register the iot device:


/etc/iotedge/configedge.sh “{device_connection_string}”

to get connection string run:

az iot hub device-identity show-connection-string --device-id myEdgeDevice --hub-name {hub_name}
az iot hub device-identity show-connection-string --device-id myEdgeDevice --hub-name IoThubIoTEdgeResources

az vm run-command invoke -g IoTEdgeResources -n EdgeVM --command-id RunShellScript --script "/etc/iotedge/configedge.sh '{device_connection_string}'"

az vm run-command invoke -g education -n IoT-Edge --command-id RunShellScript --scripts "/etc/iotedge/configedge.sh "{hub_connection_string}"

az vm run-command invoke -g IoTEdgeResources -n EdgeVM --command-id RunShellScript --script "/etc/iotedge/configedge.sh 'HostName=IoThubIoTEdgeResources.azure-devices.net;DeviceId=myEdgeDevice;SharedAccessKey=hNyoOryFsmUiCL+G8i42Z7iT69aZa7ohfhWY4BUbNlg='"

az vm run-command invoke -g IoTEdgeResources -n EdgeVM --command-id RunShellScript --script "/etc/iotedge/configedge.sh '{device_connection_string}'"