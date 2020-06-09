---
title: Nachrichtensicherheit über einen Windows-Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: dcb311523c6ec41b62f6e69fe6bc7635b9d49708
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595231"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="6a191-102">Nachrichtensicherheit über einen Windows-Client</span><span class="sxs-lookup"><span data-stu-id="6a191-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="6a191-103">Dieses Szenario zeigt einen Windows Communication Foundation (WCF)-Client und-Server, die durch den Nachrichten Sicherheitsmodus gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="6a191-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="6a191-104">Client und Dienst werden mit Windows-Anmeldeinformationen authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="6a191-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="6a191-105">![Nachrichten Sicherheit mit einem Windows-Client](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32bd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="6a191-105">![Message security with a Windows client](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="6a191-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="6a191-106">Characteristic</span></span>|<span data-ttu-id="6a191-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a191-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6a191-108">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="6a191-108">Security Mode</span></span>|<span data-ttu-id="6a191-109">`Message`</span><span class="sxs-lookup"><span data-stu-id="6a191-109">Message</span></span>|  
|<span data-ttu-id="6a191-110">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="6a191-110">Interoperability</span></span>|<span data-ttu-id="6a191-111">Nur WCF</span><span class="sxs-lookup"><span data-stu-id="6a191-111">WCF Only</span></span>|  
|<span data-ttu-id="6a191-112">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="6a191-112">Authentication (Server)</span></span>|<span data-ttu-id="6a191-113">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="6a191-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="6a191-114">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="6a191-114">Authentication (Client)</span></span>|<span data-ttu-id="6a191-115">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="6a191-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="6a191-116">Integrität</span><span class="sxs-lookup"><span data-stu-id="6a191-116">Integrity</span></span>|<span data-ttu-id="6a191-117">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="6a191-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="6a191-118">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="6a191-118">Confidentiality</span></span>|<span data-ttu-id="6a191-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="6a191-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="6a191-120">Transport</span><span class="sxs-lookup"><span data-stu-id="6a191-120">Transport</span></span>|<span data-ttu-id="6a191-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="6a191-121">NET.TCP</span></span>|  
|<span data-ttu-id="6a191-122">Bindung</span><span class="sxs-lookup"><span data-stu-id="6a191-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="6a191-123">Dienst</span><span class="sxs-lookup"><span data-stu-id="6a191-123">Service</span></span>  
 <span data-ttu-id="6a191-124">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a191-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6a191-125">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6a191-125">Do one of the following:</span></span>  
  
- <span data-ttu-id="6a191-126">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a191-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="6a191-127">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="6a191-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6a191-128">Code</span><span class="sxs-lookup"><span data-stu-id="6a191-128">Code</span></span>  
 <span data-ttu-id="6a191-129">Der folgende Code zeigt, wie Sie einen Dienstendpunkt erstellen, der die Nachrichtensicherheit zum Herstellen eines sicheren Kontexts mit einem Windows-Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a191-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="6a191-130">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6a191-130">Configuration</span></span>  
 <span data-ttu-id="6a191-131">Die folgende Konfiguration kann statt des Codes zum Einrichten des Diensts verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6a191-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="6a191-132">Client</span><span class="sxs-lookup"><span data-stu-id="6a191-132">Client</span></span>  
 <span data-ttu-id="6a191-133">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a191-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6a191-134">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6a191-134">Do one of the following:</span></span>  
  
- <span data-ttu-id="6a191-135">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="6a191-135">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="6a191-136">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="6a191-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="6a191-137">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a191-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="6a191-138">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6a191-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="6a191-139">Code</span><span class="sxs-lookup"><span data-stu-id="6a191-139">Code</span></span>  
 <span data-ttu-id="6a191-140">Mit dem folgenden Code wird ein Client erstellt.</span><span class="sxs-lookup"><span data-stu-id="6a191-140">The following code creates a client.</span></span> <span data-ttu-id="6a191-141">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `Windows` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6a191-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="6a191-142">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6a191-142">Configuration</span></span>  
 <span data-ttu-id="6a191-143">Die folgende Konfiguration wird zum Festlegen der Clienteigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a191-143">The following configuration is used to set the client properties.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a191-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a191-144">See also</span></span>

- [<span data-ttu-id="6a191-145">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="6a191-145">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="6a191-146">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="6a191-146">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
