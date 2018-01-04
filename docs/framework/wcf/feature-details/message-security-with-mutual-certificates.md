---
title: Nachrichtensicherheit durch gegenseitige Zertifikate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: a60af220bf962e523a35bc5b8d8abca041a9fd46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="6d590-102">Nachrichtensicherheit durch gegenseitige Zertifikate</span><span class="sxs-lookup"><span data-stu-id="6d590-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="6d590-103">Das folgende Szenario zeigt, wie ein Client und ein Dienst von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mit dem Nachrichtensicherheitsmodus gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="6d590-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client secured using message security mode.</span></span> <span data-ttu-id="6d590-104">Sowohl der Client als auch der Dienst werden mit Zertifikaten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="6d590-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="6d590-105">Dieses Szenario ist interoperabel, da es WS-Sicherheit mit dem X.509-Zertifikatstokenprofil verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d590-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d590-106">Dieses Szenario führt keine Aushandlung für das Dienstzertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="6d590-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="6d590-107">Das Dienstzertifikat muss dem Client vor jeder Kommunikation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6d590-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="6d590-108">Das Serverzertifikat kann mit der Anwendung oder im Rahmen einer Out-of-Band-Kommunikation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6d590-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="6d590-109">![Nachrichtensicherheit durch gegenseitige Zertifikate](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="6d590-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="6d590-110">Merkmal</span><span class="sxs-lookup"><span data-stu-id="6d590-110">Characteristic</span></span>|<span data-ttu-id="6d590-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d590-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6d590-112">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="6d590-112">Security Mode</span></span>|<span data-ttu-id="6d590-113">Meldung</span><span class="sxs-lookup"><span data-stu-id="6d590-113">Message</span></span>|  
|<span data-ttu-id="6d590-114">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="6d590-114">Interoperability</span></span>|<span data-ttu-id="6d590-115">Ja, mit WS-Sicherheit und X.509-Zertifikatstokenprofil kompatible Clients und Dienste.</span><span class="sxs-lookup"><span data-stu-id="6d590-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="6d590-116">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6d590-116">Authentication</span></span>|<span data-ttu-id="6d590-117">Gegenseitige Authentifizierung des Servers und des Clients.</span><span class="sxs-lookup"><span data-stu-id="6d590-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="6d590-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="6d590-118">Integrity</span></span>|<span data-ttu-id="6d590-119">Ja</span><span class="sxs-lookup"><span data-stu-id="6d590-119">Yes</span></span>|  
|<span data-ttu-id="6d590-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="6d590-120">Confidentiality</span></span>|<span data-ttu-id="6d590-121">Ja</span><span class="sxs-lookup"><span data-stu-id="6d590-121">Yes</span></span>|  
|<span data-ttu-id="6d590-122">Transport</span><span class="sxs-lookup"><span data-stu-id="6d590-122">Transport</span></span>|<span data-ttu-id="6d590-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="6d590-123">HTTP</span></span>|  
|<span data-ttu-id="6d590-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="6d590-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="6d590-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="6d590-125">Service</span></span>  
 <span data-ttu-id="6d590-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d590-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6d590-127">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6d590-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6d590-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d590-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="6d590-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="6d590-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6d590-130">Code</span><span class="sxs-lookup"><span data-stu-id="6d590-130">Code</span></span>  
 <span data-ttu-id="6d590-131">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6d590-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="6d590-132">Der Dienst benötigt ein Zertifikat, um sich zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d590-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="6d590-133">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6d590-133">Configuration</span></span>  
 <span data-ttu-id="6d590-134">Die folgende Konfiguration kann statt des Codes verwendet werden, um denselben Dienst einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6d590-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="6d590-135">Client</span><span class="sxs-lookup"><span data-stu-id="6d590-135">Client</span></span>  
 <span data-ttu-id="6d590-136">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d590-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6d590-137">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6d590-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6d590-138">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="6d590-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="6d590-139">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="6d590-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="6d590-140">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d590-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="6d590-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6d590-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="6d590-142">Code</span><span class="sxs-lookup"><span data-stu-id="6d590-142">Code</span></span>  
 <span data-ttu-id="6d590-143">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="6d590-143">The following code creates the client.</span></span> <span data-ttu-id="6d590-144">Der Sicherheitsmodus wird auf "Nachricht" und der Clientanmeldeinformationstyp wird auf "Zertifikat" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="6d590-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="6d590-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6d590-145">Configuration</span></span>  
 <span data-ttu-id="6d590-146">Der Client wird wie folgt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6d590-146">The following configures the client.</span></span> <span data-ttu-id="6d590-147">Ein Clientzertifikat muss angegeben werden, mithilfe der [ \<ClientCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="6d590-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="6d590-148">Darüber hinaus wird das Dienstzertifikat mithilfe angegeben die [ \<DefaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="6d590-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d590-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d590-149">See Also</span></span>  
 [<span data-ttu-id="6d590-150">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6d590-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="6d590-151">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="6d590-151">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)  
 [<span data-ttu-id="6d590-152">Vorgehensweise: Erstellen und Installieren von temporären Zertifikaten in WCF für die Transportsicherheit während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="6d590-152">How to: Create and Install Temporary Certificates in WCF for Transport Security During Development</span></span>](http://go.microsoft.com/fwlink/?LinkId=244264)
