---
title: Transportsicherheit mit Windows-Authentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 6703da4f97cba38ee0dc334d3010ca509d1fb3ef
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598696"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="9db51-102">Transportsicherheit mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9db51-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="9db51-103">Das folgende Szenario zeigt einen von der Windows-Sicherheit gesicherten Windows Communication Foundation (WCF)-Client und-Dienst.</span><span class="sxs-lookup"><span data-stu-id="9db51-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="9db51-104">Weitere Informationen zum Programmieren finden Sie unter Vorgehens [Weise: Sichern eines Dienstanbieter mit Windows-Anmelde](../how-to-secure-a-service-with-windows-credentials.md)Informationen.</span><span class="sxs-lookup"><span data-stu-id="9db51-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="9db51-105">Ein Intranetwebdienst zeigt Personalinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9db51-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="9db51-106">Der Client ist eine Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9db51-106">The client is a Windows Form application.</span></span> <span data-ttu-id="9db51-107">Die Anwendung wird in einer Domäne mit einem Kerberos-Controller bereitgestellt, der die Domäne sichert.</span><span class="sxs-lookup"><span data-stu-id="9db51-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Transportsicherheit mit Windows-Authentifizierung](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="9db51-109">Merkmal</span><span class="sxs-lookup"><span data-stu-id="9db51-109">Characteristic</span></span>|<span data-ttu-id="9db51-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9db51-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9db51-111">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="9db51-111">Security Mode</span></span>|<span data-ttu-id="9db51-112">Transport</span><span class="sxs-lookup"><span data-stu-id="9db51-112">Transport</span></span>|  
|<span data-ttu-id="9db51-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="9db51-113">Interoperability</span></span>|<span data-ttu-id="9db51-114">Nur WCF</span><span class="sxs-lookup"><span data-stu-id="9db51-114">WCF only</span></span>|  
|<span data-ttu-id="9db51-115">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="9db51-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="9db51-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="9db51-116">Authentication (Client)</span></span>|<span data-ttu-id="9db51-117">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="9db51-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="9db51-118">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="9db51-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="9db51-119">Integrität</span><span class="sxs-lookup"><span data-stu-id="9db51-119">Integrity</span></span>|<span data-ttu-id="9db51-120">Ja</span><span class="sxs-lookup"><span data-stu-id="9db51-120">Yes</span></span>|  
|<span data-ttu-id="9db51-121">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="9db51-121">Confidentiality</span></span>|<span data-ttu-id="9db51-122">Ja</span><span class="sxs-lookup"><span data-stu-id="9db51-122">Yes</span></span>|  
|<span data-ttu-id="9db51-123">Transport</span><span class="sxs-lookup"><span data-stu-id="9db51-123">Transport</span></span>|<span data-ttu-id="9db51-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="9db51-124">NET.TCP</span></span>|  
|<span data-ttu-id="9db51-125">Bindung</span><span class="sxs-lookup"><span data-stu-id="9db51-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="9db51-126">Dienst</span><span class="sxs-lookup"><span data-stu-id="9db51-126">Service</span></span>  
 <span data-ttu-id="9db51-127">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9db51-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="9db51-128">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9db51-128">Do one of the following:</span></span>  
  
- <span data-ttu-id="9db51-129">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="9db51-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="9db51-130">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="9db51-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9db51-131">Code</span><span class="sxs-lookup"><span data-stu-id="9db51-131">Code</span></span>  
 <span data-ttu-id="9db51-132">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Windows-Sicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9db51-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="9db51-133">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9db51-133">Configuration</span></span>  
 <span data-ttu-id="9db51-134">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienstendpunkt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="9db51-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="9db51-135">Client</span><span class="sxs-lookup"><span data-stu-id="9db51-135">Client</span></span>  
 <span data-ttu-id="9db51-136">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9db51-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="9db51-137">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9db51-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="9db51-138">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="9db51-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="9db51-139">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="9db51-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="9db51-140">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="9db51-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="9db51-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9db51-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="9db51-142">Code</span><span class="sxs-lookup"><span data-stu-id="9db51-142">Code</span></span>  
 <span data-ttu-id="9db51-143">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="9db51-143">The following code creates the client.</span></span> <span data-ttu-id="9db51-144">Die Bindung ist für die Verwendung der Transportmodussicherheit mit dem TCP-Transport konfiguriert, wobei der Clientanmeldeinformationstyp auf Windows festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9db51-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="9db51-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9db51-145">Configuration</span></span>  
 <span data-ttu-id="9db51-146">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Client zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9db51-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9db51-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9db51-147">See also</span></span>

- [<span data-ttu-id="9db51-148">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="9db51-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="9db51-149">Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="9db51-149">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="9db51-150">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="9db51-150">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
