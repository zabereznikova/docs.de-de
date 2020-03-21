---
title: Nachrichtensicherheit durch gegenseitige Zertifikate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: e2aaf1a5e6ae1074a81c08fc798f22ea5e9ce139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184609"
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="df5bb-102">Nachrichtensicherheit durch gegenseitige Zertifikate</span><span class="sxs-lookup"><span data-stu-id="df5bb-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="df5bb-103">Das folgende Szenario zeigt einen Windows Communication Foundation (WCF)-Dienst und einen Client, der im Nachrichtensicherheitsmodus gesichert ist.</span><span class="sxs-lookup"><span data-stu-id="df5bb-103">The following scenario shows a Windows Communication Foundation (WCF) service and client secured using message security mode.</span></span> <span data-ttu-id="df5bb-104">Sowohl der Client als auch der Dienst werden mit Zertifikaten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="df5bb-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="df5bb-105">Dieses Szenario ist interoperabel, da es WS-Sicherheit mit dem X.509-Zertifikatstokenprofil verwendet.</span><span class="sxs-lookup"><span data-stu-id="df5bb-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df5bb-106">Dieses Szenario führt keine Aushandlung für das Dienstzertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="df5bb-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="df5bb-107">Das Dienstzertifikat muss dem Client vor jeder Kommunikation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="df5bb-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="df5bb-108">Das Serverzertifikat kann mit der Anwendung oder im Rahmen einer Out-of-Band-Kommunikation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="df5bb-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="df5bb-109">![Nachrichtensicherheit mit gegenseitigen Zertifikaten](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="df5bb-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="df5bb-110">Merkmal</span><span class="sxs-lookup"><span data-stu-id="df5bb-110">Characteristic</span></span>|<span data-ttu-id="df5bb-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df5bb-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="df5bb-112">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="df5bb-112">Security Mode</span></span>|<span data-ttu-id="df5bb-113">`Message`</span><span class="sxs-lookup"><span data-stu-id="df5bb-113">Message</span></span>|  
|<span data-ttu-id="df5bb-114">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="df5bb-114">Interoperability</span></span>|<span data-ttu-id="df5bb-115">Ja, mit WS-Sicherheit und X.509-Zertifikatstokenprofil kompatible Clients und Dienste.</span><span class="sxs-lookup"><span data-stu-id="df5bb-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="df5bb-116">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="df5bb-116">Authentication</span></span>|<span data-ttu-id="df5bb-117">Gegenseitige Authentifizierung des Servers und des Clients.</span><span class="sxs-lookup"><span data-stu-id="df5bb-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="df5bb-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="df5bb-118">Integrity</span></span>|<span data-ttu-id="df5bb-119">Ja</span><span class="sxs-lookup"><span data-stu-id="df5bb-119">Yes</span></span>|  
|<span data-ttu-id="df5bb-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="df5bb-120">Confidentiality</span></span>|<span data-ttu-id="df5bb-121">Ja</span><span class="sxs-lookup"><span data-stu-id="df5bb-121">Yes</span></span>|  
|<span data-ttu-id="df5bb-122">Transport</span><span class="sxs-lookup"><span data-stu-id="df5bb-122">Transport</span></span>|<span data-ttu-id="df5bb-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="df5bb-123">HTTP</span></span>|  
|<span data-ttu-id="df5bb-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="df5bb-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="df5bb-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="df5bb-125">Service</span></span>  
 <span data-ttu-id="df5bb-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="df5bb-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="df5bb-127">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="df5bb-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="df5bb-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="df5bb-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="df5bb-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="df5bb-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="df5bb-130">Code</span><span class="sxs-lookup"><span data-stu-id="df5bb-130">Code</span></span>  
 <span data-ttu-id="df5bb-131">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="df5bb-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="df5bb-132">Der Dienst benötigt ein Zertifikat, um sich zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="df5bb-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="df5bb-133">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="df5bb-133">Configuration</span></span>  
 <span data-ttu-id="df5bb-134">Die folgende Konfiguration kann statt des Codes verwendet werden, um denselben Dienst einzurichten.</span><span class="sxs-lookup"><span data-stu-id="df5bb-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="df5bb-135">Client</span><span class="sxs-lookup"><span data-stu-id="df5bb-135">Client</span></span>  
 <span data-ttu-id="df5bb-136">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="df5bb-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="df5bb-137">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="df5bb-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="df5bb-138">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="df5bb-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="df5bb-139">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="df5bb-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="df5bb-140">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="df5bb-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="df5bb-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df5bb-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="df5bb-142">Code</span><span class="sxs-lookup"><span data-stu-id="df5bb-142">Code</span></span>  
 <span data-ttu-id="df5bb-143">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="df5bb-143">The following code creates the client.</span></span> <span data-ttu-id="df5bb-144">Der Sicherheitsmodus wird auf "Nachricht" und der Clientanmeldeinformationstyp wird auf "Zertifikat" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="df5bb-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="df5bb-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="df5bb-145">Configuration</span></span>  
 <span data-ttu-id="df5bb-146">Der Client wird wie folgt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="df5bb-146">The following configures the client.</span></span> <span data-ttu-id="df5bb-147">Ein Clientzertifikat muss mithilfe des [ \<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="df5bb-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="df5bb-148">Außerdem wird das Dienstzertifikat mit dem [ \<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="df5bb-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="df5bb-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df5bb-149">See also</span></span>

- [<span data-ttu-id="df5bb-150">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="df5bb-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="df5bb-151">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="df5bb-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
- <span data-ttu-id="df5bb-152">[Gewusst wie: Erstellen und Installieren temporärer Zertifikate in WCF für Transportsicherheit während der Entwicklung](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="df5bb-152">[How to: Create and Install Temporary Certificates in WCF for Transport Security During Development](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))</span></span>
