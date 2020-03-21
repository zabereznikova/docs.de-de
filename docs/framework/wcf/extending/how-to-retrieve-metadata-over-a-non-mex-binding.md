---
title: 'Vorgehensweise: Abrufen von Metadaten über eine Nicht-MEX-Bindung'
ms.date: 03/30/2017
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
ms.openlocfilehash: a006795c87a2ae845d03db90dce296692c4339fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186444"
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="5c837-102">Vorgehensweise: Abrufen von Metadaten über eine Nicht-MEX-Bindung</span><span class="sxs-lookup"><span data-stu-id="5c837-102">How to: Retrieve Metadata Over a non-MEX Binding</span></span>
<span data-ttu-id="5c837-103">In diesem Thema wird beschrieben, wie Metadaten über eine Nicht-MEX-Bindung von einem MEX-Endpunkt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5c837-103">This topic describes how to retrieve metadata from a MEX endpoint over a non-MEX binding.</span></span> <span data-ttu-id="5c837-104">Der Code in diesem Beispiel basiert auf dem [Custom Secure Metadata Endpoint-Beispiel.](../samples/custom-secure-metadata-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="5c837-104">The code in this sample is based on the [Custom Secure Metadata Endpoint](../samples/custom-secure-metadata-endpoint.md) sample.</span></span>  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="5c837-105">So rufen Sie Metadaten über eine Nicht-MEX-Bindung ab</span><span class="sxs-lookup"><span data-stu-id="5c837-105">To retrieve metadata over a non-MEX binding</span></span>  
  
1. <span data-ttu-id="5c837-106">Bestimmen Sie die vom MEX-Endpunkt verwendete Bindung.</span><span class="sxs-lookup"><span data-stu-id="5c837-106">Determine the binding used by the MEX endpoint.</span></span> <span data-ttu-id="5c837-107">Bei Windows Communication Foundation (WCF)-Diensten können Sie die MEX-Bindung ermitteln, indem Sie auf die Konfigurationsdatei des Dienstes zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5c837-107">For Windows Communication Foundation (WCF) services, you can determine the MEX binding by accessing the service's configuration file.</span></span> <span data-ttu-id="5c837-108">In diesem Fall wird die MEX-Bindung in der folgenden Dienstkonfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="5c837-108">In this case, the MEX binding is defined in the following service configuration.</span></span>  
  
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
  
2. <span data-ttu-id="5c837-109">Konfigurieren Sie in der Clientkonfigurationsdatei die gleiche benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="5c837-109">In the client configuration file, configure the same custom binding.</span></span> <span data-ttu-id="5c837-110">Hier definiert der Client auch ein `clientCredentials`-Verhalten, um ein Zertifikat bereitzustellen, das beim Abrufen von Metadaten vom MEX-Endpunkt für die Authentifizierung am Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c837-110">Here the client also defines a `clientCredentials` behavior to provide a certificate to use to authenticate to the service when requesting metadata from the MEX endpoint.</span></span> <span data-ttu-id="5c837-111">Wenn Sie „Svcutil.exe“ zum Anfordern von Metadaten über eine benutzerdefinierte Bindung verwenden, sollten Sie die MEX-Endpunktkonfiguration der Konfigurationsdatei für „Svcutil.exe“ (Svcutil.exe.config) hinzufügen. Der Name der Endpunktkonfiguration sollte dann mit dem URI-Schema der MEX-Endpunktadresse übereinstimmen, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="5c837-111">When using Svcutil.exe to request metadata over a custom binding, you should add the MEX endpoint configuration to the configuration file for Svcutil.exe (Svcutil.exe.config), and the name of the endpoint configuration should match the URI scheme of the address of the MEX endpoint, as shown in the following code.</span></span>  
  
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
  
3. <span data-ttu-id="5c837-112">Erstellen Sie einen `MetadataExchangeClient`, und rufen Sie `GetMetadata` auf.</span><span class="sxs-lookup"><span data-stu-id="5c837-112">Create a `MetadataExchangeClient` and call `GetMetadata`.</span></span> <span data-ttu-id="5c837-113">Dazu stehen zwei Methoden zur Verfügung: Sie können die benutzerdefinierte Bindung in der Konfiguration angeben oder die benutzerdefinierte Bindung im Code, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5c837-113">There are two ways to do this: you can specify the custom binding in configuration, or you can specify the custom binding in code, as shown in the following example.</span></span>  
  
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
  
4. <span data-ttu-id="5c837-114">Erstellen Sie ein `WsdlImporter`-Element, und rufen Sie `ImportAllEndpoints` auf, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c837-114">Create a `WsdlImporter` and call `ImportAllEndpoints`, as shown in the following code.</span></span>  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5. <span data-ttu-id="5c837-115">An diesem Punkt verfügen Sie über eine Auflistung von Dienstendpunkten.</span><span class="sxs-lookup"><span data-stu-id="5c837-115">At this point, you have a collection of service endpoints.</span></span> <span data-ttu-id="5c837-116">Weitere Informationen zum Importieren von Metadaten finden Sie unter [Gewusst wie: Importieren von Metadaten in Serviceendpoints](../feature-details/how-to-import-metadata-into-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="5c837-116">For more information about importing metadata, see [How to: Import Metadata into Service Endpoints](../feature-details/how-to-import-metadata-into-service-endpoints.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c837-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c837-117">See also</span></span>

- [<span data-ttu-id="5c837-118">Metadaten</span><span class="sxs-lookup"><span data-stu-id="5c837-118">Metadata</span></span>](../feature-details/metadata.md)
