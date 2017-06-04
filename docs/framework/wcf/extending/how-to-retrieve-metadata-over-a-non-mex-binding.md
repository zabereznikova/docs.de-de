---
title: "Vorgehensweise: Abrufen von Metadaten &#252;ber eine Nicht-MEX-Bindung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Vorgehensweise: Abrufen von Metadaten &#252;ber eine Nicht-MEX-Bindung
In diesem Thema wird beschrieben, wie Metadaten über eine Nicht\-MEX\-Bindung von einem MEX\-Endpunkt abgerufen werden.In diesem Beispiel basiert der Code auf dem [Benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)\-Beispiel.  
  
### So rufen Sie Metadaten über eine Nicht\-MEX\-Bindung ab  
  
1.  Bestimmen Sie die vom MEX\-Endpunkt verwendete Bindung.Für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste können Sie die MEX\-Bindung ermitteln, indem Sie die Konfigurationsdatei des Diensts aufrufen.In diesem Fall wird die MEX\-Bindung in der folgenden Dienstkonfiguration definiert.  
  
    ```  
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
  
2.  Konfigurieren Sie in der Clientkonfigurationsdatei die gleiche benutzerdefinierte Bindung.Hier definiert der Client auch ein `clientCredentials`\-Verhalten, um ein Zertifikat bereitzustellen, das beim Abrufen von Metadaten vom MEX\-Endpunkt für die Authentifizierung am Dienst verwendet wird.Wenn Sie "Svcutil.exe" zum Anfordern von Metadaten über eine benutzerdefinierte Bindung verwenden, sollten Sie die MEX\-Endpunktkonfiguration der Konfigurationsdatei für "Svcutil.exe" \(Svcutil.exe.config\) hinzufügen. Der Name der Endpunktkonfiguration sollte dann mit dem URI\-Schema der MEX\-Endpunktadresse übereinstimmen, wie im folgenden Code dargestellt:  
  
    ```  
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
  
3.  Erstellen Sie einen `MetadataExchangeClient`, und rufen Sie `GetMetadata` auf.Dazu stehen zwei Methoden zur Verfügung: Sie können die benutzerdefinierte Bindung in der Konfiguration angeben oder die benutzerdefinierte Bindung im Code, wie im folgenden Beispiel gezeigt:  
  
    ```  
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
  
4.  Erstellen Sie ein `WsdlImporter`\-Element, und rufen Sie `ImportAllEndpoints` auf, wie im folgenden Code gezeigt.  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5.  An diesem Punkt verfügen Sie über eine Auflistung von Dienstendpunkten.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Importieren von Metadaten finden Sie unter [Vorgehensweise: Importieren von Metadaten in Dienstendpunkte](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).  
  
## Siehe auch  
 [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md)