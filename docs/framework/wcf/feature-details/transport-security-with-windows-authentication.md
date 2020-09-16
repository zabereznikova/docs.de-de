---
title: Transportsicherheit mit Windows-Authentifizierung
description: Lesen Sie dieses Szenario, in dem ein von der Windows-Sicherheit geschützter WCF-Client/-Dienst angezeigt wird. In diesem Beispiel zeigt ein Intranetdienst Human Resources-Informationen an.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 9b81f2f2fb6352af254146951ed35ad4fdca8caa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545206"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="45771-104">Transportsicherheit mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="45771-104">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="45771-105">Das folgende Szenario zeigt einen von der Windows-Sicherheit gesicherten Windows Communication Foundation (WCF)-Client und-Dienst.</span><span class="sxs-lookup"><span data-stu-id="45771-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="45771-106">Weitere Informationen zum Programmieren finden Sie unter Vorgehens [Weise: Sichern eines Dienstanbieter mit Windows-Anmelde](../how-to-secure-a-service-with-windows-credentials.md)Informationen.</span><span class="sxs-lookup"><span data-stu-id="45771-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="45771-107">Ein Intranetwebdienst zeigt Personalinformationen an.</span><span class="sxs-lookup"><span data-stu-id="45771-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="45771-108">Der Client ist eine Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="45771-108">The client is a Windows Form application.</span></span> <span data-ttu-id="45771-109">Die Anwendung wird in einer Domäne mit einem Kerberos-Controller bereitgestellt, der die Domäne sichert.</span><span class="sxs-lookup"><span data-stu-id="45771-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Transportsicherheit mit Windows-Authentifizierung](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="45771-111">Merkmal</span><span class="sxs-lookup"><span data-stu-id="45771-111">Characteristic</span></span>|<span data-ttu-id="45771-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="45771-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="45771-113">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="45771-113">Security Mode</span></span>|<span data-ttu-id="45771-114">Transport</span><span class="sxs-lookup"><span data-stu-id="45771-114">Transport</span></span>|  
|<span data-ttu-id="45771-115">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="45771-115">Interoperability</span></span>|<span data-ttu-id="45771-116">Nur WCF</span><span class="sxs-lookup"><span data-stu-id="45771-116">WCF only</span></span>|  
|<span data-ttu-id="45771-117">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="45771-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="45771-118">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="45771-118">Authentication (Client)</span></span>|<span data-ttu-id="45771-119">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="45771-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="45771-120">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="45771-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="45771-121">Integrität</span><span class="sxs-lookup"><span data-stu-id="45771-121">Integrity</span></span>|<span data-ttu-id="45771-122">Ja</span><span class="sxs-lookup"><span data-stu-id="45771-122">Yes</span></span>|  
|<span data-ttu-id="45771-123">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="45771-123">Confidentiality</span></span>|<span data-ttu-id="45771-124">Ja</span><span class="sxs-lookup"><span data-stu-id="45771-124">Yes</span></span>|  
|<span data-ttu-id="45771-125">Transport</span><span class="sxs-lookup"><span data-stu-id="45771-125">Transport</span></span>|<span data-ttu-id="45771-126">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="45771-126">NET.TCP</span></span>|  
|<span data-ttu-id="45771-127">Bindung</span><span class="sxs-lookup"><span data-stu-id="45771-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="45771-128">Dienst</span><span class="sxs-lookup"><span data-stu-id="45771-128">Service</span></span>  
 <span data-ttu-id="45771-129">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45771-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="45771-130">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="45771-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="45771-131">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="45771-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="45771-132">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="45771-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45771-133">Code</span><span class="sxs-lookup"><span data-stu-id="45771-133">Code</span></span>  
 <span data-ttu-id="45771-134">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Windows-Sicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="45771-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="45771-135">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="45771-135">Configuration</span></span>  
 <span data-ttu-id="45771-136">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienstendpunkt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="45771-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="45771-137">Client</span><span class="sxs-lookup"><span data-stu-id="45771-137">Client</span></span>  
 <span data-ttu-id="45771-138">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45771-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="45771-139">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="45771-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="45771-140">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="45771-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="45771-141">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="45771-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="45771-142">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="45771-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="45771-143">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="45771-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="45771-144">Code</span><span class="sxs-lookup"><span data-stu-id="45771-144">Code</span></span>  
 <span data-ttu-id="45771-145">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="45771-145">The following code creates the client.</span></span> <span data-ttu-id="45771-146">Die Bindung ist für die Verwendung der Transportmodussicherheit mit dem TCP-Transport konfiguriert, wobei der Clientanmeldeinformationstyp auf Windows festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="45771-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="45771-147">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="45771-147">Configuration</span></span>  
 <span data-ttu-id="45771-148">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Client zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45771-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45771-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45771-149">See also</span></span>

- [<span data-ttu-id="45771-150">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="45771-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="45771-151">Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="45771-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="45771-152">[Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="45771-152">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
