---
title: 'Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung'
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 6459e3f0cf0ab72af8027bd6802a0e7aa574aece
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635784"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a>Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung

In diesem Artikel wird erläutert, wie Sie eine benutzerdefinierte WS-Metadata-Austauschbindung konfigurieren. Windows Communication Foundation (WCF) enthält vier systemdefinierte Metadatenbindungen, Sie können Metadaten jedoch mit einer beliebigen Bindung veröffentlichen. In diesem Artikel erfahren Sie, `wsHttpBinding`wie Sie Metadaten mit der veröffentlichen. Diese Bindung ermöglicht es Ihnen, Metadaten auf eine sichere Weise verfügbar zu machen. Der Code in diesem Artikel basiert auf der [Ersten Schritte](../samples/getting-started-sample.md).  
  
### <a name="using-a-configuration-file"></a>Verwenden einer Konfigurationsdatei  
  
1. Fügen Sie in der Konfigurationsdatei des Dienstes ein Dienstverhalten hinzu, das das `serviceMetadata`-Tag enthält:  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. Fügen Sie dem Dienst-Tag ein `behaviorConfiguration`-Attribut hinzu, das auf dieses neue Verhalten verweist:  
  
    ```xml  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior" />
    ```  
  
3. Fügen Sie einen Metadatenendpunkt hinzu, der MEX als Adresse, `wsHttpBinding` als Bindung und <xref:System.ServiceModel.Description.IMetadataExchange> als Vertrag angibt:  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. Um zu überprüfen, ob der Metadatenaustauschendpunkt ordnungsgemäß funktioniert, fügen Sie der Clientkonfigurationsdatei ein Endpunkt-Tag hinzu:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie ihre <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:  
  
    ```csharp
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a>Konfigurieren durch Code  
  
1. Erstellen Sie eine <xref:System.ServiceModel.WSHttpBinding>-Bindungsinstanz:  
  
    ```csharp  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz:  
  
    ```csharp  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. Fügen Sie einen Dienstendpunkt hinzu, und fügen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz hinzu:  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. Fügen Sie einen Metadatenaustausch-Endpunkt hinzu, der die zuvor erstellte <xref:System.ServiceModel.WSHttpBinding> angibt:  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. Fügen Sie ein Endpunkt-Tag in der Client-Konfigurationsdatei hinzu, um zu überprüfen, ob der Metadatenaustausch-Endpunkt ordnungsgemäß funktioniert:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie die <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:  
  
    ```csharp  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenveröffentlichungsverhalten](../samples/metadata-publishing-behavior.md)
- [Metadaten abrufen](../samples/retrieve-metadata.md)
- [Metadaten](../feature-details/metadata.md)
- [Veröffentlichen von Metadaten](../feature-details/publishing-metadata.md)
- [Veröffentlichen von Metadatenendpunkten](../publishing-metadata-endpoints.md)
