## Sample Network Reference Architecture
This repository contains the code that can be used to provision a VNET in Azure
* via Infrastructure-as-Code
* according to a common deployment pattern

The common pattern will go as following ;
* Typically use a /16 network (f.e. 10.40.0.0/16) as the address space for the VNET
* Use the last /24 range (f.e. 10.40.254.0/16) for the Gateway & DMZ subnets
* Provide the ability to rollout subnets in the unused space before the DMZ ranges (f.e. 10.40.0.0 - 10.40.253.254)
* It will follow a common naming pattern like "SUBNETxxx" for the regular subnets and "SUBNETDMZ" for the ones from DMZ. The gatway subnet will use the mandatory "GatewaySubnet" as name"

![Example VNET Subnets](/Screenshots/Example-VNET-subnets.png)

The template files also have an accompanying .tests file that can be picked up by pester for unit/integration testing. The tests will include some basic unit testing and will do several test deployments as a kind of smoke test /syntax validation.

![Example Build Pester](/Screenshots/Example-Build-pester.png)

You can find exports of the Build & Release definitions under the [VSTS](/VSTS) folder in this repository. The release definition can be imported with out-of-the-box VSTS functionality. For the build definition, you'll need to use the following extension ; [Export/Import Build Definition](https://marketplace.visualstudio.com/items?itemName=onlyutkarsh.ExportImportBuildDefinition)

## Tasmanian Traders
Tasmanian Traders is a [fictional Microsoft company](https://en.wikipedia.org/wiki/List_of_fictional_Microsoft_companies) which I found to be a very cool name. It makes me think back towards the Tasmanian Devil in Looney Tunes. Here I've "borrowed" the name as a kind of theme for all demos related to Azure.
