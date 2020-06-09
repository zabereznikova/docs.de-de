---
title: Transportsicherheit mit Zertifikatauthentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: 47322cbcddf9f33101bbfbeaa07a3fab74b9d26a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576017"
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="d7775-102">Transportsicherheit mit Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="d7775-102">Transport Security with Certificate Authentication</span></span>

<span data-ttu-id="d7775-103">In diesem Artikel wird die Verwendung von X. 509-Zertifikaten für die Server-und Client Authentifizierung bei der Transportsicherheit erläutert.</span><span class="sxs-lookup"><span data-stu-id="d7775-103">This article discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="d7775-104">Weitere Informationen zu X.509-Zertifikaten finden Sie unter [X.509 Public Key Certificates (X.509-Zertifikate mit öffentlichem Schlüssel)](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span><span class="sxs-lookup"><span data-stu-id="d7775-104">For more information about X.509 certificates see [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span></span> <span data-ttu-id="d7775-105">Zertifikate müssen von einer Zertifizierungsstelle ausgestellt werden, bei der es sich oft um einen Drittanbieter von Zertifikaten handelt.</span><span class="sxs-lookup"><span data-stu-id="d7775-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="d7775-106">In einer Windows Server-Domäne können Sie Active Directory-Zertifikatdienste verwenden, um Zertifikate für Clientcomputer in der Domäne auszustellen.</span><span class="sxs-lookup"><span data-stu-id="d7775-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="d7775-107">In diesem Szenario wird der Dienst unter Internetinformationsdienste (IIS) konfiguriert mit Secure Sockets Layer (SSL) gehostet.</span><span class="sxs-lookup"><span data-stu-id="d7775-107">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="d7775-108">Der Dienst ist mit einem SSL-Zertifikat (X.509) konfiguriert, um Clients das Überprüfen der Identität des Servers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d7775-108">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="d7775-109">Der Client ist ebenfalls mit einem X.509-Zertifikat konfiguriert, das es dem Dienst ermöglicht, die Identität des Clients zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d7775-109">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="d7775-110">Das Zertifikat des Servers muss für den Client vertrauenswürdig sein und das Zertifikat des Clients für den Server.</span><span class="sxs-lookup"><span data-stu-id="d7775-110">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="d7775-111">Die tatsächliche Funktionsweise, in der der Dienst und der Client die Identität der anderen überprüfen, würde den Rahmen dieses Artikels sprengen.</span><span class="sxs-lookup"><span data-stu-id="d7775-111">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this article.</span></span> <span data-ttu-id="d7775-112">Weitere Informationen finden Sie unter [digitale Signatur](https://en.wikipedia.org/wiki/Digital_signature) auf Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="d7775-112">For more information, see [Digital Signature](https://en.wikipedia.org/wiki/Digital_signature) on Wikipedia.</span></span>
  
 <span data-ttu-id="d7775-113">In diesem Szenario wird das im folgenden Diagramm dargestellte Anforderungs-/Antwortnachrichtenmuster implementiert.</span><span class="sxs-lookup"><span data-stu-id="d7775-113">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="d7775-114">![Sichere Übertragung mit Zertifikaten](media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f 7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="d7775-114">![Secure transfer using certificates](media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 <span data-ttu-id="d7775-115">Weitere Informationen zum Verwenden eines Zertifikats mit einem Dienst finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md) und Gewusst [wie: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="d7775-115">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="d7775-116">In der folgenden Tabelle werden die verschiedenen Merkmale des Szenarios beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7775-116">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="d7775-117">Merkmal</span><span class="sxs-lookup"><span data-stu-id="d7775-117">Characteristic</span></span>|<span data-ttu-id="d7775-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d7775-118">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d7775-119">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="d7775-119">Security Mode</span></span>|<span data-ttu-id="d7775-120">Transport</span><span class="sxs-lookup"><span data-stu-id="d7775-120">Transport</span></span>|  
|<span data-ttu-id="d7775-121">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="d7775-121">Interoperability</span></span>|<span data-ttu-id="d7775-122">Mit vorhandenen Webdienstclients und Diensten.</span><span class="sxs-lookup"><span data-stu-id="d7775-122">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="d7775-123">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="d7775-123">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="d7775-124">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="d7775-124">Authentication (Client)</span></span>|<span data-ttu-id="d7775-125">Ja (mit einem SSL-Zertifikat)</span><span class="sxs-lookup"><span data-stu-id="d7775-125">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="d7775-126">Ja (mit einem X.509-Zertifikat)</span><span class="sxs-lookup"><span data-stu-id="d7775-126">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="d7775-127">Datenintegrität</span><span class="sxs-lookup"><span data-stu-id="d7775-127">Data Integrity</span></span>|<span data-ttu-id="d7775-128">Ja</span><span class="sxs-lookup"><span data-stu-id="d7775-128">Yes</span></span>|  
|<span data-ttu-id="d7775-129">Datenvertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="d7775-129">Data Confidentiality</span></span>|<span data-ttu-id="d7775-130">Ja</span><span class="sxs-lookup"><span data-stu-id="d7775-130">Yes</span></span>|  
|<span data-ttu-id="d7775-131">Transport</span><span class="sxs-lookup"><span data-stu-id="d7775-131">Transport</span></span>|<span data-ttu-id="d7775-132">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d7775-132">HTTPS</span></span>|  
|<span data-ttu-id="d7775-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="d7775-133">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="d7775-134">Konfigurieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="d7775-134">Configure the Service</span></span>  
 <span data-ttu-id="d7775-135">Da der Dienst in diesem Szenario unter IIS gehostet wird, wird er mit einer Datei "web.config" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d7775-135">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="d7775-136">Die folgende Datei "web.config" zeigt, wie die <xref:System.ServiceModel.WSHttpBinding> zur Verwendung von Transportsicherheit und X.509-Clientanmeldeinformationen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="d7775-136">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a><span data-ttu-id="d7775-137">Konfigurieren des Clients</span><span class="sxs-lookup"><span data-stu-id="d7775-137">Configure the Client</span></span>  
 <span data-ttu-id="d7775-138">Der Client kann im Code oder in einer Datei "app.config" konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d7775-138">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="d7775-139">Das folgende Beispiel zeigt, wie Sie den Client im Code konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d7775-139">The following example shows how to configure the client in code.</span></span>  
  
```csharp
// Create the binding.  
var myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.
var ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
var cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 <span data-ttu-id="d7775-140">Alternativ können Sie den Client wie im folgenden Beispiel dargestellt in einer Datei "app.config" konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="d7775-140">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7775-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7775-141">See also</span></span>

- [<span data-ttu-id="d7775-142">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="d7775-142">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="d7775-143">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d7775-143">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
