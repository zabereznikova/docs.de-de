---
title: Metadaten abrufen
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: c5512ab2c1aea573feb1515aa220fd00bcb82c02
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716492"
---
# <a name="retrieve-metadata"></a>Metadaten abrufen
Dieses Beispiel veranschaulicht, wie ein Client implementiert werden kann, der Metadaten dynamisch von einem Dienst abruft, um einen Endpunkt für die Kommunikation auszuwählen. Dieses Beispiel basiert [auf den ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritten. Der Dienst wurde so geändert, dass zwei Endpunkte verfügbar gemacht werden – ein Endpunkt an der Basisadresse mithilfe der `basicHttpBinding` Bindung und ein sicherer Endpunkt unter {*BaseAddress*}/Secure mithilfe der `wsHttpBinding` Bindung. Anstatt den Client mit den Endpunktadressen und -bindungen zu konfigurieren, ruft der Client mithilfe der Klasse  <xref:System.ServiceModel.Description.MetadataExchangeClient> dynamisch die Metadaten für den Dienst ab und importiert sie danach als <xref:System.ServiceModel.Description.ServiceEndpointCollection> mithilfe der <xref:System.ServiceModel.Description.WsdlImporter>-Klasse.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Clientanwendung verwendet die importierte <xref:System.ServiceModel.Description.ServiceEndpointCollection>, um Clients für die Kommunikation mit dem Dienst zu erstellen. Die Clientanwendung durchläuft jeden empfangenen Endpunkt und kommuniziert mit jedem Endpunkt, der den `ICalculator`-Vertrag implementiert. Die geeignete Adresse und Bindung werden zusammen mit dem empfangenen Endpunkt bereitgestellt, sodass der Client für die Kommunikation mit den einzelnen Endpunkten konfiguriert wird, wie im folgenden Beispielcode gezeigt.  
  
```csharp   
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
```  
  
 Das Clientkonsolenfenster zeigt die an jeden Endpunkt gesendeten Vorgänge an (unter Angabe von Adresspfad und Bindungsnamen).  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Befolgen Sie zum C#erstellen C++der-,-oder-Visual Basic .NET-Edition der Projekt Mappe die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
