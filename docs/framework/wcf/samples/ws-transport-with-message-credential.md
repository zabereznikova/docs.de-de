---
title: WS-Transport mit Nachrichtenanmeldeinformationen
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 44f37e3576b508e679d45a3cbafacfb5a68a7838
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030180"
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="4560e-102">WS-Transport mit Nachrichtenanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="4560e-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="4560e-103">In diesem Beispiel wird die Verwendung der SSL-Transportsicherheit in Verbindung mit Clientanmeldeinformationen veranschaulicht, die in der Nachricht übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="4560e-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="4560e-104">In diesem Beispiel wird die `wsHttpBinding`-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4560e-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="4560e-105">Standardmäßig bietet die `wsHttpBinding`-Bindung HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="4560e-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="4560e-106">Wenn die Bindung für Transportsicherheit konfiguriert ist, unterstützt sie HTTPS-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="4560e-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="4560e-107">HTTPS stellt Vertraulichkeit und Integritätsschutz für die über die Verbindung übertragenen Nachrichten bereit.</span><span class="sxs-lookup"><span data-stu-id="4560e-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="4560e-108">Die Authentifizierungsmechanismen, die zum Authentifizieren des Clients beim Dienst verwendet werden können, sind jedoch auf die Mechanismen beschränkt, die der HTTPS-Transport unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4560e-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> <span data-ttu-id="4560e-109">Windows Communication Foundation (WCF) bietet eine `TransportWithMessageCredential` Sicherheitsmodus, die entwickelt wird, um diese Einschränkung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="4560e-109">Windows Communication Foundation (WCF) offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="4560e-110">Wenn dieser Sicherheitsmodus konfiguriert ist, werden mithilfe der Transportsicherheit Vertraulichkeit und Integrität für die übertragenen Nachrichten bereitgestellt und die Dienstauthentifizierung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4560e-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="4560e-111">Die Clientauthentifizierung wird jedoch ausgeführt, indem die Clientanmeldeinformationen direkt in der Nachricht übertragen.</span><span class="sxs-lookup"><span data-stu-id="4560e-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="4560e-112">Dadurch können Sie jeden Anmeldeinformationstyp verwenden, die vom Modus für die nachrichtensicherheit für die Clientauthentifizierung verwenden und halten den Leistungsvorteil von transportsicherheitsmodus unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4560e-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="4560e-113">In diesem Beispiel wird der `UserName`-Anmeldeinformationstyp verwendet, um den Client beim Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4560e-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="4560e-114">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="4560e-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="4560e-115">Die `wsHttpBinding`-Bindung wird in den Anwendungskonfigurationsdateien für den Client und den Dienst angegeben und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4560e-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4560e-116">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="4560e-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4560e-117">Der Programmcode im Beispiel ist fast identisch mit der die [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) Service.</span><span class="sxs-lookup"><span data-stu-id="4560e-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="4560e-118">Es gibt einen zusätzlichen vom Dienstvertrag bereitgestellten Vorgang: `GetCallerIdentity`.</span><span class="sxs-lookup"><span data-stu-id="4560e-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="4560e-119">Dieser Vorgang gibt den Namen der Identität des Aufrufers an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="4560e-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="4560e-120">Sie müssen ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen, bevor Sie das Beispiel erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="4560e-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="4560e-121">Durch die Endpunktdefinition und Bindungsdefinition in den Einstellungen der Konfigurationsdatei wird der `TransportWithMessageCredential`-Sicherheitsmodus aktiviert, wie in der folgenden Beispielkonfiguration für den Client dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4560e-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="4560e-122">Für die angegebene Adresse wird das https:// Schema verwendet.</span><span class="sxs-lookup"><span data-stu-id="4560e-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="4560e-123">Die Bindungskonfiguration legt den Sicherheitsmodus auf `TransportWithMessageCredential` fest.</span><span class="sxs-lookup"><span data-stu-id="4560e-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="4560e-124">Der gleiche Sicherheitsmodus muss in der Datei "Web.config" für den Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4560e-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="4560e-125">Da das in diesem Beispiel verwendete Zertifikat ein mit Makecert.exe erstelltes Testzertifikat ist, wird eine sicherheitswarnung angezeigt, wenn Sie versuchen, eine Https-Zugriff: Adresse, z. B. `https://localhost/servicemodelsamples/service.svc `, in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="4560e-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as  `https://localhost/servicemodelsamples/service.svc `, from your browser.</span></span> <span data-ttu-id="4560e-126">Damit den WCF-Client mit einem vorhandenen Testzertifikat arbeiten kann, wurde an den Client, um die sicherheitswarnung zu unterdrücken, zusätzlicher Code hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4560e-126">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="4560e-127">Dieser Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4560e-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="4560e-128">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4560e-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="4560e-129">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4560e-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4560e-130">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="4560e-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4560e-131">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4560e-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4560e-132">Stellen Sie sicher, dass Sie ausgeführt haben die [Installationsanweisungen zu Serverzertifikaten (Internet Information Services, IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="4560e-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3.  <span data-ttu-id="4560e-133">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4560e-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="4560e-134">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4560e-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4560e-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4560e-135">See Also</span></span>
