---
title: 'Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadatenaustausch-Bindung'
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 3d6f74d88dc9db775718c0098eccced4750d3b75
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184503"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a>Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadatenaustausch-Bindung
In diesem Thema wird erläutert, wie Sie eine benutzerdefinierte WS-Metadatenaustausch-Bindung konfigurieren. Windows Communication Foundation (WCF) enthält vier vom System definierte metadatenbindungen, aber Sie können Metadaten mit jeder gewünschten Bindung veröffentlichen. In diesem Thema wird beschrieben, wie Metadaten mit der `wsHttpBinding` veröffentlicht werden. Diese Bindung ermöglicht es Ihnen, Metadaten auf eine sichere Weise verfügbar zu machen. Der Code in diesem Artikel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
### <a name="using-a-configuration-file"></a>Verwenden einer Konfigurationsdatei  
  
1.  Fügen Sie in der Konfigurationsdatei des Dienstes ein Dienstverhalten hinzu, das das `serviceMetadata`-Tag enthält:  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  Fügen Sie dem Dienst-Tag ein `behaviorConfiguration`-Attribut hinzu, das auf dieses neue Verhalten verweist:  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3.  Fügen Sie einen Metadatenendpunkt hinzu, der MEX als Adresse, `wsHttpBinding` als Bindung und <xref:System.ServiceModel.Description.IMetadataExchange> als Vertrag angibt:  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4.  Fügen Sie ein Endpunkt-Tag in der Client-Konfigurationsdatei hinzu, um zu überprüfen, ob der Metadatenaustausch-Endpunkt ordnungsgemäß funktioniert:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5.  Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie ihre <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a>Konfigurieren durch Code  
  
1.  Erstellen Sie eine <xref:System.ServiceModel.WSHttpBinding>-Bindungsinstanz:  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2.  Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz:  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3.  Fügen Sie einen Dienstendpunkt hinzu, und fügen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz hinzu:  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4.  Fügen Sie einen Metadatenaustausch-Endpunkt hinzu, der die zuvor erstellte <xref:System.ServiceModel.WSHttpBinding> angibt:  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5.  Fügen Sie ein Endpunkt-Tag in der Client-Konfigurationsdatei hinzu, um zu überprüfen, ob der Metadatenaustausch-Endpunkt ordnungsgemäß funktioniert:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6.  Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie die <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenveröffentlichungsverhalten](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)  
 [Metadaten abrufen](../../../../docs/framework/wcf/samples/retrieve-metadata.md)  
 [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [Veröffentlichen von Metadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [Veröffentlichen von Metadatenendpunkten](../../../../docs/framework/wcf/publishing-metadata-endpoints.md)
