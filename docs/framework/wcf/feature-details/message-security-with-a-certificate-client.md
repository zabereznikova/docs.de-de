---
title: Nachrichtensicherheit durch einem Zertifikatclient
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
ms.openlocfilehash: 3660877194931c2be5b9b1c9aa54e2595701697f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184645"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="d37fc-102">Nachrichtensicherheit durch einem Zertifikatclient</span><span class="sxs-lookup"><span data-stu-id="d37fc-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="d37fc-103">Das folgende Szenario zeigt einen Windows Communication Foundation (WCF)-Client und -Dienst, der im Nachrichtensicherheitsmodus gesichert ist.</span><span class="sxs-lookup"><span data-stu-id="d37fc-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="d37fc-104">Sowohl der Client als auch der Dienst werden mit Zertifikaten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="d37fc-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="d37fc-105">Weitere Informationen finden Sie unter [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="d37fc-105">For more information, see [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>

 ![Screenshot, der einen Client mit Zertifikat zeigt.](./media/message-security-with-a-certificate-client/client-with-certificate.gif)  
  
 <span data-ttu-id="d37fc-107">Eine Beispielanwendung finden Sie unter [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="d37fc-107">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  

|<span data-ttu-id="d37fc-108">Merkmal</span><span class="sxs-lookup"><span data-stu-id="d37fc-108">Characteristic</span></span>|<span data-ttu-id="d37fc-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d37fc-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d37fc-110">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="d37fc-110">Security Mode</span></span>|<span data-ttu-id="d37fc-111">`Message`</span><span class="sxs-lookup"><span data-stu-id="d37fc-111">Message</span></span>|  
|<span data-ttu-id="d37fc-112">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="d37fc-112">Interoperability</span></span>|<span data-ttu-id="d37fc-113">Nur WCF</span><span class="sxs-lookup"><span data-stu-id="d37fc-113">WCF only</span></span>|  
|<span data-ttu-id="d37fc-114">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="d37fc-114">Authentication (Server)</span></span>|<span data-ttu-id="d37fc-115">Mit Dienstzertifikat</span><span class="sxs-lookup"><span data-stu-id="d37fc-115">Using service certificate</span></span>|  
|<span data-ttu-id="d37fc-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="d37fc-116">Authentication (Client)</span></span>|<span data-ttu-id="d37fc-117">Mit Clientzertifikat</span><span class="sxs-lookup"><span data-stu-id="d37fc-117">Using client certificate</span></span>|  
|<span data-ttu-id="d37fc-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="d37fc-118">Integrity</span></span>|<span data-ttu-id="d37fc-119">Ja</span><span class="sxs-lookup"><span data-stu-id="d37fc-119">Yes</span></span>|  
|<span data-ttu-id="d37fc-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="d37fc-120">Confidentiality</span></span>|<span data-ttu-id="d37fc-121">Ja</span><span class="sxs-lookup"><span data-stu-id="d37fc-121">Yes</span></span>|  
|<span data-ttu-id="d37fc-122">Transport</span><span class="sxs-lookup"><span data-stu-id="d37fc-122">Transport</span></span>|<span data-ttu-id="d37fc-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="d37fc-123">HTTP</span></span>|  
|<span data-ttu-id="d37fc-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="d37fc-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="d37fc-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="d37fc-125">Service</span></span>  
 <span data-ttu-id="d37fc-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d37fc-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d37fc-127">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="d37fc-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="d37fc-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="d37fc-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="d37fc-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="d37fc-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d37fc-130">Code</span><span class="sxs-lookup"><span data-stu-id="d37fc-130">Code</span></span>  
 <span data-ttu-id="d37fc-131">Der folgende Code zeigt, wie Sie einen Dienstendpunkt erstellen, der zum Herstellen eines sicheren Kontextes die Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="d37fc-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="d37fc-132">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d37fc-132">Configuration</span></span>  
 <span data-ttu-id="d37fc-133">Anstelle des Codes kann die folgende Konfiguration verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d37fc-133">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCertificateClient"
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="d37fc-134">Client</span><span class="sxs-lookup"><span data-stu-id="d37fc-134">Client</span></span>  
 <span data-ttu-id="d37fc-135">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d37fc-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d37fc-136">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="d37fc-136">Do one of the following:</span></span>  
  
- <span data-ttu-id="d37fc-137">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="d37fc-137">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="d37fc-138">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="d37fc-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="d37fc-139">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="d37fc-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="d37fc-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d37fc-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="d37fc-141">Code</span><span class="sxs-lookup"><span data-stu-id="d37fc-141">Code</span></span>  
 <span data-ttu-id="d37fc-142">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="d37fc-142">The following code creates the client.</span></span> <span data-ttu-id="d37fc-143">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `Certificate` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d37fc-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="d37fc-144">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d37fc-144">Configuration</span></span>  
 <span data-ttu-id="d37fc-145">Die folgende Konfiguration gibt das Clientzertifikat mit einem Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="d37fc-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="d37fc-146">Weitere Informationen zu Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d37fc-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="d37fc-147">Der Code verwendet `identity` auch eine <>-Element, um ein Domänennamensystem (DNS) der erwarteten Serveridentität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d37fc-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="d37fc-148">Weitere Informationen zur Identität finden Sie unter [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d37fc-148">For more information about identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d37fc-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d37fc-149">See also</span></span>

- [<span data-ttu-id="d37fc-150">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="d37fc-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="d37fc-151">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d37fc-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d37fc-152">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="d37fc-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- <span data-ttu-id="d37fc-153">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d37fc-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
