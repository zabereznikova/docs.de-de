---
title: Nachrichtensicherheit über einen Windows-Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 34f6078baba86868fa03f37873731c39e73ac81f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44209723"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="2ee92-102">Nachrichtensicherheit über einen Windows-Client</span><span class="sxs-lookup"><span data-stu-id="2ee92-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="2ee92-103">Dieses Szenario zeigt einen Windows Communication Foundation (WCF)-Client und Server im nachrichtensicherheitsmodus gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="2ee92-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="2ee92-104">Client und Dienst werden mit Windows-Anmeldeinformationen authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="2ee92-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="2ee92-105">![Nachrichtensicherheit mit einem Windows-Client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="2ee92-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="2ee92-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="2ee92-106">Characteristic</span></span>|<span data-ttu-id="2ee92-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ee92-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2ee92-108">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="2ee92-108">Security Mode</span></span>|<span data-ttu-id="2ee92-109">Meldung</span><span class="sxs-lookup"><span data-stu-id="2ee92-109">Message</span></span>|  
|<span data-ttu-id="2ee92-110">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="2ee92-110">Interoperability</span></span>|<span data-ttu-id="2ee92-111">Nur WCF</span><span class="sxs-lookup"><span data-stu-id="2ee92-111">WCF Only</span></span>|  
|<span data-ttu-id="2ee92-112">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="2ee92-112">Authentication (Server)</span></span>|<span data-ttu-id="2ee92-113">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="2ee92-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="2ee92-114">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="2ee92-114">Authentication (Client)</span></span>|<span data-ttu-id="2ee92-115">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="2ee92-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="2ee92-116">Integrität</span><span class="sxs-lookup"><span data-stu-id="2ee92-116">Integrity</span></span>|<span data-ttu-id="2ee92-117">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="2ee92-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="2ee92-118">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="2ee92-118">Confidentiality</span></span>|<span data-ttu-id="2ee92-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="2ee92-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="2ee92-120">Transport</span><span class="sxs-lookup"><span data-stu-id="2ee92-120">Transport</span></span>|<span data-ttu-id="2ee92-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="2ee92-121">NET.TCP</span></span>|  
|<span data-ttu-id="2ee92-122">Bindung</span><span class="sxs-lookup"><span data-stu-id="2ee92-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="2ee92-123">Dienst</span><span class="sxs-lookup"><span data-stu-id="2ee92-123">Service</span></span>  
 <span data-ttu-id="2ee92-124">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ee92-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2ee92-125">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ee92-125">Do one of the following:</span></span>  
  
-   <span data-ttu-id="2ee92-126">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ee92-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="2ee92-127">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="2ee92-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2ee92-128">Code</span><span class="sxs-lookup"><span data-stu-id="2ee92-128">Code</span></span>  
 <span data-ttu-id="2ee92-129">Der folgende Code zeigt, wie Sie einen Dienstendpunkt erstellen, der die Nachrichtensicherheit zum Herstellen eines sicheren Kontexts mit einem Windows-Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ee92-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="2ee92-130">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2ee92-130">Configuration</span></span>  
 <span data-ttu-id="2ee92-131">Die folgende Konfiguration kann statt des Codes zum Einrichten des Diensts verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="2ee92-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="2ee92-132">Client</span><span class="sxs-lookup"><span data-stu-id="2ee92-132">Client</span></span>  
 <span data-ttu-id="2ee92-133">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ee92-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2ee92-134">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ee92-134">Do one of the following:</span></span>  
  
-   <span data-ttu-id="2ee92-135">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="2ee92-135">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="2ee92-136">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="2ee92-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="2ee92-137">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ee92-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="2ee92-138">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ee92-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="2ee92-139">Code</span><span class="sxs-lookup"><span data-stu-id="2ee92-139">Code</span></span>  
 <span data-ttu-id="2ee92-140">Mit dem folgenden Code wird ein Client erstellt.</span><span class="sxs-lookup"><span data-stu-id="2ee92-140">The following code creates a client.</span></span> <span data-ttu-id="2ee92-141">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `Windows` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2ee92-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="2ee92-142">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2ee92-142">Configuration</span></span>  
 <span data-ttu-id="2ee92-143">Die folgende Konfiguration wird zum Festlegen der Clienteigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ee92-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"   
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">          
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ee92-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ee92-144">See Also</span></span>  
 [<span data-ttu-id="2ee92-145">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2ee92-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="2ee92-146">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="2ee92-146">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
