# Dependent service URL configuration

While OpenMAVN project is not ready to fully and easily run on a single development environment the only ability to run individual service and satisfy its service dependencies is to connect to the development kubernetes cluster using VPN. Here is the [instruction](https://github.com/OpenMAVN/Welcome/blob/master/vpn-connection-configuration.md) for trusted contributors about how to get vpn access.    


After you connected using VPN you should navigate to [http://settingsv2.settings.svc.cluster.local/Home/Repository](http://settingsv2.settings.svc.cluster.local/Home/Repository) and find the service you are trying to run in the “Name” column. Then follow the appropriate link from the “Connection URL” column. The response will contain all service URLs ready to be used inside the development kubernetes cluster.