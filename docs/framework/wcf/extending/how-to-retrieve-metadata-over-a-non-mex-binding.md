---
title: 'Vorgehensweise: Aufrufen von Metadaten über eine Nicht-MEX-Bindung'
ms.date: 03/30/2017
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
ms.openlocfilehash: db4bad81241295e168685c8b80546f2305021066
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249019"
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a>Vorgehensweise: Aufrufen von Metadaten über eine Nicht-MEX-Bindung

In diesem Thema wird beschrieben, wie Metadaten über eine Nicht-MEX-Bindung von einem MEX-Endpunkt abgerufen werden. Der Code in diesem Beispiel basiert auf dem Beispiel für einen [benutzerdefinierten sicheren Metadatenendpunkt](../samples/custom-secure-metadata-endpoint.md) .  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a>So rufen Sie Metadaten über eine Nicht-MEX-Bindung ab  
  
1. Bestimmen Sie die vom MEX-Endpunkt verwendete Bindung. Für Windows Communication Foundation (WCF)-Dienste können Sie die MEX-Bindung ermitteln, indem Sie auf die Konfigurationsdatei des Diensts zugreifen. In diesem Fall wird die MEX-Bindung in der folgenden Dienstkonfiguration definiert.  
  
    ```xml  
    <services>  
        <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                behaviorConfiguration="CalculatorServiceBehavior">  
         <!-- Use the base address provided by the host. -->  
         <endpoint address=""  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding2"  
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
         <endpoint address="mex"  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding1"  
           contract="IMetadataExchange" />  
         </service>  
     </services>  
     <bindings>  
       <wsHttpBinding>  
         <binding name="Binding1">  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
         <binding name="Binding2">  
           <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
       </wsHttpBinding>  
     </bindings>  
    ```  
  
2. Konfigurieren Sie in der Clientkonfigurationsdatei die gleiche benutzerdefinierte Bindung. Hier definiert der Client auch ein `clientCredentials`-Verhalten, um ein Zertifikat bereitzustellen, das beim Abrufen von Metadaten vom MEX-Endpunkt für die Authentifizierung am Dienst verwendet wird. Wenn Sie „Svcutil.exe“ zum Anfordern von Metadaten über eine benutzerdefinierte Bindung verwenden, sollten Sie die MEX-Endpunktkonfiguration der Konfigurationsdatei für „Svcutil.exe“ (Svcutil.exe.config) hinzufügen. Der Name der Endpunktkonfiguration sollte dann mit dem URI-Schema der MEX-Endpunktadresse übereinstimmen, wie im folgenden Code dargestellt:  
  
    ```xml  
    <system.serviceModel>  
      <client>  
        <endpoint name="http"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientCertificateBehavior"  
                  contract="IMetadataExchange" />  
      </client>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="Certificate"/>  
            </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="ClientCertificateBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
              <serviceCertificate>  
                <authentication certificateValidationMode="PeerOrChainTrust" />  
              </serviceCertificate>  
            </clientCredentials>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>
    </system.serviceModel>  
    ```  
  
3. Erstellen Sie einen `MetadataExchangeClient`, und rufen Sie `GetMetadata` auf. Dazu stehen zwei Methoden zur Verfügung: Sie können die benutzerdefinierte Bindung in der Konfiguration angeben oder die benutzerdefinierte Bindung im Code, wie im folgenden Beispiel gezeigt:  
  
    ```csharp
    // The custom binding is specified in configuration.  
    EndpointAddress mexAddress = new EndpointAddress("http://localhost:8000/ServiceModelSamples/Service/mex");  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("http");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mexSet = mexClient.GetMetadata(mexAddress);  
  
    // The custom binding is specified in code.  
    // Specify the Metadata Exchange binding and its security mode.  
    WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
    mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
    // Create a MetadataExchangeClient and set the certificate details.  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
    mexClient.SoapCredentials.ClientCertificate.SetCertificate(  
        StoreLocation.CurrentUser, StoreName.My,  
        X509FindType.FindBySubjectName, "client.com");  
    mexClient.SoapCredentials.ServiceCertificate.Authentication.  
        CertificateValidationMode =  
        X509CertificateValidationMode.PeerOrChainTrust;  
    mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(  
        StoreLocation.CurrentUser, StoreName.TrustedPeople,  
        X509FindType.FindBySubjectName, "localhost");  
    MetadataExchangeClient mexClient2 = new MetadataExchangeClient(customBinding);  
    mexClient2.ResolveMetadataReferences = true;  
    MetadataSet mexSet2 = mexClient2.GetMetadata(mexAddress);  
    ```  
  
4. Erstellen Sie ein `WsdlImporter`-Element, und rufen Sie `ImportAllEndpoints` auf, wie im folgenden Code gezeigt.  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5. An diesem Punkt verfügen Sie über eine Auflistung von Dienstendpunkten. Weitere Informationen zum Importieren von Metadaten finden Sie unter Gewusst [wie: Importieren von Metadaten in Dienst Endpunkte](../feature-details/how-to-import-metadata-into-service-endpoints.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadaten](../feature-details/metadata.md)
